# Análise crítica dos requisitos: Cadastro (BugBank)

Regra seguida: não inventar regras de negócio. Quando faltou informação, o ponto virou dúvida para o time de produto (ver [duvidas.md](../duvidas-para-produto/duvidas.md)).

## 1. Pontos ambíguos ou incompletos

**Validação dos campos**
- **Nome:** há tamanho mínimo ou máximo? Aceita números e caracteres especiais? Um nome só com espaços conta como "vazio"?
- **Email:** existe validação de formato? O requisito só cobre o campo vazio.
- **Senha:** há tamanho mínimo, máximo ou regra de complexidade? O requisito só diz que é obrigatória e igual à confirmação.
- **Espaços:** senha e email têm espaços nas extremidades aparados (trim) ou preservados?

**Regras de negócio**
- **Email duplicado:** é permitido? Se não, qual o comportamento e a mensagem?
- **Senhas diferentes:** qual a mensagem exibida? A comparação diferencia maiúsculas de minúsculas?
- **Número da conta:** qual o formato (tamanho, dígito verificador, separador)? Deve ser único? É sequencial ou aleatório?
- **Saldo:** onde é exibido? O valor é persistido após login e recarregamento?
- **Estado inicial da opção "Criar conta com saldo":** começa ativa ou inativa?

**Comportamento da tela**
- **Múltiplos erros:** as mensagens aparecem juntas ou uma por vez? Existe ordem de prioridade?
- **Momento da validação:** ao clicar em cadastrar, ao sair do campo ou durante a digitação?
- **Pós-cadastro:** há redirecionamento, login automático ou limpeza dos campos? A mensagem de sucesso tem texto definido?
- **Campos após erro:** o formulário mantém os dados preenchidos ou limpa tudo?

**Inconsistências de redação**
- **Nomenclatura:** o requisito usa "Confirmação de senha" no campo e "Confirmar senha" na mensagem. Qual é o rótulo oficial?
- **Concordância:** "Senha não pode ser vazio" está no masculino. É intencional ou erro de redação? Isso afeta o critério de aceite, pois o teste valida o texto literal.

## 2. Cenários não cobertos (sugeridos como testes exploratórios)

Nenhum destes tem resultado esperado definido no requisito. Por isso ficaram fora da suíte. Devem ser executados registrando o comportamento observado.

| Área | Cenário | Falha que poderia revelar |
|---|---|---|
| Dados | Email sem "@", sem domínio ou com espaços | Cadastro aceitando email inválido |
| Dados | Email duplicado | Duas contas com o mesmo email, ou erro sem tratamento |
| Dados | Campos preenchidos só com espaços | Validação de vazio contornada |
| Dados | Tamanhos extremos (1 caractere, centenas de caracteres) | Estouro de layout, truncamento silencioso ou erro |
| Dados | Caracteres especiais, acentos e emojis no nome | Erro de codificação ou dado corrompido |
| Dados | Entradas com HTML ou script (ex.: `<script>`) | Falha de XSS, especialmente se o nome for exibido depois |
| Dados | Emails com maiúsculas/minúsculas diferentes | Duplicidade não detectada |
| Validação | Confirmação preenchida e senha vazia, e o inverso | Mensagem incorreta ou ordem de validação errada |
| Validação | Senhas iguais, mas com espaço no final de um dos campos | Comparação inconsistente |
| Interação | Duplo clique ou cliques repetidos em Cadastrar | Contas duplicadas ou números diferentes para o mesmo cadastro |
| Interação | Envio do formulário pelo Enter | Comportamento diferente do clique no botão |
| Interação | Recarregar ou voltar a página após o sucesso | Reenvio do cadastro ou perda do número da conta |
| Persistência | Anotar o número da conta e fazer login em seguida | Número ou saldo exibido diferente do persistido |
| Persistência | Criar várias contas em sequência | Número de conta repetido |
| Interface | Senha exibida em texto puro, sem mascaramento | Exposição de credencial |
| Interface | Outros navegadores, mobile e zoom alterado | Falhas de layout ou comportamento |
| Acessibilidade | Navegação só por teclado, leitor de tela, contraste das mensagens | Barreiras para parte dos usuários |
| Resiliência | Falha de rede ou lentidão durante o envio | Conta criada sem confirmação ao usuário, ou o inverso |

## 3. Maiores riscos

**Para o usuário**
- **Perda do acesso à conta:** número da conta não exibido corretamente ou perdido ao recarregar.
- **Senha divergente aceita:** o usuário fica com uma senha diferente da digitada.
- **Saldo incorreto:** conta criada com saldo diferente do informado.
- **Exposição de dados:** senha visível ou dado pessoal em mensagens de erro.
- **Cadastro duplicado por engano:** clique repetido gera contas paralelas e confusão de saldos.

**Para o negócio**
- **Saldo inicial indevido:** a opção "Criar conta com saldo" concede R$ 1.000,00. Se puder ser contornada ou adulterada na requisição, há risco de criação irregular de valor. É o ponto financeiramente mais sensível e vale testar se a regra é aplicada também no servidor.
- **Fraude e abuso:** sem regra de duplicidade ou limite de tentativas, é possível criar contas em massa e explorar o saldo inicial.
- **Base de dados inconsistente:** sem validação de formato de email e de nome, o cadastro tem baixa qualidade.
- **Reputacional e regulatório:** com dados reais, falhas no tratamento de dados pessoais e credenciais têm implicações de LGPD.
- **Requisito frágil como critério de aceite:** com tantas lacunas, cada pessoa interpreta o esperado de um jeito, gerando defeitos que na verdade são dúvidas de requisito.

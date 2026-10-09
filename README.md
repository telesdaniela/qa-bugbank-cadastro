# Testes da funcionalidade de Cadastro: BugBank

Projeto de prática de QA, criado de um exercício do Workshop da EBAC - O Futuro do QA na Era da IA.

No projeto analisei a funcionalidade de **Cadastro** do [BugBank](https://bugbank.netlify.app), um banco digital fictício criado para treino de testes.

O foco do projeto era usar a IA como uma ferramenta de apoio no aprendizado sobre como desenvolver o pensamento crítico e analítico.
Não é só listar casos de teste, mas mostrar o raciocínio de QA: analisar o requisito, apontar lacunas, evitar suposições e transformar dúvidas em perguntas para o time de produto.

## O que foi feito

- Análise dos requisitos, com identificação de ambiguidades e informações faltantes
- 8 casos de teste (positivos, negativos e de limite)
- 3 casos eliminados por dependerem de comportamento não definido, com justificativa
- 13 dúvidas levantadas para o time de produto
- Análise de cenários não cobertos e de riscos para o usuário e para o negócio
- Execução dos 8 casos de teste, com registro dos resultados e de 3 bugs

## Resultado da execução

**Ambiente:** Safari, macOS, https://bugbank.netlify.app | **Data:** 09/10/2026

**8 casos executados: 5 passaram e 3 falharam. 3 bugs registrados (BUG-001, BUG-002 e BUG-003).**

| Caso | Cenário | Resultado |
| ---- | ------- | --------- |
| CT01 | Cadastro com sucesso, "Criar conta com saldo" ativa | Passou |
| CT02 | Cadastro com sucesso, "Criar conta com saldo" inativa | Passou |
| CT03 | Cadastro sem preencher Nome | Passou |
| CT04 | Cadastro sem preencher Email | Falhou (BUG-001) |
| CT05 | Cadastro sem preencher Senha | Falhou (BUG-002) |
| CT06 | Cadastro sem preencher Confirmação de senha | Falhou (BUG-003) |
| CT08 | Senha e Confirmação de senha diferentes | Passou |
| CT10 | Alternar a opção "Criar conta com saldo" antes de cadastrar | Passou |

**Bugs encontrados:** nos campos Email, Senha e Confirmação de senha, a mensagem exibida é "É campo obrigatório" em vez da mensagem específica definida no requisito. No campo Nome a mensagem está correta, o que indica inconsistência entre os campos.

- [BUG-001](bugs/BUG-001-mensagem-campo-obrigatorio.md) – Email vazio
- [BUG-002](bugs/BUG-002-senha-vazia-mensagem-generica.md) – Senha vazia
- [BUG-003](bugs/BUG-003-confirmacao-senha-vazia-mensagem-generica.md) – Confirmação de senha vazia

## Conteúdo

| Pasta / arquivo | Descrição |
| --------------- | --------- |
| [casos-de-teste/casos-de-teste.md](casos-de-teste/casos-de-teste.md) | Casos de teste mantidos (leitura direta no GitHub) |
| [casos-de-teste/casos-eliminados.md](casos-de-teste/casos-eliminados.md) | Casos eliminados e o motivo de cada um |
| [casos-de-teste/casos-de-teste.csv](casos-de-teste/casos-de-teste.csv) | Mesmos casos em CSV, para importar no Excel ou Google Sheets |
| [casos-de-teste/BugBank_Cadastro_Casos_de_Teste.xlsx](casos-de-teste/BugBank_Cadastro_Casos_de_Teste.xlsx) | Planilha completa (casos, eliminados, dúvidas e resumo) |
| [execucao/BugBank_Cadastro_Execucao.xlsx](execução/BugBank_Cadastro_Execucao.xlsx) | Planilha com o resultado da execução dos casos |
| [bugs/](bugs/) | Registro dos 3 bugs encontrados, com evidências |
| [analise-de-requisitos/analise-critica.md](analise-de-requisitos/analise-critica.md) | Ambiguidades, cenários não cobertos e riscos |
| [duvidas-para-produto/duvidas.md](duvidas-para-produto/duvidas.md) | Perguntas para validação das regras de negócio |

## Requisitos analisados

- Nome, Email, Senha e Confirmação de senha são obrigatórios
- Cada campo vazio exibe uma mensagem específica (ex.: "Nome não pode ser vazio")
- A opção "Criar conta com saldo" define o saldo inicial: R$ 1.000,00 (ativa) ou R$ 0,00 (inativa)
- Senha e confirmação de senha precisam ser iguais
- Cadastro com sucesso exibe o número da conta criada

## Decisões de QA

- **Não inventei regras de negócio.** O que o requisito não define virou dúvida ou suposição registrada, não caso de teste.
- **Eliminei casos ambíguos** para evitar defeitos falsos. Cada um tem justificativa e uma condição clara para voltar à suíte.
- **Mensagem divergente do requisito foi tratada como falha** (severidade baixa), porque o requisito define o texto de cada campo. A dúvida D11 registra se o texto exato é obrigatório ou apenas um exemplo.
- **Destaquei o maior risco de negócio:** a opção que concede R$ 1.000,00 de saldo inicial deve ser validada também no servidor, e não só na tela.

## Próximos passos (conforme aprendizado)

- [x] Executar os casos e registrar os resultados
- [ ] Testes exploratórios dos cenários não cobertos
- [x] Registrar bugs encontrados, com evidências
- [ ] Automatizar os fluxos principais (Playwright ou Cypress)

## Autor

**Daniela Teles** | [LinkedIn](https://www.linkedin.com/in/telesdaniela/) | danielateles18@gmail.com

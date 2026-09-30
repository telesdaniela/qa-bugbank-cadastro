# Testes da funcionalidade de Cadastro: BugBank

Projeto de prática de QA, criado de um exercício do Workshop da EBAC - O Futuro do QA na Era da IA,

No projeto analisei a funcionalidade de **Cadastro** do [BugBank](https://bugbank.netlify.app), um banco digital fictício criado para treino de testes.

O foco do projeto era usar a IA como uma ferramenta de apoio no aprendizado sobre como desenvolver o pensamento crítico e analítico. 
Não é só listar casos de teste, mas mostrar o raciocínio de QA: analisar o requisito, apontar lacunas, evitar suposições e transformar dúvidas em perguntas para o time de produto.

## O que foi feito

- Análise dos requisitos, com identificação de ambiguidades e informações faltantes
- 8 casos de teste (positivos, negativos e de limite)
- 3 casos eliminados por dependerem de comportamento não definido, com justificativa
- 13 dúvidas levantadas para o time de produto
- Análise de cenários não cobertos e de riscos para o usuário e para o negócio

## Conteúdo

| Pasta / arquivo | Descrição |
|---|---|
| [casos-de-teste/casos-de-teste.md](casos-de-teste/casos-de-teste.md) | Casos de teste mantidos (leitura direta no GitHub) |
| [casos-de-teste/casos-eliminados.md](casos-de-teste/casos-eliminados.md) | Casos eliminados e o motivo de cada um |
| [casos-de-teste/casos-de-teste.csv](casos-de-teste/casos-de-teste.csv) | Mesmos casos em CSV, para importar no Excel ou Google Sheets |
| [casos-de-teste/BugBank_Cadastro_Casos_de_Teste.xlsx](casos-de-teste/BugBank_Cadastro_Casos_de_Teste.xlsx) | Planilha completa (casos, eliminados, dúvidas e resumo) |
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
- **Destaquei o maior risco de negócio:** a opção que concede R$ 1.000,00 de saldo inicial deve ser validada também no servidor, e não só na tela.

## Próximos passos (conforme aprendizado)

- [ ] Executar os casos e registrar os resultados
- [ ] Testes exploratórios dos cenários não cobertos
- [ ] Registrar bugs encontrados, com evidências
- [ ] Automatizar os fluxos principais (Playwright ou Cypress)

## Autor

**Daniela Teles** | (https://www.linkedin.com/in/telesdaniela/) | danielateles18@gmail.com

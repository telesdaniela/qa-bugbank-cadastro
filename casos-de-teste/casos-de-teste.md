# Casos de teste: Cadastro (BugBank)

Baseados somente nos requisitos fornecidos. Suposições e dúvidas estão em [duvidas-para-produto](../duvidas-para-produto/duvidas.md). Casos eliminados por ambiguidade estão em [casos-eliminados.md](casos-eliminados.md).

| ID | Cenário | Pré-condição | Passos | Resultado esperado | Tipo | Prioridade |
|---|---|---|---|---|---|---|
| CT01 | Cadastro com sucesso com a opção "Criar conta com saldo" ativa | Estar na tela de cadastro; e-mail ainda não utilizado | 1) Preencher Nome "Maria Silva"; 2) Preencher Email "maria.teste01@email.com"; 3) Preencher Senha "Senha@123"; 4) Preencher Confirmação de senha "Senha@123"; 5) Ativar "Criar conta com saldo"; 6) Clicar em Cadastrar | Conta criada com sucesso, com o número da conta exibido e saldo de R$ 1.000,00 | Positivo | Alta |
| CT02 | Cadastro com sucesso com a opção "Criar conta com saldo" inativa | Estar na tela de cadastro; e-mail ainda não utilizado | 1) Preencher Nome, Email, Senha e Confirmação de senha com dados válidos e iguais; 2) Manter "Criar conta com saldo" inativa; 3) Clicar em Cadastrar | Conta criada com sucesso, com o número da conta exibido e saldo de R$ 0,00 | Positivo | Alta |
| CT03 | Cadastro sem preencher Nome | Estar na tela de cadastro | 1) Deixar Nome vazio; 2) Preencher Email, Senha e Confirmação de senha com dados válidos; 3) Clicar em Cadastrar | Exibe a mensagem "Nome não pode ser vazio" e a conta não é criada | Negativo | Alta |
| CT04 | Cadastro sem preencher Email | Estar na tela de cadastro | 1) Deixar Email vazio; 2) Preencher Nome, Senha e Confirmação de senha com dados válidos; 3) Clicar em Cadastrar | Exibe a mensagem "Email não pode ser vazio" e a conta não é criada | Negativo | Alta |
| CT05 | Cadastro sem preencher Senha | Estar na tela de cadastro | 1) Deixar Senha vazia; 2) Preencher Nome, Email e Confirmação de senha; 3) Clicar em Cadastrar | Exibe a mensagem "Senha não pode ser vazio" e a conta não é criada | Negativo | Alta |
| CT06 | Cadastro sem preencher Confirmação de senha | Estar na tela de cadastro | 1) Deixar Confirmação de senha vazia; 2) Preencher Nome, Email e Senha com dados válidos; 3) Clicar em Cadastrar | Exibe a mensagem "Confirmar senha não pode ser vazio" e a conta não é criada | Negativo | Alta |
| CT08 | Senha e Confirmação de senha diferentes | Estar na tela de cadastro | 1) Preencher Nome e Email com dados válidos; 2) Preencher Senha "Senha@123"; 3) Preencher Confirmação de senha "Outra@456"; 4) Clicar em Cadastrar | Cadastro não é concluído, nenhuma conta é criada e nenhum número de conta é exibido (registrar a mensagem apresentada, pois o requisito não a define) | Negativo | Alta |
| CT10 | Alternar a opção "Criar conta com saldo" antes de cadastrar (ativar, desativar e ativar) | Estar na tela de cadastro; e-mail ainda não utilizado | 1) Preencher todos os campos com dados válidos; 2) Ativar a opção; 3) Desativar a opção; 4) Ativar a opção novamente; 5) Clicar em Cadastrar | Conta criada com saldo de R$ 1.000,00, prevalecendo o último estado da opção | Limite | Baixa |

## Observações

- CT08: o texto da mensagem para senhas diferentes não está no requisito (dúvida D3).
- CT10: baixo risco. É o primeiro candidato a corte se faltar tempo.
- Use um e-mail diferente a cada execução para evitar interferência de uma eventual regra de duplicidade.

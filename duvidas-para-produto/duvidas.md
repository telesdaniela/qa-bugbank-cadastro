# Suposições e dúvidas para o time de produto

## Suposições feitas pelo QA

| ID | Suposição | Casos afetados |
|---|---|---|
| S1 | O saldo pode ser verificado na tela de sucesso ou após login com a conta recém-criada. | CT01, CT02, CT10 |
| S2 | Os textos das mensagens são validados exatamente como no requisito, inclusive "vazio" no masculino. | CT03 a CT06 |
| S3 | O estado inicial da opção "Criar conta com saldo" não é definido; os passos ativam ou desativam explicitamente. | CT01, CT02, CT10 |
| S4 | Os dados de teste são exemplos. Usar um email diferente a cada execução. | Todos |

## Dúvidas

| ID | Dúvida | Casos afetados | Status |
|---|---|---|---|
| D1 | Existe validação de formato de email? Qual? | Não coberto | Em aberto |
| D2 | Email duplicado é permitido? Se não, qual a mensagem? | Não coberto | Em aberto |
| D3 | Qual a mensagem exibida para senhas diferentes? | CT08 | Em aberto |
| D4 | Há regras de tamanho e complexidade para senha, e tamanho máximo para nome e email? | Não coberto | Em aberto |
| D5 | Espaços nas extremidades e campos só com espaços: como devem ser tratados? | Não coberto | Em aberto |
| D6 | Qual o formato e a regra de unicidade do número da conta? | CT01, CT02 | Em aberto |
| D7 | Onde o saldo é exibido, e o valor é persistido após login? | CT01, CT02, CT10 | Em aberto |
| D8 | A opção "Criar conta com saldo" começa ativa ou inativa? | CT01, CT02, CT10 | Em aberto |
| D9 | As mensagens de erro aparecem juntas ou uma por vez? Existe ordem de prioridade? | CT07 (eliminado) | Em aberto |
| D10 | O que acontece após o cadastro com sucesso (redirecionamento, limpeza do formulário, texto da mensagem)? | CT11 (eliminado) | Em aberto |
| D11 | Os textos das mensagens, incluindo a concordância "vazio", estão corretos? O rótulo oficial é "Confirmação de senha" ou "Confirmar senha"? | CT03 a CT06 | Em aberto |
| D12 | A comparação entre senha e confirmação diferencia maiúsculas de minúsculas? | CT09 (eliminado) | Em aberto |
| D13 | Após um erro de validação, o formulário mantém os dados preenchidos ou limpa tudo? | CT11 (eliminado) | Em aberto |

# BUG-001 – Mensagem de erro genérica nos campos Email, Senha e Confirmação de senha vazios

- **Severidade:** Baixa (a conta não é criada; apenas o texto da mensagem diverge)
- **Prioridade:** Média
- **Casos de teste relacionados:** CT04, CT05, CT06
- **Ambiente:** [Safari], [MacOs], https://bugbank.netlify.app
- **Data:** [09/10/2026]

## Passos para reproduzir
1. Acessar a tela de cadastro.
2. Deixar o campo Email vazio (repetir com Senha e com Confirmação de senha).
3. Preencher os demais campos com dados válidos.
4. Clicar em Cadastrar.

## Resultado esperado
Mensagem específica por campo, conforme o requisito:
- "Email não pode ser vazio"
- "Senha não pode ser vazio"
- "Confirmar senha não pode ser vazio"

## Resultado obtido
A mensagem exibida é "É campo obrigatório" nos três campos. A conta não é criada.

## Observações
- No campo Nome, a mensagem exibida é a do requisito ("Nome não pode ser vazio"), o que indica inconsistência entre os campos.
- Dúvida relacionada em aberto: D11 (o texto das mensagens é obrigatório ou é só exemplo?).

## Evidências
![Email vazio](evidencias/evidencias/bug001-cadastro-campo-email-vazio.png)
![Senha vazia](evidencias/evidencias/bug002-cadastro-campo-senha-vazio.png)
![Confirmação vazia](evidencias/evidencias/bug003-cadastro-campo-confirmacao-de-senha-vazio.png)

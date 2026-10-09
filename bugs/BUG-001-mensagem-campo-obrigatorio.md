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
<img width="2511" height="1228" alt="bug001-cadastro-campo-email-vazio" src="https://github.com/user-attachments/assets/4f37872d-a7cf-4f07-bf66-6c8cdb394a29" />
<img width="2505" height="1221" alt="bug002-cadastro-campo-senha-vazio" src="https://github.com/user-attachments/assets/3d0ec595-8836-4646-a0d2-9b2fa9bb3aec" />
<img width="2507" height="1227" alt="bug003-cadastro-campo-confirmacao-de-senha-vazio" src="https://github.com/user-attachments/assets/c2a8a4ba-d230-49f9-a04c-291628661b51" />



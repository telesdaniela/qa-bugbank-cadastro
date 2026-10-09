# BUG-003 – Mensagem de erro genérica no campo Confirmação de senha vazio

- **Severidade:** Baixa (a conta não é criada; apenas o texto da mensagem diverge)
- **Prioridade:** Média
- **Caso de teste relacionado:** CT06
- **Ambiente:** Safari, macOS, https://bugbank.netlify.app
- **Data:** 09/10/2026

## Passos para reproduzir
1. Acessar a tela de cadastro.
2. Deixar o campo Confirmação de senha vazio.
3. Preencher Nome, Email e Senha com dados válidos.
4. Clicar em Cadastrar.

## Resultado esperado
Exibe a mensagem "Confirmar senha não pode ser vazio" e a conta não é criada.

## Resultado obtido
A mensagem exibida é "É campo obrigatório". A conta não é criada.

## Observações
- No campo Nome, a mensagem exibida é a do requisito ("Nome não pode ser vazio"), o que indica inconsistência entre os campos.
- Mesmo comportamento observado em [BUG-001](BUG-001-mensagem-campo-obrigatorio.md) (Email) e BUG-002 (Senha).
- Dúvida relacionada em aberto: D11 (o texto das mensagens é obrigatório ou é só exemplo? O rótulo oficial é "Confirmação de senha" ou "Confirmar senha"?).

## Evidência
<img width="1200" alt="Tela de cadastro com o campo Confirmação de senha vazio exibindo a mensagem É campo obrigatório" src="https://github.com/user-attachments/assets/c2a8a4ba-d230-49f9-a04c-291628661b51" />

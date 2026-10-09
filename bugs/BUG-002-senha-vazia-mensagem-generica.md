# BUG-002 – Mensagem de erro genérica no campo Senha vazio

- **Severidade:** Baixa (a conta não é criada; apenas o texto da mensagem diverge)
- **Prioridade:** Média
- **Caso de teste relacionado:** CT05
- **Ambiente:** Safari, macOS, https://bugbank.netlify.app
- **Data:** 09/10/2026

## Passos para reproduzir
1. Acessar a tela de cadastro.
2. Deixar o campo Senha vazio.
3. Preencher Nome, Email e Confirmação de senha.
4. Clicar em Cadastrar.

## Resultado esperado
Exibe a mensagem "Senha não pode ser vazio" e a conta não é criada.

## Resultado obtido
A mensagem exibida é "É campo obrigatório". A conta não é criada.

## Observações
- No campo Nome, a mensagem exibida é a do requisito ("Nome não pode ser vazio"), o que indica inconsistência entre os campos.
- Mesmo comportamento observado em [BUG-001](BUG-001-mensagem-campo-obrigatorio.md) (Email) e BUG-003 (Confirmação de senha).
- Dúvida relacionada em aberto: D11 (o texto das mensagens é obrigatório ou é só exemplo?).

## Evidência
<img width="2505" height="1221" alt="bug002-cadastro-campo-senha-vazio" src="https://github.com/user-attachments/assets/3d0ec595-8836-4646-a0d2-9b2fa9bb3aec" />

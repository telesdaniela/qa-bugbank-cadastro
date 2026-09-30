# Casos eliminados por ambiguidade

Estes casos foram removidos da suíte porque o resultado esperado dependia de algo que o requisito não define. Manter esses casos poderia gerar defeitos falsos, baseados na minha interpretação e não em uma regra do produto.

| ID | Cenário | Por que foi eliminado | Ponto ambíguo | Como reincluir |
|---|---|---|---|---|
| CT07 | Cadastro com todos os campos obrigatórios vazios | Depende de comportamento não definido. A classificação como "Limite" também era discutível: é um negativo combinado. | O requisito não diz se, com vários campos vazios, as mensagens aparecem juntas ou uma por vez, nem em que ordem (D9). | Reincluir como Negativo quando o produto definir o comportamento de múltiplos erros. |
| CT09 | Senha e Confirmação diferentes apenas por maiúscula/minúscula | O resultado esperado se apoiava em uma suposição minha (comparação sensível a maiúsculas). | O requisito diz apenas que as senhas "precisam ser iguais", sem definir sensibilidade a maiúsculas (D12). | Reincluir como Limite quando a regra for confirmada. |
| CT11 | Corrigir um campo obrigatório após erro e reenviar | Duplica o CT03 com uma etapa a mais e depende de comportamento não especificado. | O requisito não descreve o comportamento da tela após um erro nem o pós-cadastro (D10, D13). | Reincluir como Positivo quando o comportamento pós-erro estiver definido, ou tratar como teste exploratório. |

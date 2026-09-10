# Validação do MVP

O CorpAI foi testado manualmente no n8n em três caminhos principais do workflow.

## Cenário 1 — Aprovação automática

Uma comunicação interna e rotineira foi classificada como de baixo risco e não exigiu revisão humana.

**Resultado esperado e validado:**

```text
Precisa revisao humana? → FALSE
Resultado - Aprovado automatico
status: APROVADO_AUTOMATICAMENTE
```

## Cenário 2 — Aprovação humana

Uma comunicação externa destinada a cliente foi classificada como caso que exige supervisão humana.

O workflow foi pausado na etapa de Human in the Loop e a opção `APROVAR` foi selecionada.

**Resultado esperado e validado:**

```text
Precisa revisao humana? → TRUE
Aprovacao humana → APROVAR
Aprovado pelo humano? → TRUE
Resultado - Aprovado pelo humano
status: APROVADO_PELO_HUMANO
```

## Cenário 3 — Rejeição humana

O mesmo caminho de revisão humana foi executado com a opção `REJEITAR`.

**Resultado esperado e validado:**

```text
Precisa revisao humana? → TRUE
Aprovacao humana → REJEITAR
Aprovado pelo humano? → FALSE
Resultado - Rejeitado
status: REJEITADO_PELO_HUMANO
```

## Observação sobre alucinações

Durante a evolução do protótipo, os prompts foram reforçados para impedir que o modelo acrescente nomes, datas, dias da semana, valores, prazos, responsáveis ou outras informações não fornecidas pelo usuário.

Também foi adicionada uma etapa de revisão que compara o conteúdo gerado com os dados originais e pode ajustar ou bloquear a comunicação antes da saída final.

# Arquitetura do CorpAI

## Visão geral

```text
Formulário
   ↓
Classificador + Gemini
   ↓
Redator + Gemini
   ↓
Revisor + Gemini
   ↓
IF: precisa de revisão humana?
   ├── Não → Resultado aprovado automaticamente
   └── Sim → Preparar revisão humana
               ↓
             Wait / formulário
               ↓
             IF: aprovado pelo humano?
               ├── Sim → Resultado aprovado pelo humano
               └── Não → Resultado rejeitado
```

## Decisões de projeto

- **Entrada estruturada:** reduz ambiguidade.
- **Separação de responsabilidades:** divide classificação, geração e validação.
- **Revisão automática:** procura dados inventados e inadequações.
- **Human in the Loop:** impede autonomia total em comunicações externas ou sensíveis.
- **Execução local:** n8n Community Edition em Docker durante o desenvolvimento.

# Casos de teste

## Caso 1 — Comunicação interna
**Nome do remetente:** Sandro Ferreira  
**Objetivo:** Avisar sobre manutenção programada do sistema  
**Público:** Colaboradores  
**Canal:** Teams/Slack  
**Informações principais:** O sistema ficará indisponível no dia 15/09, das 22h às 23h, para manutenção programada.  
**Tom:** Profissional e amigável  

**Esperado:** baixo risco, sem revisão humana e aprovação automática.

## Caso 2 — E-mail externo aprovado
**Nome do remetente:** Sandro Ferreira  
**Objetivo:** Informar um cliente sobre atraso em uma entrega  
**Público:** Cliente  
**Canal:** E-mail  
**Informações principais:** A entrega estava prevista para 10/09 e a nova previsão é 12/09.  
**Tom:** Transparente  

**Esperado:** revisão humana obrigatória e decisão `APROVAR`.

## Caso 3 — E-mail externo rejeitado
Repita o Caso 2 e selecione `REJEITAR`.

**Esperado:** status `REJEITADO_PELO_HUMANO` e bloqueio da comunicação.

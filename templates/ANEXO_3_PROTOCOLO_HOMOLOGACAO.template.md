# ANEXO 3 — PROTOCOLO DE HOMOLOGAÇÃO E CRITÉRIOS DE ACEITE

## 1. AMBIENTE HOMOLOGADO DE TESTES (STAGING)
<!-- Proibição expressa de validação em ambiente de desenvolvimento local ou em produção. -->
{{AMBIENTE_HOMOLOGADO_STAGING}}

## 2. JANELA DE INSPEÇÃO
<!-- Prazo improrrogável de 5 (cinco) dias úteis após disponibilização do marco. -->
{{JANELA_INSPECAO_5_DIAS}}

## 3. TAXONOMIA DE DEFEITOS E GATILHOS DE FATURAMENTO
| Nível | Descrição Técnica | Bloqueia Aceite / Faturamento? |
| :--- | :--- | :--- |
| P1 - Bloqueador | Sistema inoperante, crash contínuo ou corrupção de dados | Sim |
| P2 - Crítico | Quebra de funcionalidade core sem alternativa de contorno | Sim |
| P3 - Médio | Falha pontual com procedimento alternativo viável | Não (corrige no ciclo seguinte) |
| P4 - Cosmético | Desvios visuais leves, formatação ou textos | Não (corrige no ciclo seguinte) |

## 4. CLÁUSULA PÉTREA DE ACEITE TÁCITO (DEEMED ACCEPTANCE)
<!-- Decurso do prazo de 5 dias úteis sem relatório técnico estruturado resulta em aprovação tácita irrevogável e autorização imediata de faturamento. -->
{{CLAUSULA_ACEITE_TACITO}}

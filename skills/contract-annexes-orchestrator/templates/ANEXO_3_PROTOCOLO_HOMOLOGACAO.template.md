# ANEXO 3 — PROTOCOLO DE HOMOLOGAÇÃO E CRITÉRIOS DE ACEITE

## 1. AMBIENTE HOMOLOGADO DE TESTES (STAGING)
<!-- Proibição expressa de validação em ambiente de desenvolvimento local ou em produção. -->
{{AMBIENTE_HOMOLOGADO_STAGING}}

## 2. JANELA DE INSPEÇÃO, RETESTE E CANAL EXCLUSIVO DO PRODUCT OWNER
<!-- Prazo improrrogável de 5 (cinco) dias úteis para homologação do marco após sua disponibilização formal em Staging.
     Janela de Reteste: Disponibilizada a correção de apontamento impeditivo (P1/P2), abre-se janela de reteste de até 2 (dois) dias úteis, adstrita exclusivamente à validação do defeito corrigido, vedando-se expressamente a reabertura de testes em fluxos já homologados.
     Consolidação Exclusiva pelo PO: Reportes de inconsistência só são aceitos quando consolidados e formalizados exclusivamente pelo PO titular (ou suplente nomeado no Anexo 2). -->
{{JANELA_INSPECAO_RETESTE_PO}}

## 3. TAXONOMIA DE DEFEITOS E GATILHOS DE FATURAMENTO
| Nível | Descrição Técnica | Bloqueia Aceite / Faturamento? |
| :--- | :--- | :--- |
| P1 - Bloqueador | Sistema inoperante, crash contínuo ou corrupção de dados | Sim |
| P2 - Crítico | Quebra de funcionalidade core sem alternativa de contorno | Sim |
| P3 - Médio | Falha pontual com procedimento alternativo viável | Não (corrige no ciclo seguinte) |
| P4 - Cosmético | Desvios visuais leves, formatação ou textos | Não (corrige no ciclo seguinte) |

<!-- Requisitos obrigatórios para reporte técnico de não-conformidade formalizado pelo PO: (1) URL/endpoint exato afetado; (2) Payload ou parâmetros de requisição; (3) Passos determinísticos de reprodução; (4) Evidências técnicas completas (prints, gravações de tela e/ou logs de console e rede); e (5) Versão exata do navegador, sistema operacional e dispositivo/resolução testados. -->
{{REQUISITOS_EVIDENCIA_REPORTE_TECNICO}}

## 4. CLÁUSULA PÉTREA DE ACEITE TÁCITO (DEEMED ACCEPTANCE)
<!-- Decurso do prazo de 5 dias úteis sem relatório técnico estruturado resulta em aprovação tácita irrevogável e autorização imediata de faturamento. -->
{{CLAUSULA_ACEITE_TACITO}}

## 5. NÃO-INTERRUPÇÃO DO ACEITE TÁCITO POR INSTABILIDADE DE AMBIENTES/APIS DO CLIENTE
<!-- O prazo de 5 (cinco) dias úteis de homologação e a contagem de Aceite Tácito não são suspensos ou postergados por falhas, lentidão excessiva ou indisponibilidade em APIs legadas, sandboxes de ERP ou bancos de dados sob custódia do Cliente ou terceiros. A conformidade dos entregáveis da Contratada é comprovada de forma autônoma mediante suíte de testes automatizados com mocks/stubs no pipeline de CI/CD, liberando o respectivo faturamento do marco. -->
{{NAO_INTERRUPCAO_INSTABILIDADE_CLIENTE}}

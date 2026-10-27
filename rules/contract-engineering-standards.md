---
description: >-
  Normas de engenharia para anexos técnicos vinculantes de software. Impõe substantivação do escopo, não-escopo obrigatório, proibição de aceite subjetivo, aceite tácito (deemed acceptance em 5 dias), classificação binária de defeitos (P1/P2 vs P3/P4) e não-interrupção do relógio de aceite por instabilidade de APIs legadas do cliente.
trigger: model_decision
---

# NORMAS DE ENGENHARIA PARA ANEXOS TÉCNICOS VINCULANTES

1. **Substantivação do Escopo (Regra Anti-Ambiguidade):**
   - É terminantemente proibido redigir escopo com verbos vagos (ex.: "desenvolver telas", "otimizar sistema", "testar funcionalidades").
   - Todo item de escopo deve ser um substantivo auditável acompanhado de critérios verificáveis (ex.: "Interface Web responsiva para reconciliação financeira com filtros por data, status e exportação em formato CSV").

2. **Obrigatoriedade Taxativa do "Não-Escopo" (Out of Scope):**
   - O Anexo 1 (SOW) deve conter uma lista mínima obrigatória de exclusões expressas:
     a) Migração, higienização ou saneamento de bases de dados legadas do Cliente.
     b) Suporte a navegadores fora das 3 versões mais recentes de Chrome, Safari e Edge (exclusão expressa de IE/Legacy).
     c) Custos de faturamento de infraestrutura em nuvem (AWS/GCP/Azure) ou licenças de APIs de terceiros.
     d) Treinamento presencial de ponta a ponta ou suporte operacional de nível 1 a usuários finais.

3. **Inadmissibilidade de Aceite Subjetivo:**
   - Nenhum anexo pode permitir critérios subjetivos de aceitação (ex.: "layout agradável", "boa usabilidade").
   - A aprovação é estritamente vinculada ao atendimento dos critérios de aceite previamente acordados nos marcos (Milestones).

4. **Cláusula Pétrea de Aceite Tácito (Deemed Acceptance):**
   - Todo protocolo de homologação deve fixar prazo máximo de 5 (cinco) dias úteis para o Cliente homologar as entregas em ambiente de Staging.
   - Decorrido o prazo sem envio de relatório técnico circunstanciado de inconsistências, o marco é considerado homologado de forma irrevogável, autorizando a cobrança e o avanço de cronograma.

5. **Classificação Binária de Defeitos:**
   - Apenas falhas de severidade P1 (Bloqueador) ou P2 (Crítico sem contorno) impedem o aceite de um marco.
   - Inconsistências P3 (Médio com workaround) e P4 (Cosmético/Visual) geram aceite do marco com obrigação de correção na sprint seguinte, sem reter o faturamento.

6. **Não-Interrupção do Aceite Tácito por Instabilidade de Sistemas Legados do Cliente:**
   - O prazo de 5 (cinco) dias úteis de homologação e a contagem regressiva para o Aceite Tácito não são suspensos nem interrompidos em razão de instabilidade, latência excessiva, queda de rede ou indisponibilidade de APIs, sandboxes, ERPs ou bancos de dados sob custódia do Cliente ou de fornecedores por ele indicados.
   - Verificada a instabilidade externa imputável à infraestrutura do Cliente, a comprovação do aceite técnico do entregável da Contratada dar-se-á mediante apresentação de relatórios de testes automatizados com mocks/stubs simuladores devidamente aprovados no pipeline de CI/CD, liberando-se a respectiva cobrança financeira.

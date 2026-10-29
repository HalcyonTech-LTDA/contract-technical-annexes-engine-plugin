---
description: Aplicar exclusivamente durante a elaboração, revisão ou auditoria de anexos técnicos contratuais de software (SOW, RACI, Homologação, Change Request, Garantia e SLA).
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
     e) Desenvolvimento, publicação ou manutenção de aplicativos móveis nativos (iOS/Android), restringindo-se à aplicação Web responsiva;
     f) Custos de contratação, taxas transacionais e tarifas de intermediação de gateways de pagamento ou mensageria.

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

7. **Requisitos de Evidência Técnica e Consolidação Exclusiva pelo Product Owner:**
   - Todo reporte de inconsistência impeditiva (P1/P2) formulado pelo Cliente deve ser consolidado e formalizado exclusivamente pelo Product Owner titular (ou suplente indicado no Anexo 2) e conter obrigatoriamente: (1) URL/endpoint exato afetado; (2) Payload ou parâmetros de requisição utilizados; (3) Passos determinísticos para reprodução; (4) Evidências técnicas completas (prints, gravações de tela e/ou logs de console e de rede); e (5) Versão exata do navegador, sistema operacional e dispositivo/resolução testados. Apontamentos genéricos ou desprovidos destes requisitos não interrompem o prazo de homologação nem o Aceite Tácito.

8. **Janela Estrita de Reteste (Vedação de Reabertura de Escopo Homologado):**
   - Disponibilizada a correção de apontamento impeditivo (P1/P2) pela Contratada, abre-se janela de reteste de até 2 (dois) dias úteis, adstrita exclusivamente à validação do defeito corrigido. É expressamente vedada a reabertura de testes ou inclusão de novos apontamentos sobre fluxos, telas ou regras de negócio já homologados em rodadas anteriores.

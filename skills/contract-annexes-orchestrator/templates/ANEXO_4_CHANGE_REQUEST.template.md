# ANEXO 4 — POLÍTICA DE GESTÃO DE MUDANÇAS (CHANGE REQUEST — CR)

## 1. FATORES GERADORES DE MUDANÇA (CHANGE TRIGGERS) E PROIBIÇÃO DE COMANDOS INFORMAIS
<!-- Tipificação formal dos Fatores Geradores de Mudança (Change Triggers):
     1. Adição de novos fluxos, entidades ou integrações não previstos na SOW;
     2. Alteração de fluxos, telas ou regras de negócio já homologadas em marcos anteriores;
     3. Desvios, quebras de contrato ou mudanças unilaterais em APIs e sistemas legados fornecidos pelo cliente.
     Vedação estrita de solicitações via WhatsApp, Slack, Teams, e-mails informais ou discussões verbais. -->
{{FATORES_GERADORES_PROIBICAO_COMANDOS_INFORMAIS}}

## 2. PROCEDIMENTO DE ANÁLISE DE IMPACTO EM TRÊS EIXOS E PRINCÍPIO DA CONTINUIDADE
<!-- Todo pedido de alteração de escopo gera cálculo obrigatório nos três eixos: (1) Horas adicionais de engenharia por disciplina, (2) Dias de impacto no Caminho Crítico (CPM) e marcos do cronograma e (3) Custo financeiro baseado na taxa horária técnica contratual.
     Princípio da Continuidade do Escopo Corrente: Durante a análise ou tramitação de qualquer CR, a equipe de engenharia continuará executando rigorosamente o escopo contratado na SOW original, sem desvios ou paralisações. -->
{{PROCEDIMENTO_IMPACTO_TRES_EIXOS_E_CONTINUIDADE}}

## 3. PRAZOS DE DELIBERAÇÃO, VALIDADE E EFICÁCIA OPERACIONAL
<!-- Prazos mandatórios:
     - Prazo de deliberação: até 3 (três) dias úteis para o Cliente aprovar formalmente o impacto em custo e cronograma da CR;
     - Validade da estimativa técnica: 10 (dez) dias corridos a contar do seu envio formal. Decorrido o prazo sem assinatura do aditivo pelo Cliente, a CR considera-se automaticamente cancelada e arquivada sem ônus;
     - Eficácia operacional: Nenhuma alteração fora do escopo original é codificada ou entra em backlog de sprint sem o Aditivo Técnico de Mudança devidamente assinado por ambas as partes. -->
{{PRAZOS_VALIDADE_EFICACIA_OPERACIONAL}}

## 4. FORMULÁRIO PADRÃO DE SOLICITAÇÃO E ADITIVO TÉCNICO DE MUDANÇA (TERMO DE CR)
<!-- Formulário padronizado para preenchimento obrigatório em eventuais aditivos: -->
| Campo Cadastral / Técnico | Detalhamento da Solicitação de Mudança |
| :--- | :--- |
| **ID da Change Request** | CR-[A PREENCHER: Nº DA CR] |
| **Data da Solicitação** | [A PREENCHER: DATA DD/MM/AAAA] |
| **Solicitante Oficial** | [A PREENCHER: NOME DO PO DO CLIENTE] (Product Owner do Cliente) |
| **Módulo / Componente Afetado** | [A PREENCHER: MÓDULO/COMPONENTE AFETADO] |
| **Descrição Técnica da Mudança** | [A PREENCHER: DESCRIÇÃO TÉCNICA DETALHADA DA MUDANÇA] |
| **Justificativa de Negócio** | [A PREENCHER: JUSTIFICATIVA DE NEGÓCIO E IMPACTO] |
| **Memória de Cálculo (Horas por Disciplina)** | Frontend: [___]h \| Backend: [___]h \| QA: [___]h \| DevOps/Infra: [___]h — **Total: [___]h** |
| **Impacto no Cronograma (Caminho Crítico / CPM)** | +[___] dias úteis no cronograma global (Marcos afetados: [A PREENCHER]) |
| **Impacto Financeiro Total (R$)** | [___]h × R$ [TAXA_HORARIA_CONTRATUAL]/h = **R$ [A CALCULAR]** |
| **Condição de Faturamento da CR** | [A PREENCHER: CONDIÇÃO DE FATURAMENTO DA CR] |

### Termo de Aprovação e Assinatura Eletrônica do Aditivo de Mudança

As partes aprovam expressamente as alterações técnicas, de cronograma e financeiras acima descritas, que passam a integrar o contrato principal como aditivo vinculado.

| Pela CONTRATADA | Pelo CONTRATANTE (Cliente) |
| :--- | :--- |
| **Nome:** [NOME_RESPONSAVEL_CONTRATADA] | **Nome:** [NOME_PO_CLIENTE] |
| **Cargo:** [CARGO_RESPONSAVEL_CONTRATADA] | **Cargo:** Product Owner / Representante Legal |
| **Data / Assinatura:** ____________________ | **Data / Assinatura:** ____________________ |

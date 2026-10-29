# ANEXO 1 — DECLARAÇÃO DE TRABALHO (STATEMENT OF WORK — SOW)

## 1. OBJETO E ESCOPO FUNCIONAL DISCRIMINADO
<!-- Lista numerada de módulos e entregáveis técnicos inspecionáveis com critérios de aceite determinísticos. Proibido o uso de verbos soltos. -->
{{ESCOPO_FUNCIONAL_DISCRIMINADO}}

## 2. ESCOPO EXPRESSAMENTE NÃO CONTEMPLADO (OUT OF SCOPE)
<!-- Exclusões taxativas obrigatórias: migração/saneamento de dados legados, suporte a browsers legados, faturamento de infraestrutura em nuvem, treinamento presencial de ponta a ponta, desenvolvimento/publicação de aplicativos móveis nativos (iOS/Android) e custos/taxas de gateways de pagamento ou mensageria. -->
{{MATRIZ_NAO_ESCOPO}}

## 3. BASELINE ARQUITETURAL E REQUISITOS NÃO-FUNCIONAIS (NFRS)
<!-- Stack homologada, protocolos de rede, metas de concorrência, SLAs de performance p95/p99 e zoneamento de segurança. -->
{{BASELINE_ARQUITETURAL_NFRS}}

## 4. CRONOGRAMA, MODELO DE CONTRATAÇÃO E VINCULAÇÃO FINANCEIRA
<!-- O agente deve renderizar a estrutura correspondente ao modelo comercial identificado no Dossiê de Pré-Venda:
     - MODO A: Escopo Fechado (Fixed Price por Milestones)
     - MODO B: Squad Dedicada / Time & Materials (Capacidade, Sprints e Mensalidade)
     - MODO C: Fase 0 (Inception Técnica Paga) -->
{{ESTRUTURA_MODELO_CONTRATACAO}}

<!-- MODELO A (EXEMPLO DE RENDERIZAÇÃO: ESCOPO FECHADO / MILESTONES) -->
<!--
| Código | Marco de Entrega | Entregável Técnico Inspecionável | % Faturamento |
| :--- | :--- | :--- | :--- |
| M0 | Setup & Arquitetura Base | Repositório CI/CD ativo e staging configurado | 20% |
| M1 | Módulos Core | Entregáveis funcionais homologados em Staging | 30% |
| M2 | Integrações & Relatórios | APIs conectadas e painéis operacionais | 30% |
| M3 | Go-Live & Handover | Deploy em produção, smoke tests e entrega do código | 20% |
-->

<!-- MODELO B (EXEMPLO DE RENDERIZAÇÃO: SQUAD DEDICADA / TIME & MATERIALS) -->
<!--
| Papel / Perfil Técnico | Senioridade | Dedicação | Horas Estimadas / Mês | Valor Mensal |
| :--- | :--- | :--- | :--- | :--- |
| Tech Lead / Architect | Sênior | 50% | 80h | R$ ... |
| Full Stack Developer | Pleno / Sênior | 100% | 160h | R$ ... |
| QA Automation Engineer | Pleno | 50% | 80h | R$ ... |
-->

<!-- MODELO C (EXEMPLO DE RENDERIZAÇÃO: FASE 0 - INCEPTION TÉCNICA) -->
<!--
| Semana | Entregável Técnico da Inception | Critério de Aceite | Faturamento Vinculado |
| :--- | :--- | :--- | :--- |
| Sem 1-2 | Arquitetura, PoC de APIs e Modelo de Dados | Documento de Arquitetura e PoC validada | 50% |
| Sem 3-4 | Protótipo Alta Fidelidade e Backlog Refinado | Protótipo navegável aprovado e Backlog detalhado | 50% |
-->

## 5. PREMISSAS TÉCNICAS ESTRUTURAIS CONDICIONANTES
<!-- Premissas técnicas e operacionais sob custódia do Cliente ou de terceiros que condicionam diretamente o cronograma, dimensionamento e critérios de aceite da SOW:
     1. Latência e Performance de APIs de Terceiros: Tempo de resposta p95 inferior a 500ms em todas as rotas integradas;
     2. Estabilidade de Ambientes e Sandboxes Legadas: Disponibilidade e estabilidade contínua de sandboxes funcionais para testes de integração;
     3. Disponibilidade de Documentação Técnica: Disponibilidade de contratos de interface, documentação técnica e especificações OpenAPI/Swagger válidas e atualizadas. -->
{{PREMISSAS_TECNICAS_ESTRUTURAIS_CONDICIONANTES}}

## 6. PROPRIEDADE INTELECTUAL E LICENCIAMENTO DE ATIVOS PRÉ-EXISTENTES (FOREGROUND IP VS. BACKGROUND IP)
<!--
1. Condição Suspensiva de Titularidade (Foreground IP): A cessão patrimonial do código-fonte desenvolvido especificamente sob encomenda para o Cliente somente se aperfeiçoa após a quitação integral de 100% dos valores pactuados no contrato. Até lá, vigora apenas licença precária de homologação em Staging.
2. Reserva de Background IP (Aceleradores da Contratada): Bibliotecas internas, módulos genéricos de autenticação/infraestrutura (IaC), boilerplates, frameworks e ferramentas pré-existentes da software house permanecem de propriedade exclusiva da Contratada, concedendo-se ao Cliente licença de uso perpétua, não-exclusiva e intransferível embutida na solução entregue.
-->
{{CLAUSULA_PROPRIEDADE_INTELECTUAL_FOREGROUND_BACKGROUND}}

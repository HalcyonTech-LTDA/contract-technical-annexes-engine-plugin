# ANEXO 1 — ESCOPO TÉCNICO E DECLARAÇÃO DE TRABALHO (STATEMENT OF WORK - SOW)

**VINCULAÇÃO CONTRATUAL:** Instrumento Técnico Vinculante integrante do Contrato de Prestação de Serviços de Engenharia de Software celebrado entre **{{CONTRATANTE_RAZAO_SOCIAL}}** ("CONTRATANTE") e **{{CONTRATADA_RAZAO_SOCIAL}}** ("CONTRATADA").

---

## 1. OBJETO TÉCNICO E ARQUITETURA MACRO DA SOLUÇÃO

### 1.1 Descrição Substantiva da Solução
{{DESCRICAO_SUBSTANTIVA_SOLUCAO}}

### 1.2 Arquitetura de Referência e Topologia de Componentes
- **Frontend / Client Layer:** {{TOPOLOGIA_FRONTEND}}
- **Backend / Microservices Layer:** {{TOPOLOGIA_BACKEND}}
- **Camada de Persistência e Dados:** {{TOPOLOGIA_BANCO_DADOS}}
- **Autenticação, Autorização e Segurança:** {{TOPOLOGIA_SEGURANCA}}
- **Infraestrutura e Pipeline CI/CD:** {{TOPOLOGIA_INFRA_DEPLOY}}

---

## 2. ESCOPO DETALHADO POR MACRO-ÉPICOS E CRITÉRIOS DE ACEITE AUDITÁVEIS

> **REGRA DE ENGENHARIA ANTI-AMBIGUIDADE:** Todo item de escopo abaixo é definido estritamente por substantivos técnicos auditáveis e critérios de verificação objetivos.

### Macro-Épico 1: {{EPICO_1_TITULO_SUBSTANTIVO}}
- **Entregáveis Técnicos Auditáveis:**
  1. {{EPICO_1_ENTREGAVEL_1}}
  2. {{EPICO_1_ENTREGAVEL_2}}
  3. {{EPICO_1_ENTREGAVEL_3}}
- **Critérios de Aceite Verificáveis:**
  - [ ] {{EPICO_1_CRITERIO_1}}
  - [ ] {{EPICO_1_CRITERIO_2}}
  - [ ] {{EPICO_1_CRITERIO_3}}

### Macro-Épico 2: {{EPICO_2_TITULO_SUBSTANTIVO}}
- **Entregáveis Técnicos Auditáveis:**
  1. {{EPICO_2_ENTREGAVEL_1}}
  2. {{EPICO_2_ENTREGAVEL_2}}
- **Critérios de Aceite Verificáveis:**
  - [ ] {{EPICO_2_CRITERIO_1}}
  - [ ] {{EPICO_2_CRITERIO_2}}

### Macro-Épico 3: {{EPICO_3_TITULO_SUBSTANTIVO}}
- **Entregáveis Técnicos Auditáveis:**
  1. {{EPICO_3_ENTREGAVEL_1}}
  2. {{EPICO_3_ENTREGAVEL_2}}
- **Critérios de Aceite Verificáveis:**
  - [ ] {{EPICO_3_CRITERIO_1}}
  - [ ] {{EPICO_3_CRITERIO_2}}

### Macro-Épico 4: {{EPICO_4_TITULO_SUBSTANTIVO}}
- **Entregáveis Técnicos Auditáveis:**
  1. {{EPICO_4_ENTREGAVEL_1}}
  2. {{EPICO_4_ENTREGAVEL_2}}
- **Critérios de Aceite Verificáveis:**
  - [ ] {{EPICO_4_CRITERIO_1}}
  - [ ] {{EPICO_4_CRITERIO_2}}

### Macro-Épico 5: {{EPICO_5_TITULO_SUBSTANTIVO}}
- **Entregáveis Técnicos Auditáveis:**
  1. {{EPICO_5_ENTREGAVEL_1}}
  2. {{EPICO_5_ENTREGAVEL_2}}
- **Critérios de Aceite Verificáveis:**
  - [ ] {{EPICO_5_CRITERIO_1}}
  - [ ] {{EPICO_5_CRITERIO_2}}

---

## 3. MATRIZ TAXATIVA DE NÃO-ESCOPO (EXCLUSÕES CONTRATUAIS EXPRESSAS)

Ficam expressa e taxativamente excluídos deste escopo, não podendo ser exigidos da CONTRATADA sob qualquer pretexto:

1. **Migração, Limpeza e Saneamento de Dados:** Quaisquer atividades de higienização, desduplicação, saneamento, script de carga manual ou reconciliação de dados legados do CONTRATANTE. A responsabilidade por entregar dados íntegros e compatíveis é exclusiva do CONTRATANTE.
2. **Navegadores e Ambientes Descontinuados:** Suporte técnico ou testes de compatibilidade em versões de navegadores web fora das 3 (três) versões mais recentes de Google Chrome, Apple Safari e Microsoft Edge. Exclusão categórica de Internet Explorer ou versões legadas de navegadores móveis não atualizados.
3. **Custos de Infraestrutura em Nuvem e Licenciamento:** Todo e qualquer faturamento de consumo de computação em nuvem (AWS, GCP, Azure, Oracle Cloud), ferramentas SaaS, licenças de banco de dados, certificados SSL, contas de desenvolvedor Apple/Google e faturas de APIs pagas de terceiros (ex.: OpenAI, gateways de pagamento, biometria facial, SMS/WhatsApp).
4. **Treinamento Presencial e Suporte de Nível 1:** Treinamento presencial, condução de onboarding individual de usuários da ponta ou prestação de service desk Nível 1 a colaboradores ou clientes do CONTRATANTE. O escopo compreende apenas documentação técnica em Markdown e sessão única gravada de Handover Técnico aos multiplicadores indicados.
5. **Modificações Fora do Escopo sem CR:** Quaisquer integrações, regras de negócio ou telas não expressamente descritas na Seção 2 deste SOW exigem aditivo formal via Anexo 4 (Change Request).

---

## 4. MARCOS DE ENTREGA (MILESTONES) E CRONOGRAMA VINCULANTE

| Marco (Milestone) | Descrição do Pacote de Entrega | Prazo Estimado | Critério de Homologação Vinculado |
| :--- | :--- | :--- | :--- |
| **M0 — Inception Técnica & Baseline** | Configuração de CI/CD, repositório, arquitetura base e contratos de API | Semana {{SEMANA_M0}} | Checklist de Inception & Pipeline Verde |
| **M1 — Núcleo Transacional & Dados** | Camada de dados, autenticação e macro-épicos 1 e 2 | Semana {{SEMANA_M1}} | Homologação Staging conforme Anexo 3 |
| **M2 — Fluxos de Negócio & Integrações** | Telas operacionais e conexões com APIs externas pactuadas | Semana {{SEMANA_M2}} | Homologação Staging conforme Anexo 3 |
| **M3 — Conclusão Funcional & Regras** | Macro-épicos finais e validação de ponta a ponta | Semana {{SEMANA_M3}} | Homologação Staging conforme Anexo 3 |
| **M4 — Handover & Go-Live** | Deploy em Produção, testes de fumaça e documentação técnica | Semana {{SEMANA_M4}} | Termo de Encerramento e início da Garantia |

---

## 5. DISPOSIÇÕES FINAIS E ASSINATURAS TÉCNICAS

Este anexo técnico prevalece sobre qualquer correspondência comercial prévia ou proposta preliminar em caso de divergência técnica de escopo.

______________________________________
**{{CONTRATANTE_RESPONSAVEL_TECNICO}}**  
Líder Técnico do CONTRATANTE

______________________________________
**{{CONTRATADA_RESPONSAVEL_TECNICO}}**  
Líder Técnico da CONTRATADA

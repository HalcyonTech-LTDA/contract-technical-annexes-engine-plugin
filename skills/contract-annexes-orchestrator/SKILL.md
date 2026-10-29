---
name: contract-annexes-orchestrator
description: >-
  Orquestra a esteira agêntica (DAG) de engenharia para transformar o dossiê técnico de pré-venda (DOSSIE_TECNICO_PRE_PROPOSTA.md)
  nos 5 anexos técnicos vinculantes (SOW, RACI, Homologação, CR e SLA) e no Documento Mestre Unificado (ANEXO_TECNICO_MESTRE_CONTRATO.md).
---

# Contract Annexes Orchestrator Skill

Esta skill expõe o comando `/contract-annexes-orchestrator` e orienta o modelo orquestrador a executar o pipeline agêntico nativo de geração dos 5 anexos técnicos contratuais vinculantes para contratos de prestação de serviços de engenharia de software.

A inteligência de orquestração reside inteiramente nas instruções deste documento: o modelo orquestrador lê as dependências, analisa os pré-requisitos, faz a resolução segura de templates e aciona os subagentes especializados na ordem prescrita.

---

## Gatilhos e Invocação
- **Comando direto via Slash Command:** `/contract-annexes-orchestrator [caminho_do_dossie] [diretorio_saida]`
- **Invocação contextual por linguagem natural:** Sempre que o usuário solicitar gerar anexos contratuais de engenharia, minutas vinculantes, SOW, protocolo de homologação ou matriz RACI a partir de um dossiê técnico ou notas de discovery.

---

## Diretórios e Localização de Templates (Execução Global)
- **Localização dos Templates da Skill:** Os templates estruturais residem obrigatoriamente dentro da própria pasta da Skill:
  `skills/contract-annexes-orchestrator/templates/`
  - `ANEXO_1_SOW.template.md`
  - `ANEXO_2_RACI_PRE_REQUISITOS.template.md`
  - `ANEXO_3_PROTOCOLO_HOMOLOGACAO.template.md`
  - `ANEXO_4_CHANGE_REQUEST.template.md`
  - `ANEXO_5_GARANTIA_SLA.template.md`
- **Injeção de Templates:** O modelo orquestrador deve ler o conteúdo do template correspondente da pasta da skill e injetá-lo no prompt de execução do subagente redator.
- **Isolamento de Handoff Transitório:** O artefato intermediário de dados deve ser salvo em `{{output_dir}}/.scratch/normalized_project_baseline.json`. A pasta `.scratch/` é ignorada pelo controle de versão (`.gitignore`), garantindo que o diretório raiz de entrega `{{output_dir}}` permaneça limpo, contendo apenas os documentos finais.
- **Higienização Estrita de Saída (.md):** Todos os agentes redatores e o auditor cruzado são instruídos a remover integralmente os comentários HTML (`<!-- ... -->`) originários dos templates e assegurar que nenhum placeholder no formato `{{...}}` permaneça exposto nos documentos finais.

---

## Fluxo de Execução Obrigatório (DAG em Linguagem Natural)

```
[DOSSIE_TECNICO_PRE_PROPOSTA.md]
              │
              ▼ (Passo 1: Sequencial com Pre-Flight Check)
     [ingestion-normalizer] ──> [{{output_dir}}/.scratch/normalized_project_baseline.json]
              │
  ┌───────────┼───────────┬───────────┐ (Passo 2: Fan-Out Paralelo)
  ▼           ▼           ▼           ▼
[sow]       [raci]     [qa-acc]   [risk-sla]
  │           │           │           │
  └───────────┼───────────┴───────────┘ (Passo 3: Fan-In & Quadro Sinóptico)
              ▼
        [cross-auditor]
              │
              ▼
[{{output_dir}}/ANEXO_TECNICO_MESTRE_CONTRATO.md]
```

### Passo 1: Ingestão e Pre-Flight Check com Fallbacks (Sequencial)
1. Identifique o dossiê de entrada: por padrão `./DOSSIE_TECNICO_PRE_PROPOSTA.md` (ou o caminho fornecido pelo usuário) e o diretório de saída (padrão: `./anexos_contratuais`). Crie o subdiretório `{{output_dir}}/.scratch/`.
2. Execute o subagente `ingestion-normalizer` passando o dossiê de entrada.
3. **Avaliação da Barreira de Qualidade (Pre-Flight Check):**
   - **Bloqueio Estrito (`STATUS: BLOCKED_MISSING_PRECONDITIONS`):** Interrompa imediatamente a esteira SOMENTE se o dossiê omitir o escopo funcional mínimo estrutural ou a definição básica de arquitetura técnica. Notifique o usuário dos requisitos faltantes.
   - **Fallbacks Padrão Inteligentes:** Se faltarem variáveis comerciais secundárias, o normalizador NÃO aborta; injeta os defaults contratuais padrão da software house no JSON e registra a lista `applied_defaults`:
     - Janela de Homologação em Staging: `5 dias úteis`
     - SLA de Resposta do Cliente: `até 2 dias úteis de expediente comercial (16 horas úteis de expediente)`
     - Garantia Técnica: `60 dias corridos a contar do Aceite Definitivo ou Go-Live (o que ocorrer primeiro)`
     - Taxa Horária de CR: `[R$ VALOR_HORA_TECNICA_A_DEFINIR]`
     - PO do Cliente: `[NOME_E_CARGO_DO_PO_A_DESIGNAR]`
4. O subagente grava a baseline canônica em `{{output_dir}}/.scratch/normalized_project_baseline.json`.

### Passo 2: Redação Especializada dos Anexos (Fan-Out Paralelo)
Com a baseline aprovada em `.scratch/`, acione os subagentes redatores em paralelo injetando os templates de `skills/contract-annexes-orchestrator/templates/`:

1. **`sow-architect`** -> Redige `{{output_dir}}/ANEXO_1_SOW.md` com base em `skills/contract-annexes-orchestrator/templates/ANEXO_1_SOW.template.md`:
   - Substantivação do escopo (módulos entregáveis, zero ambiguidades).
   - Não-Escopo explícito e taxativo (migração de banco legado, browsers obsoletos, contas de terceiros, suporte presencial, apps móveis nativos e taxas transacionais de gateways/mensageria).
   - **Modelo de Contratação Dinâmico (Seção 4):**
     - *Modo A (Fixed Price por Milestones):* Marcos M0..Mn vinculados a entregáveis físicos e percentuais de faturamento.
     - *Modo B (Squad Dedicada / Time & Materials):* Tabela de capacidade técnica alocada (seniores/plenos), horas/mês e faturamento por capacidade.
     - *Modo C (Fase 0 / Inception Técnica Paga):* Cronograma ágil de discovery técnico, protótipo navegável, POC e backlog refinado.
   - **Premissas Técnicas Estruturais Condicionantes (Seção 5):** Latência de APIs terceiras < 500ms p95, estabilidade de sandboxes legadas e documentação Swagger válida.
   - **Propriedade Intelectual (Seção 6):**
     - *Foreground IP:* Titularidade suspensivamente vinculada à quitação de 100% de todas as faturas contratuais.
     - *Background IP:* Titularidade exclusiva da Contratada sobre frameworks, bibliotecas e aceleradores de infraestrutura (IaC) pré-existentes, concedendo ao Cliente licença de uso perpétua e não-exclusiva.
   - *Higienização:* Remoção de comentários HTML e resolução completa de placeholders.

2. **`client-governance-drafter`** -> Redige `{{output_dir}}/ANEXO_2_RACI_PRE_REQUISITOS.md` com base em `skills/contract-annexes-orchestrator/templates/ANEXO_2_RACI_PRE_REQUISITOS.template.md`:
   - Designação do Product Owner (PO) único do Cliente.
   - **Matriz RACI Bilateral (Seção 2):** Mapeamento formal R/A/C/I para os 7 eventos-chave de engenharia.
   - **Gate Zero / Marco Zero (Seção 3):** Condição precedente de eficácia do cronograma mediante assinatura mútua do Termo de Liberação Integral de Acessos e Ambientes.
   - **Schedule Freeze (Seção 4):** Atrasos do cliente > 2 dias úteis de expediente comercial (16h úteis) congelam e prorrogam o cronograma 1:1 sem ônus.
   - **Desmobilização e Standby (Seção 5):** Atrasos > 10 dias úteis autorizam desmobilização da equipe para outros projetos (janela de remobilização de 5 dias úteis sem mora). Standby contínuo faturado via Taxa de Standby da Squad (custo horário/diário proporcional integral dos profissionais retidos).
   - **Conformidade LGPD em Ambientes de Engenharia (Seção 6):** Cliente como Controlador e Contratada como Operadora técnica; vedação expressa ao fornecimento de dados reais de produção com dados pessoais (PII) sem anonimização irreversível prévia.
   - *Higienização:* Remoção de comentários HTML e resolução completa de placeholders.

3. **`acceptance-policy-drafter`** -> Redige `{{output_dir}}/ANEXO_3_PROTOCOLO_HOMOLOGACAO.md` com base em `skills/contract-annexes-orchestrator/templates/ANEXO_3_PROTOCOLO_HOMOLOGACAO.template.md`:
   - Homologação adstrita exclusivamente ao ambiente de Staging.
   - Janela de teste de 5 (cinco) dias úteis com **Janela de Reteste de até 2 (dois) dias úteis** adstrita exclusivamente à validação do defeito corrigido (sem reabertura de fluxos homologados).
   - Reportes aceitos e formalizados exclusivamente pelo PO titular ou suplente.
   - **Taxonomia P1-P4 e Evidência Técnica Expandida:** Retenção de faturamento restrita a P1/P2; falhas cosméticas P3/P4 não retêm aceite. Injeção obrigatória dos 5 requisitos de reporte técnico em `{{REQUISITOS_EVIDENCIA_REPORTE_TECNICO}}` (URL, payload, passos determinísticos de reprodução, logs/prints e versão de navegador, SO e resolução).
   - **Aceite Tácito (*Deemed Acceptance*):** Silêncio decorrido os 5 dias acarreta aprovação tácita irrevogável e liberação de faturamento.
   - **Resiliência a Legados do Cliente:** Quedas ou instabilidades de APIs ou sandboxes legadas do Cliente NÃO suspendem o relógio do aceite tácito; conformidade comprovada via testes automatizados/mocks no CI/CD.
   - *Higienização:* Remoção de comentários HTML e resolução completa de placeholders.

4. **`risk-maintenance-drafter`** -> Redige `{{output_dir}}/ANEXO_4_CHANGE_REQUEST.md` e `{{output_dir}}/ANEXO_5_GARANTIA_SLA.md` com base nos respectivos templates:
   - **Anexo 4:** Fatores geradores de mudança tipificados nos 3 gatilhos formais; princípio da continuidade do escopo corrente; deliberação em até 3 dias úteis pelo Cliente com validade de 10 dias corridos sob pena de cancelamento automático; Formulário Padrão de Solicitação e Aditivo de Mudança nos 3 eixos (Horas, Prazo e Custo); nulidade de canais informais; adaptação no Modo B.
   - **Anexo 5:** Garantia técnica de 60 dias a contar do Aceite Definitivo ou Go-Live (o que ocorrer primeiro) limitada a vícios ocultos do código autoral nos Modos A/B; exclusões expressas adicionais (erros operacionais de usuários e corrupção manual de BD); horário de suporte em dias úteis das 09h00 às 18h00 via canal oficial e SLA P3 de até 40h úteis; adaptação no Modo C para revisão técnica documental e de artefatos de 15 dias, sem SLA de produção.
   - *Higienização:* Remoção de comentários HTML e resolução completa de placeholders.

### Passo 3: Auditoria Cruzada e Compilação Mestre com Quadro Sinóptico (Fan-In)
1. Acione o subagente `cross-auditor` fornecendo `{{output_dir}}/.scratch/normalized_project_baseline.json` e os 5 anexos gerados.
2. O subagente audita harmonia técnica, consistência entre marcos e faturamento, conformidade ao modelo comercial, presença do Gate Zero, preenchimento da Matriz RACI bilateral de 7 eventos, Janela de Reteste de até 2 dias úteis, prazos de deliberação (3 dias) e Formulário Padrão de CR, marco inicial duplo da garantia e horário de atendimento de suporte (09h-18h), presença da Taxa de Standby da Squad, higienização de comentários HTML e eliminação de placeholders brutos.
3. Aprovada a auditoria, compila o arquivo **`{{output_dir}}/ANEXO_TECNICO_MESTRE_CONTRATO.md`**, iniciando com a **Seção 0 (Quadro Sinóptico de Variáveis Contratuais)** como espelho executivo para o contrato principal.

---

## Entrega Final ao Usuário
Apresente no chat:
1. Resumo executivo dos 5 anexos gerados e do Documento Mestre consolidado.
2. Tabela do Quadro Sinóptico de Variáveis Contratuais destacando os defaults que demandam ratificação comercial/jurídica.
3. Confirmação de higienização dos arquivos gerados (zero comentários HTML e zero placeholders expostos).
4. Caminho de todos os artefatos gerados em disco.

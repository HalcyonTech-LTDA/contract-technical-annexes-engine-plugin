---
name: contract-annexes-orchestrator
description: >-
  Orquestra a esteira agêntica (DAG) de engenharia para transformar o dossiê técnico de pré-venda (DOSSIE_TECNICO_PRE_PROPOSTA.md)
  nos 5 anexos técnicos vinculantes (SOW, RACI, Homologação, CR e SLA) e no Documento Mestre Unificado (ANEXO_TECNICO_MESTRE_CONTRATO.md).
---

# Contract Annexes Orchestrator Skill

Esta skill expõe o comando `/contract-generate-annexes` e orienta o modelo orquestrador a executar o pipeline agêntico de geração dos 5 anexos técnicos contratuais vinculantes para contratos de prestação de serviços de engenharia de software.

A inteligência de orquestração reside inteiramente nas instruções deste documento: o modelo orquestrador lê as dependências, analisa os pré-requisitos e aciona os subagentes especializados na ordem estrita abaixo.

---

## Gatilhos e Invocação
- **Comando direto via Slash Command:** `/contract-generate-annexes [caminho_do_dossie] [diretorio_saida]`
- **Invocação contextual por linguagem natural:** Sempre que o usuário solicitar gerar anexos contratuais de engenharia, minutas vinculantes, SOW, protocolo de homologação ou matriz RACI a partir de um dossiê técnico ou notas de discovery.

---

## Fluxo de Execução Obrigatório (DAG em Linguagem Natural)

```
[DOSSIE_TECNICO_PRE_PROPOSTA.md]
              │
              ▼ (Passo 1: Sequencial)
    [ingestion-normalizer]
              │
  ┌───────────┼───────────┬───────────┐ (Passo 2: Fan-Out Paralelo)
  ▼           ▼           ▼           ▼
[sow]       [raci]     [qa-acc]   [risk-sla]
  │           │           │           │
  └───────────┼───────────┴───────────┘ (Passo 3: Fan-In)
              ▼
       [cross-auditor]
              │
              ▼
[ANEXO_TECNICO_MESTRE_CONTRATO.md]
```

### Passo 1: Ingestão e Validação Prévia (Sequencial)
1. Identifique o dossiê de entrada: por padrão `./DOSSIE_TECNICO_PRE_PROPOSTA.md` (ou o caminho fornecido pelo usuário) e o diretório de saída (padrão: `./anexos_contratuais`).
2. Execute o subagente `ingestion-normalizer` passando o arquivo de entrada.
3. **Barreira de Qualidade (Gate 1):**
   - Se o subagente retornar `STATUS: BLOCKED_MISSING_PRECONDITIONS`, **interrompa a execução imediatamente** e apresente ao usuário os campos mandatórios ausentes (ex.: marcos de entrega inverificáveis, ausência de stack ou escopo vago).
   - Somente avance para o Passo 2 se a baseline estiver completa e validada.

### Passo 2: Redação Especializada dos Anexos (Fan-Out Paralelo)
Com a baseline normalizada aprovada, acione os subagentes redatores em paralelo para gerar os 5 anexos nos seus respectivos caminhos em disco:

1. **`sow-architect`** -> Redige `ANEXO_1_SOW.md` com base em `templates/ANEXO_1_SOW.template.md`:
   - Substantivação estrita do escopo (substantivos técnicos auditáveis, zero verbos soltos).
   - Lista taxativa de Não-Escopo (migração de banco legado, browsers legados, contas de nuvem/APIs e suporte presencial L1).
   - Tabela de Marcos (M0 a Mn) e percentuais de faturamento vinculados.
   - **Salvaguarda de IP:** Reserva expressa de Propriedade Intelectual subordinada à quitação de 100% de todas as faturas contratuais pactuadas e eventuais CRs.

2. **`client-governance-drafter`** -> Redige `ANEXO_2_RACI_PRE_REQUISITOS.md` com base em `templates/ANEXO_2_RACI_PRE_REQUISITOS.template.md`:
   - Nomeação obrigatória de Product Owner (PO) único do Cliente com poderes irrevogáveis.
   - Checklist prévio de credenciais, sandboxes funcionais e bases de teste anonimizadas (LGPD).
   - **Schedule Freeze:** Atrasos do cliente > 48h úteis congelam e prorrogam o cronograma na proporção de 1:1 sem penalidade à software house.
   - **Desmobilização e Standby:** Bloqueios > 10 dias úteis autorizam desmobilização da squad para outros projetos, com janela de 5 dias úteis para remobilização sem mora. Prontidão contínua forçada gera faturamento de Taxa de Standby da Squad.

3. **`acceptance-policy-drafter`** -> Redige `ANEXO_3_PROTOCOLO_HOMOLOGACAO.md` com base em `templates/ANEXO_3_PROTOCOLO_HOMOLOGACAO.template.md`:
   - Homologação restrita ao ambiente de Staging (proibição de testes locais ou em produção).
   - Janela máxima de 5 (cinco) dias úteis para testes do Cliente.
   - **Aceite Tácito (*Deemed Acceptance*):** Silêncio ou falta de relatório circunstanciado em 5 dias gera aprovação irrevogável e liberação imediata de faturamento.
   - **Taxonomia Binária:** Apenas falhas P1/P2 retêm faturamento; P3/P4 são aceitas com faturamento liberado e correção na sprint seguinte.
   - **Não-Interrupção por Queda Externa:** Instabilidade de ERPs/APIs legadas do Cliente NÃO suspende a contagem de 5 dias do Aceite Tácito; conformidade da Contratada é atestada via testes automatizados/mocks no CI/CD.

4. **`risk-maintenance-drafter`** -> Redige `ANEXO_4_CHANGE_REQUEST.md` e `ANEXO_5_GARANTIA_SLA.md` com base nos respectivos templates:
   - **Anexo 4:** Nulidade de pedidos via WhatsApp/Slack; análise de impacto obrigatória nos 3 eixos (Horas, Caminho Crítico e Custo); proibição de codificar sem aditivo assinado.
   - **Anexo 5:** Garantia de 60 dias adstrita a vícios ocultos do código autoral; exclusão taxativa de quebras em APIs de terceiros; tabela de SLA; extinção automática do suporte gratuito e transição obrigatória para contrato de AMS.

### Passo 3: Auditoria Cruzada e Compilação Mestre (Fan-In)
1. Acione o subagente `cross-auditor` fornecendo a baseline e os 5 anexos gerados.
2. O auditor inspecionará:
   - Rastreabilidade e sincronia dos marcos (M0, M1, M2...) entre SOW, Homologação e RACI.
   - Concordância exata da taxa horária de Change Request.
   - Eliminação de qualquer termo subjetivo remanescente.
   - Presença obrigatória de todas as salvaguardas (Reserva de IP, Desmobilização/Standby, Aceite Tácito, Não-Interrupção por Sandboxes do Cliente e Não-Escopo).
3. Estando tudo aprovado, o `cross-auditor` compilará o **`ANEXO_TECNICO_MESTRE_CONTRATO.md`**, contendo sumário executivo e os 5 anexos unificados prontos para assinatura digital.

---

## Entrega Final ao Usuário
Apresente no chat:
1. Resumo executivo dos 5 anexos e do Documento Mestre gerados.
2. Caminho de cada artefato gravado no diretório de saída.
3. Confirmação do status de conformidade da auditoria cruzada e das salvaguardas de proteção contratual.

---
name: contract-annexes-orchestrator
description: Orquestra a esteira agêntica (DAG) de engenharia para gerar os 5 anexos técnicos vinculantes de um contrato de software a partir de um dossiê técnico de pré-venda.
---

# Contract Annexes Orchestrator Skill

Esta skill expõe o comando `/contract-generate-annexes` e orquestra a execução sequencial e paralela (fan-out / fan-in) dos 6 subagentes do plugin.

## Gatilhos e Invocação
- Comando direto: `/contract-generate-annexes [caminho_do_dossie] [diretorio_saida]`
- Invocação contextual: sempre que o usuário solicitar gerar minutas contratuais técnicas, SOW, critérios de homologação ou anexos jurídicos de engenharia a partir de um documento de proposta ou discovery.

## Fluxo de Execução Orquestrado (DAG)

```
[DOSSIE_TECNICO_PRE_PROPOSTA.md]
              │
              ▼
    [ingestion-normalizer]
              │
  ┌───────────┼───────────┬───────────┐ (Fan-Out Paralelo)
  ▼           ▼           ▼           ▼
[sow]       [raci]     [qa-acc]   [risk-sla]
  │           │           │           │
  └───────────┼───────────┴───────────┘ (Fan-In)
              ▼
       [cross-auditor]
              │
              ▼
[ANEXO_TECNICO_MESTRE_CONTRATO.md]
```

## Instruções de Execução da Skill

1. **Parâmetros e Entradas:**
   - Obtenha o arquivo base: se o usuário não informar o caminho, busque por padrão `./DOSSIE_TECNICO_PRE_PROPOSTA.md` ou solicite o arquivo de entrada.
   - Defina o diretório de saída (padrão: `./anexos_contratuais`).

2. **Fase 1 — Normalização (Sequential):**
   - Invoque o subagente `ingestion-normalizer`.
   - Se o status retornado for `BLOCKED_MISSING_PRECONDITIONS`, interrompa a execução imediatamente e liste para o usuário os dados faltantes (ex.: ausência de marcos claros ou de stack técnica).

3. **Fase 2 — Redação Técnica Paralela (Fan-Out):**
   - Disponibilize o contexto normalizado e execute os seguintes subagentes:
     * `sow-architect` -> gera `ANEXO_1_SOW.md` com base em `templates/ANEXO_1_SOW.template.md`.
     * `client-governance-drafter` -> gera `ANEXO_2_RACI_PRE_REQUISITOS.md` com base em `templates/ANEXO_2_RACI_PRE_REQUISITOS.template.md`.
     * `acceptance-policy-drafter` -> gera `ANEXO_3_PROTOCOLO_HOMOLOGACAO.md` com base em `templates/ANEXO_3_PROTOCOLO_HOMOLOGACAO.template.md`.
     * `risk-maintenance-drafter` -> gera `ANEXO_4_CHANGE_REQUEST.md` e `ANEXO_5_GARANTIA_SLA.md` com base nos respectivos templates.

4. **Fase 3 — Auditoria Cruzada e Compilação (Fan-In):**
   - Invoque o subagente `cross-auditor` passando os 5 anexos gerados e a baseline.
   - O auditor verificará inconsistências de prazos, divergências nos códigos dos marcos (M0, M1, M2...), termos vagos, reserva de IP condicionada à quitação de 100%, desmobilização/standby e não-interrupção de aceite por instabilidade legada externa.
   - Em caso de aprovação, ele compilará o `ANEXO_TECNICO_MESTRE_CONTRATO.md` contendo todos os anexos encadeados, pronto para assinatura digital.

5. **Entrega Final:**
   - Exiba um resumo executivo no chat com a lista de arquivos salvos em disco e a confirmação de que os critérios de proteção (aceite tácito, schedule freeze, exclusões de não-escopo, reserva de IP e standby da squad) foram inseridos com sucesso.

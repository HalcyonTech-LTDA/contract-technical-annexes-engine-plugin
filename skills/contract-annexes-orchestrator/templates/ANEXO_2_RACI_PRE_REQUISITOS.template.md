# ANEXO 2 — MATRIZ DE PRÉ-REQUISITOS E RESPONSABILIDADES DO CLIENTE (RACI)

## 1. INTERLOCUTOR TÉCNICO OFICIAL (PRODUCT OWNER)
<!-- Nomeação do ponto focal do cliente com soberania irrevogável de aprovação. -->
{{INTERLOCUTOR_TECNICO_OFICIAL}}

## 2. ATIVOS, ACESSOS E CREDENCIAIS DE TERCEIROS
<!-- Sandboxes de ERP/APIs de terceiros com documentação estável e bases de dados anonimizadas (LGPD). -->
{{CHECKLIST_ATIVOS_ACESSOS_LGPD}}

## 3. SLA DE RESPOSTA E CLÁUSULA DE SCHEDULE FREEZE
<!-- Prazo máximo de 48h úteis para resolução de impedimentos pelo cliente sob pena de congelamento e prorrogação automática do cronograma global na proporção de 1:1, sem penalidades à software house. -->
{{CLAUSULA_SCHEDULE_FREEZE}}

## 4. PROTOCOLO DE DESMOBILIZAÇÃO, REMOBILIZAÇÃO E TAXA DE STANDBY DA SQUAD
<!-- Bloqueios ou pendências do Cliente superiores a 10 (dez) dias úteis autorizam a Contratada a desmobilizar e realocar a equipe em outros projetos produtivos. A retomada dos trabalhos exige janela de remobilização de até 5 (cinco) dias úteis sem mora. Caso o Cliente demande prontidão contínua e dedicação ociosa da equipe durante o bloqueio, incidirá a Taxa de Standby da Squad contratada. -->
{{PROTOCOLO_DESMOBILIZACAO_STANDBY}}

## 5. PROTEÇÃO DE DADOS E SEGURANÇA EM AMBIENTES NÃO-PRODUTIVOS (LGPD: CONTROLADOR VS. OPERADOR)
<!--
1. Papéis LGPD: O Cliente figura formalmente como CONTROLADOR dos dados pessoais e a Contratada atua estritamente como OPERADORA técnica dos serviços de engenharia.
2. Vedação de Dados Reais de Produção: É expressamente vedado ao Cliente fornecer dumps, backups ou cópias de bases de dados contendo dados pessoais reais (PII, CPFs, dados cadastrais, bancários, transacionais ou sensíveis de produção) para ambientes de Desenvolvimento, QA ou Staging sem prévia anonimização irreversível. Toda geração de massas sintéticas ou anonimização de dados prévia para testes é de responsabilidade técnica e jurídica exclusiva do Cliente (Controlador).
-->
{{PROTECAO_DADOS_LGPD_NAO_PRODUTIVOS}}

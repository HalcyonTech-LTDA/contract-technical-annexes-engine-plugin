# ANEXO 2 — MATRIZ DE PRÉ-REQUISITOS E RESPONSABILIDADES DO CLIENTE (RACI)

## 1. INTERLOCUTOR TÉCNICO OFICIAL (PRODUCT OWNER)
<!-- Nomeação do ponto focal do cliente com soberania irrevogável de aprovação. -->
{{INTERLOCUTOR_TECNICO_OFICIAL}}

## 2. MATRIZ RACI BILATERAL DE EVENTOS-CHAVE DE ENGENHARIA
<!-- Mapeamento formal de responsabilidades: R = Responsável pela Execução, A = Aprovador Final / Autoridade Decisória, C = Consultado, I = Informado. -->
| Evento-Chave de Engenharia | Contratada | Cliente (PO) | Detalhamento da Responsabilidade |
| :--- | :---: | :---: | :--- |
| Liberação de acessos, repositórios de código e credenciais cloud | C / I | R / A | Provisionamento integral de acessos, credenciais e sandboxes antes do início |
| Fornecimento de massa de dados anonimizada/sintética (LGPD) | C | R / A | Fornecimento exclusivo de bases desprovidas de dados pessoais reais |
| Esclarecimento de dúvidas técnicas e regras de negócio | C | R / A | Resposta formal no SLA de até 2 dias úteis de expediente comercial |
| Disponibilização de ambiente de homologação (Staging) e CI/CD | R / A | I | Manutenção do pipeline automatizado e deploy das entregas de marcos |
| Execução de testes de homologação na Janela de Inspeção | C / I | R | Testes formais dos critérios de aceite nos 5 dias úteis de janela |
| Aprovação formal de marcos ou reporte circunstanciado de inconsistências | I | R / A | Emissão do Termo de Aceite ou envio consolidado pelo PO titular |
| Implantação em Produção (Deploy) e Handover Técnico | R / A | C / I | Execução da virada técnica em produção e entrega de documentação |

## 3. ATIVOS, ACESSOS E CONDIÇÃO PRECEDENTE DE EFICÁCIA (GATE ZERO / MARCO ZERO)
<!-- Checklist de sandboxes de ERP/APIs de terceiros com documentação estável e bases de dados anonimizadas (LGPD).
     Condição Precedente de Eficácia do Cronograma (Gate Zero / Marco Zero): A contagem dos dias do cronograma de desenvolvimento só tem início a partir da assinatura mútua do "Termo de Liberação Integral de Acessos e Ambientes". -->
{{CHECKLIST_ATIVOS_ACESSOS_GATE_ZERO}}

## 4. SLA DE RESPOSTA DO CLIENTE E CLÁUSULA DE SCHEDULE FREEZE
<!-- Prazo máximo de resposta de até 2 (dois) dias úteis de expediente comercial (16 horas úteis de expediente) para resolução de impedimentos, dúvidas ou validações pelo cliente. Qualquer atraso superior a este prazo aciona o congelamento e prorrogação automática do cronograma global na proporção de 1:1, sem penalidades à Contratada. -->
{{CLAUSULA_SCHEDULE_FREEZE}}

## 5. PROTOCOLO DE DESMOBILIZAÇÃO, REMOBILIZAÇÃO E TAXA DE STANDBY DA SQUAD
<!-- Bloqueios ou pendências do Cliente superiores a 10 (dez) dias úteis autorizam a Contratada a desmobilizar e realocar a equipe em outros projetos produtivos. A retomada dos trabalhos exige janela de remobilização de até 5 (cinco) dias úteis sem mora. Caso o Cliente demande prontidão contínua e dedicação ociosa da equipe durante o bloqueio, incidirá a Taxa de Standby da Squad contratada. -->
{{PROTOCOLO_DESMOBILIZACAO_STANDBY}}

## 6. PROTEÇÃO DE DADOS E SEGURANÇA EM AMBIENTES NÃO-PRODUTIVOS (LGPD: CONTROLADOR VS. OPERADOR)
<!--
1. Papéis LGPD: O Cliente figura formalmente como CONTROLADOR dos dados pessoais e a Contratada atua estritamente como OPERADORA técnica dos serviços de engenharia.
2. Vedação de Dados Reais de Produção: É expressamente vedado ao Cliente fornecer dumps, backups ou cópias de bases de dados contendo dados pessoais reais (PII, CPFs, dados cadastrais, bancários, transacionais ou sensíveis de produção) para ambientes de Desenvolvimento, QA ou Staging sem prévia anonimização irreversível. Toda geração de massas sintéticas ou anonimização de dados prévia para testes é de responsabilidade técnica e jurídica exclusiva do Cliente (Controlador).
-->
{{PROTECAO_DADOS_LGPD_NAO_PRODUTIVOS}}

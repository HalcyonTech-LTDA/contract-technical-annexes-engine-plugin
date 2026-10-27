# ANEXO 2 — MATRIZ RACI E PRÉ-REQUISITOS TÉCNICOS DO CLIENTE

**VINCULAÇÃO CONTRATUAL:** Instrumento Técnico Vinculante integrante do Contrato de Prestação de Serviços de Engenharia de Software celebrado entre **{{CONTRATANTE_RAZAO_SOCIAL}}** ("CONTRATANTE") e **{{CONTRATADA_RAZAO_SOCIAL}}** ("CONTRATADA").

---

## 1. PREMISSA DA OBRIGAÇÃO BILATERAL E COOPERAÇÃO TÉCNICA

1. A execução do escopo contratado constitui **obrigação de meio**, cujo sucesso, aderência ao cronograma e estabilidade dependem estritamente da cooperação técnica ágil e ininterrupta do CONTRATANTE.
2. O CONTRATANTE obriga-se a disponibilizar tempestivamente os insumos, credenciais de acesso, ambientes de homologação (sandbox), documentações de APIs internas e validações de regras de negócio essenciais para a continuidade dos trabalhos da CONTRATADA.

---

## 2. MATRIZ DE RESPONSABILIDADES (RACI)

**Legenda:**
- **R (Responsible):** Quem executa a atividade diretamente.
- **A (Accountable):** Quem responde pelo resultado final e tem poder de aprovação.
- **C (Consulted):** Quem deve ser consultado e fornecer insumos técnicos.
- **I (Informed):** Quem deve ser notificado sobre o andamento e conclusão.

| Macro-Processo / Atividade de Engenharia | CONTRATADA (Software House) | CONTRATANTE (Cliente) | Terceiros / Provedores de API |
| :--- | :---: | :---: | :---: |
| **Arquitetura de Software e Modelagem Técnica** | **A / R** | C | I |
| **Desenvolvimento de Código-Fonte e Testes Unitários** | **A / R** | I | I |
| **Fornecimento de Ambientes Sandbox e Documentação de APIs Legadas** | C | **A / R** | C |
| **Concessão de Credenciais de Acesso (VPN, Repos, Cloud)** | I | **A / R** | - |
| **Validação Funcional e Esclarecimento de Regras de Negócio** | C | **A / R** | - |
| **Provisionamento e Custos de Infraestrutura em Nuvem** | C | **A / R** | R |
| **Homologação em Ambiente de Staging (UAT)** | C | **A / R** | - |
| **Aprovação Formal de Marcos (Milestones)** | I | **A / R** | - |
| **Disponibilidade e Resolução de Falhas de APIs Externas de Terceiros** | I | C | **A / R** |
| **Implantação em Produção (Deploy / Cutover)** | **A / R** | C | I |

---

## 3. PRÉ-REQUISITOS TÉCNICOS MANDATÓRIOS DO CONTRATANTE

O início das atividades de cada fase fica estritamente condicionado à entrega formal, pelo CONTRATANTE, dos seguintes insumos dentro dos prazos estipulados:

| Cód. | Pré-Requisito Técnico | Descrição e Requisitos Mínimos | Data Limite / Marco |
| :---: | :--- | :--- | :--- |
| **PR-01** | **Acessos e Credenciais:** | Liberação de acessos a repositórios, VPNs corporativas, chaves de API e contas de nuvem com privilégios adequados. | Até D+3 da assinatura |
| **PR-02** | **Ambiente Sandbox / Mock:** | Disponibilização de instâncias ativas de ERP/legados com endpoints estáveis e documentação OpenAPI/Swagger. | Até o início do Marco M1 |
| **PR-03** | **Amostra de Dados de Teste:** | Fornecimento de massa de dados anonimizada (conforme LGPD) para testes unitários e de integração. | Até o início do Marco M1 |
| **PR-04** | **Nomeação de SPOC Técnico:** | Designação formal de 1 (um) responsável técnico titular e 1 (um) suplente com autonomia decisória. | No ato de assinatura |
| **PR-05** | **Validação de Dúvidas de Negócio:** | Resposta formal a dúvidas de regra de negócio submetidas pela CONTRATADA em canal oficial em até 48 horas úteis. | Contínuo ao longo do projeto |

---

## 4. CLÁUSULA PÉTREA DE SCHEDULE FREEZE (CONGELAMENTO DE CRONOGRAMA)

1. **Gatilho de Acionamento:** Qualquer atraso superior a 2 (dois) dias úteis por parte do CONTRATANTE no cumprimento de pré-requisito técnico, na disponibilização de credenciais/sandboxes, ou na resposta a bloqueios técnicos críticos notificados aciona automaticamente o mecanismo de **Schedule Freeze**.
2. **Efeitos do Congelamento:**
   - O cronograma global de entregas da CONTRATADA é imediatamente pausado e estendido na proporção exata de dias de atraso incorridos pelo CONTRATANTE, acrescido de até 3 (três) dias úteis adicionais para remobilização e realignment da equipe de engenharia.
   - Durante o período de Schedule Freeze, **é vedada a imputação de qualquer penalidade, mora, retenção de pagamento ou aplicação de multas rescisórias/indenizatórias contra a CONTRATADA**.
   - Os custos operacionais de equipe alocada em espera decorrentes de bloqueios prolongados imputáveis ao CONTRATANTE superiores a 10 (dez) dias corridos serão faturados mediante taxa de Standby da Squad contratada.

---

## 5. PONTOS FOCAIS E CANAIS DE GOVERNANÇA (SPOC)

- **SPOC Técnico do CONTRATANTE:** {{CONTRATANTE_SPOC_NOME}} ({{CONTRATANTE_SPOC_EMAIL}})
- **SPOC Técnico da CONTRATADA:** {{CONTRATADA_SPOC_NOME}} ({{CONTRATADA_SPOC_EMAIL}})
- **Canal Oficial de Notificação de Bloqueios:** {{CANAL_OFICIAL_COMUNICACAO}}

______________________________________
**{{CONTRATANTE_RESPONSAVEL_TECNICO}}**  
Pelo CONTRATANTE

______________________________________
**{{CONTRATADA_RESPONSAVEL_TECNICO}}**  
Pela CONTRATADA

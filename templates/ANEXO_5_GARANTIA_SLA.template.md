# ANEXO 5 — TERMO DE GARANTIA TÉCNICA E NÍVEIS DE SERVIÇO (SLA)

**VINCULAÇÃO CONTRATUAL:** Instrumento Técnico Vinculante integrante do Contrato de Prestação de Serviços de Engenharia de Software celebrado entre **{{CONTRATANTE_RAZAO_SOCIAL}}** ("CONTRATANTE") e **{{CONTRATADA_RAZAO_SOCIAL}}** ("CONTRATADA").

---

## 1. ALCANCE E PRAZO DA GARANTIA TÉCNICA

1. A CONTRATADA assegura a garantia técnica de conformidade pelo prazo improrrogável de **{{PRAZO_GARANTIA_DIAS}} ({{PRAZO_GARANTIA_EXTENSO}}) dias corridos**, com início formal contado no primeiro dia útil subsequente à homologação final do Marco M4 (Go-Live / Handover).
2. **Objeto Estrito da Garantia:** A garantia restringe-se única e exclusivamente à correção de vícios ocultos (*bugs*) e defeitos funcionais de código desenvolvidos pela CONTRATADA que causem desconformidade em relação aos critérios de aceite expressamente homologados no **Anexo 1 (SOW)**.

---

## 2. EXCLUSÕES EXPRESSAS E TAXATIVAS DA GARANTIA TÉCNICA

Ficam taxativamente excluídas da garantia técnica, não cabendo qualquer obrigação de correção gratuita pela CONTRATADA, as ocorrências decorrentes de:

1. **Alterações e Instabilidades em APIs de Terceiros:** Descontinuação, alteração de contratos de API, indisponibilidade, *rate limits*, alteração de esquemas JSON/XML ou falhas em serviços providos por terceiros (ex.: bancos, ERPs legados, gateways de pagamento, OpenAI, redes sociais, mensageria).
2. **Intervenção ou Adulteração de Código por Terceiros:** Qualquer modificação, refatoração, merge ou alteração direta na base de código, no banco de dados ou nos pipelines CI/CD realizada por colaboradores do CONTRATANTE ou terceiros sem a anuência prévia e por escrito da CONTRATADA.
3. **Novas Demandas de Negócio e Mudança de Requisitos:** Solicitações de alteração de regras de negócio, novos fluxos de trabalho ou modificações em telas já homologadas (as quais devem ser processadas via Anexo 4 - Change Request).
4. **Infraestrutura em Nuvem e Servidores:** Quedas de instâncias, expiração de certificados SSL de responsabilidade do cliente, custos de escala, falta de provisionamento de recursos de computação ou restrições de rede/firewall corporativo do CONTRATANTE.
5. **Má Operação de Usuários:** Erros derivados de alimentação indevida de dados, corrupção provocada por importação manual de planilhas despadronizadas ou uso em desacordo com as instruções de uso.

---

## 3. NÍVEIS DE SERVIÇO (SLA) DURANTE O PERÍODO DE GARANTIA

Os chamados técnicos abertos pelo CONTRATANTE no canal oficial de suporte durante o período de garantia serão atendidos segundo os seguintes parâmetros de SLA:

| Severidade | Definição Operacional | Tempo de Primeira Resposta (TMR) | Tempo Alvo de Resolução / Solução de Contorno |
| :---: | :--- | :---: | :---: |
| **P1 — Bloqueador** | Sistema em produção inoperante para a totalidade dos usuários, perda irreversível de dados ou interrupção de faturamento/transação sem contorno. | **Até 2 horas úteis** | **Até 8 horas úteis** |
| **P2 — Crítico** | Funcionalidade essencial comprometida para grande volume de usuários sem alternativa viável de contorno temporário. | **Até 4 horas úteis** | **Até 16 horas úteis** |
| **P3 — Médio** | Falha pontual em rotina não-crítica com método de contorno (*workaround*) disponível documentado. | **Até 8 horas úteis** | **Até 3 dias úteis** |
| **P4 — Cosmético** | Inconsistência visual secundária ou erro gramatical sem prejuízo ao processamento de dados. | **Até 16 horas úteis** | **Tratado em release de conveniência** |

> **Horário de Atendimento Padrão:** Dias úteis, de segunda a sexta-feira, das 09h00 às 18h00 (horário de Brasília).

---

## 4. FRONTEIRA RÍGIDA DA GARANTIA VS. SUSTENTAÇÃO / AMS

1. Findo o prazo da garantia técnica estipulado na Seção 1, cessa integralmente a obrigação da CONTRATADA de realizar correções ou intervenções não remuneradas no ambiente do CONTRATANTE.
2. Qualquer suporte contínuo, monitoramento preventivo 24/7, evolução contínua, atendimento a novos incidentes pós-garantia ou atualização de bibliotecas de terceiros exigirá a formalização de um **Contrato Autônomo de Sustentação de Software (Application Management Services - AMS)** ou faturamento por Horas Avulsas sob demanda.

---

## 5. CLÁUSULA DE PERDA TOTAL DA GARANTIA

A garantia técnica extinguir-se-á imediatamente, de pleno direito, caso o CONTRATANTE:
- Realize commits na branch principal sem aprovação da CONTRATADA;
- Contrate terceiros para alterar a arquitetura ou o código-fonte;
- Inadimpla qualquer parcela de remuneração pactuada no Contrato Principal;
- Recuse-se a aplicar correções de segurança recomendadas pela CONTRATADA.

______________________________________
**{{CONTRATANTE_RESPONSAVEL_TECNICO}}**  
Pelo CONTRATANTE

______________________________________
**{{CONTRATADA_RESPONSAVEL_TECNICO}}**  
Pela CONTRATADA

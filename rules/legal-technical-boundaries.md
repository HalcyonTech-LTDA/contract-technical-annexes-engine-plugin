---
description: >-
  Fronteiras jurídico-técnicas e mitigação de responsabilidade para contratos de engenharia de software. Define separação de obrigações bilaterais, cláusula de Schedule Freeze com regras de desmobilização/standby, reserva de propriedade intelectual (IP) até quitação integral, e demarcação estrita entre garantia técnica (30-90 dias) e sustentação/AMS.
trigger: model_decision
---

# FRONTEIRAS JURÍDICO-TÉCNICAS E MITIGAÇÃO DE RESPONSABILIDADE

1. **Separação de Obrigações Bilaterais, Schedule Freeze e Protocolo de Desmobilização/Standby:**
   - O desenvolvimento de software é uma obrigação de meio com marcos pactuados sob premissa de cooperação técnica contínua do Cliente.
   - Atrasos imputáveis ao Cliente (demora no fornecimento de credenciais, sandboxes de ERP, amostras de dados anonimizadas ou validação de regras) superiores a 48h úteis acionam imediatamente a cláusula de **Schedule Freeze** (congelamento proporcional do prazo global na proporção de 1:1, sem incidência de penalidades ou multas à software house).
   - **Desmobilização e Remobilização:** Se o período de Schedule Freeze decorrente de pendência do Cliente ultrapassar 10 (dez) dias úteis, a Contratada adquire o direito de desmobilizar e realocar os profissionais da squad em outros projetos produtivos. A retomada dos trabalhos após o saneamento da pendência pelo Cliente exigirá uma janela de remobilização de até 5 (cinco) dias úteis sem penalidade. Caso o Cliente exija a retenção exclusiva e ociosa da squad durante o bloqueio, será faturada Taxa de Standby da Squad com base nas horas de prontidão forçada.

2. **Reserva de Domínio da Propriedade Intelectual (IP) Vinculada à Quitação Integral:**
   - A cessão definitiva, irrevogável e irretratável dos direitos patrimoniais de autor sobre o código-fonte desenvolvido, repositórios de versionamento, arquiteturas, documentações técnicas e artefatos executáveis fica expressamente subordinada à condição suspensiva de **quitação integral de 100% de todas as faturas, parcelas de marcos de entrega e eventuais Change Requests (CRs) pactuadas**.
   - Até a quitação financeira cumulada de todas as obrigações contratuais, o Cliente detém exclusivamente uma licença temporária, precária, não-exclusiva e revogável para fins estritos de homologação em ambiente de Staging. Fica terminantemente vedada a implantação em produção definitiva, cessão a terceiros, comercialização ou sublicenciamento do código sem a devida quitação financeira.

3. **Fronteira da Garantia vs. Sustentação:**
   - A garantia técnica (30 a 90 dias) restringe-se exclusivamente à correção de vícios ocultos do código desenvolvido pela software house.
   - Ficam expressamente excluídas da garantia falhas decorrentes de: instabilidades ou alterações contratuais em APIs externas de terceiros; intervenções no código por profissionais externos; e solicitações de novas regras de negócio.
   - Qualquer intervenção pós-garantia ou fora do escopo original exige contratação autônoma de sustentação (AMS) ou aditivo de Change Request (CR).

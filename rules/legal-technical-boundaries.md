---
description: Aplicar exclusivamente durante a elaboração, revisão ou auditoria de anexos técnicos contratuais de software (SOW, RACI, Homologação, Change Request, Garantia e SLA).
trigger: model_decision
---

# FRONTEIRAS JURÍDICO-TÉCNICAS E MITIGAÇÃO DE RESPONSABILIDADE

1. **Separação de Obrigações Bilaterais, Gate Zero, Schedule Freeze e Protocolo de Desmobilização/Standby:**
   - O desenvolvimento de software é uma obrigação de meio com marcos pactuados sob premissa de cooperação técnica contínua do Cliente.
   - **Condição Precedente de Eficácia do Cronograma (Gate Zero / Marco Zero):** A contagem dos dias do cronograma de desenvolvimento só tem início a partir da assinatura mútua do "Termo de Liberação Integral de Acessos e Ambientes", marco sem o qual nenhum prazo corre contra a Contratada.
   - Atrasos imputáveis ao Cliente (demora no fornecimento de credenciais, sandboxes de ERP, amostras de dados anonimizadas ou validação de regras) superiores a até 2 (dois) dias úteis de expediente comercial (16 horas úteis de expediente) acionam imediatamente a cláusula de **Schedule Freeze** (congelamento proporcional do prazo global na proporção de 1:1, sem incidência de penalidades ou multas à software house).
   - **Desmobilização e Remobilização:** Se o período de Schedule Freeze decorrente de pendência do Cliente ultrapassar 10 (dez) dias úteis, a Contratada adquire o direito de desmobilizar e realocar os profissionais da squad em outros projetos produtivos. A retomada dos trabalhos após o saneamento da pendência pelo Cliente exigirá uma janela de remobilização de até 5 (cinco) dias úteis sem penalidade. Caso o Cliente exija a retenção exclusiva e ociosa da squad durante o bloqueio, será faturada a **Taxa de Standby da Squad**, correspondente, por padrão, ao custo horário ou diário proporcional integral dos profissionais mantidos em prontidão forçada.

2. **Propriedade Intelectual e Licenciamento (Foreground IP vs. Background IP):**
   - **Condição Suspensiva de Titularidade (Foreground IP):** A cessão definitiva, irrevogável e irretratável dos direitos patrimoniais de autor sobre o código-fonte desenvolvido especificamente sob encomenda para o Cliente (Foreground IP) somente se aperfeiçoa e se transfere após a quitação integral de 100% de todas as faturas contratuais pactuadas, parcelas de marcos e eventuais Change Requests (CRs). Até a quitação financeira cumulada de todas as obrigações contratuais, o Cliente detém exclusivamente uma licença temporária, precária, não-exclusiva e revogável para fins estritos de homologação em ambiente de Staging. Fica terminantemente vedada a implantação em produção definitiva, cessão a terceiros, comercialização ou sublicenciamento do código sem a devida quitação.
   - **Reserva de Background IP (Aceleradores da Contratada):** Bibliotecas internas, módulos genéricos de autenticação/infraestrutura como código (IaC), boilerplates, frameworks, algoritmos proprietários e ferramentas pré-existentes da Contratada (Background IP) permanecem sob titularidade e propriedade intelectual exclusiva da Contratada, concedendo-se ao Cliente licença de uso perpétua, não-exclusiva e intransferível embutida exclusivamente na solução contratada entregue.

3. **Fronteira da Garantia vs. Sustentação:**
   - A garantia técnica (30 a 90 dias, padrão 60 dias corridos) vigora **a contar da assinatura do Termo de Aceite Definitivo ou da entrada em produção (Go-Live), o que ocorrer primeiro**, restringindo-se exclusivamente à correção de vícios ocultos do código autoral desenvolvido pela software house.
   - Ficam expressamente excluídas da garantia falhas decorrentes de:
     a) Instabilidades, quedas ou alterações unilaterais em APIs e serviços externos de terceiros;
     b) Intervenções no código-fonte ou ambiente por profissionais externos ou pelo Cliente;
     c) Erros operacionais provocados por usuários do Cliente;
     d) Corrupção de banco de dados decorrente de manipulação manual, execução de queries diretas ou scripts executados pelo Cliente;
     e) Solicitações de novas regras de negócio ou demandas evolutivas disfarçadas de falha.
   - **Regime de Suporte e SLAs durante a Garantia:** O suporte técnico opera exclusivamente em dias úteis das 09h00 às 18h00 via canal oficial formal exclusivo de chamados. Incidentes de severidade P3 (Médio com contorno) possuem SLA com tempo de resolução (TTR) de até 40 horas úteis.
   - Qualquer intervenção pós-garantia ou fora do escopo original exige contratação autônoma de sustentação (AMS) ou aditivo de Change Request (CR).

# ANEXO 3 — PROTOCOLO DE ACEITE, HOMOLOGAÇÃO E CRITÉRIOS DE QUALIDADE

**VINCULAÇÃO CONTRATUAL:** Instrumento Técnico Vinculante integrante do Contrato de Prestação de Serviços de Engenharia de Software celebrado entre **{{CONTRATANTE_RAZAO_SOCIAL}}** ("CONTRATANTE") e **{{CONTRATADA_RAZAO_SOCIAL}}** ("CONTRATADA").

---

## 1. PRINCÍPIO DA OBJETIVIDADE E INADMISSIBILIDADE DE CRITÉRIOS SUBJETIVOS

1. A aprovação de cada marco de entrega (Milestone) vincula-se exclusivamente ao atendimento dos critérios técnicos e funcionais objetivos previamente estabelecidos no **Anexo 1 (SOW)** e nas especificações técnicas validadas.
2. **Inadmissibilidade de Aceite Subjetivo:** É nula e desprovida de eficácia qualquer recusa de aceite fundamentada em impressões subjetivas, preferências visuais genéricas ou termos vagos (tais como "layout desagradável", "usabilidade não intuitiva", "não atendeu à expectativa estética"), salvo se houver desconformidade direta e comprovada contra wireframes/protótipos em alta fidelidade aprovados previamente por escrito.

---

## 2. PROCEDIMENTO E RITO DE HOMOLOGAÇÃO (UAT EM STAGING)

1. **Disponibilização:** A CONTRATADA notificará formalmente o CONTRATANTE via e-mail e canal oficial sobre a disponibilização da entrega em ambiente estável de **Staging / Homologação**, acompanhada das Notas de Release (*Release Notes*) e roteiro de testes dos critérios de aceite do marco.
2. **Janela de Testes:** O CONTRATANTE terá a prerrogativa de executar testes funcionais com seus usuários-chave durante a janela oficial de homologação.

---

## 3. CLÁUSULA PÉTREA DE ACEITE TÁCITO (DEEMED ACCEPTANCE)

> **REGRA FUNDAMENTAL DE EQUILÍBRIO CONTRATUAL:**
> 1. O CONTRATANTE dispõe de um prazo improrrogável de **5 (cinco) dias úteis**, contados a partir da data de notificação de disponibilização em Staging, para concluir os testes de homologação do marco.
> 2. Findo o prazo de 5 (cinco) dias úteis sem que o CONTRATANTE tenha:
>    a) Emitido o Termo Formal de Aceite do Marco; OU
>    b) Encaminhado um **Relatório Técnico Circunstanciado de Inconsistências** contendo evidências reproduzíveis de falhas impeditivas (P1 ou P2);
> 3. Operar-se-á, de pleno direito e para todos os fins jurídicos e contratuais, o **ACEITE TÁCITO E IRREVOGÁVEL (DEEMED ACCEPTANCE)** da entrega correspondente.
> 4. O Aceite Tácito autoriza imediata e automaticamente a **emissão da fatura/cobrança financeira do marco**, a liberação do código para o próximo ciclo e o avanço irrestrito do cronograma, ficando precluso o direito de retenção de pagamento.

---

## 4. MATRIZ BINÁRIA DE CLASSIFICAÇÃO DE DEFEITOS

A rejeição de um marco ou retenção de aceite é estritamente vinculada à severidade técnica objetiva das falhas identificadas:

| Severidade | Definição Técnica Objetiva | Impacto no Aceite do Marco | Prazo de Resolução |
| :---: | :--- | :---: | :---: |
| **P1 — Bloqueador (Blocker)** | Sistema indisponível em Staging, falha geral de banco de dados, corrupção irreparável de dados, ou impossibilidade total de autenticação/fluxo core sem qualquer meio de contorno. | **IMPEDE ACEITE** (Retém cobrança do marco) | Até 24 horas úteis |
| **P2 — Crítico (Critical)** | Funcionalidade central do marco inoperante sem método alternativo de contorno (*workaround*), inviabilizando a continuidade dos testes daquele módulo. | **IMPEDE ACEITE** (Retém cobrança do marco) | Até 48 horas úteis |
| **P3 — Médio (Major/Medium)** | Inconsistência pontual em funcionalidade secundária, cálculo auxiliar com desvio menor, ou falha funcional que possui contorno operacional simples documentado. | **NÃO IMPEDE ACEITE** (Aceite concedido; correção agendada para o ciclo seguinte) | Incluído no backlog da sprint seguinte |
| **P4 — Cosmético (Minor/Cosmetic)** | Desalinhamento visual milimétrico de CSS, texto de ajuda com erro de grafia, truncamento estético de label, ou detalhes visuais em navegadores suportados. | **NÃO IMPEDE ACEITE** (Aceite concedido; cobrança liberada; ajuste em refinamento) | Tratado em esteira de polimento contínuo |

---

## 5. REQUISITOS DO RELATÓRIO TÉCNICO DE INCONSISTÊNCIAS

Para que uma notificação de inconformidade seja válida e interrompa o prazo de aceite tácito, o CONTRATANTE deverá fornecer, dentro dos 5 dias úteis:
- Código da entrega / história de usuário avaliada.
- Passo a passo detalhado para reprodução exata da falha (*Steps to Reproduce*).
- Dados de entrada e credencial de teste utilizada.
- Comportamento esperado vs. comportamento real observado.
- Evidências técnicas (captura de tela com URL visível, gravação em vídeo ou logs do console do navegador).

Relatórios genéricos (ex.: *"sistema com muitos erros"*, *"não funciona"*) são expressamente ineficazes para afastar o Aceite Tácito.

______________________________________
**{{CONTRATANTE_RESPONSAVEL_TECNICO}}**  
Pelo CONTRATANTE

______________________________________
**{{CONTRATADA_RESPONSAVEL_TECNICO}}**  
Pela CONTRATADA

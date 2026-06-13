# C_blueprint_asis.md — Service Blueprint AS-IS
## Contratação do FIES pelo portal acesso.gov.br — MEC/FNDE

**Serviço:** Fundo de Financiamento Estudantil (FIES)  
**Canal principal:** Portal de Acesso Único ao Ensino Superior (acessounico.mec.gov.br/fies)  
**Órgão responsável:** Ministério da Educação (MEC) / Fundo Nacional de Desenvolvimento da Educação (FNDE)  
**Recorte temporal:** Operação vigente em 2025/2026 — Novo FIES (pós-2018) + FIES Social  

---

## Estrutura do Blueprint

O Service Blueprint AS-IS do FIES é organizado em **5 camadas horizontais**, separadas por **3 linhas divisórias**, e cobre **5 etapas sequenciais** da jornada do estudante.

---

## Camada 1 — Evidências Físicas

São os artefatos tangíveis (digitais ou físicos) que o estudante encontra em cada etapa e que atestam sua transição entre fases.

| Etapa 1: Inscrição | Etapa 2: Complementação | Etapa 3: Validação (CPSA) | Etapa 4: Formalização Bancária | Etapa 5: Renovação (Aditamentos) |
|---|---|---|---|---|
| Portal acessounico.mec.gov.br/fies | Painel FiesSeleção (tela de complementação) | Portais acadêmicos das IES / guichês físicos da CPSA | Agências Caixa ou BB / App FIES CAIXA | Portal SIFESWeb / SisFIES Aluno |
| Tela de login Gov.br | Tela de confirmação de dados | Guichê de atendimento da CPSA | Balcão bancário / tela do App FIES CAIXA | Tela de aditamento no SIFESWeb |
| Boletim do ENEM integrado | Proposta de Seguro Prestamista (digital) | DRI — Documento de Regularidade de Inscrição (físico ou digital) | Contrato de Financiamento / CCB assinado | DRM — Documento de Regularidade de Matrícula |
| Comprovante de Inscrição (PDF com chave de segurança) | Comprovante de Complementação (PDF) | Comprovantes físicos de renda e residência | Apólice do Seguro Prestamista | Guia mensal de pagamento (boleto digital) |
| E-mail automático de confirmação do MEC | — | Certificado de conclusão do Ensino Médio | Comprovante de abertura de conta corrente | Termo Aditivo físico (apenas em aditamentos Não Simplificados) |

---

## ─── Linha de Interação (visível ao estudante) ───

---

## Camada 2 — Ações do Cidadão (Frontstage — o que o estudante faz)

| Etapa 1: Inscrição | Etapa 2: Complementação | Etapa 3: Validação (CPSA) | Etapa 4: Formalização Bancária | Etapa 5: Renovação (Aditamentos) |
|---|---|---|---|---|
| Acessa o Portal de Acesso Único | Acessa o painel FiesSeleção após pré-seleção | Reúne documentos do grupo familiar | Comparece à agência bancária ou acessa o App FIES CAIXA | Realiza rematrícula semestral na IES |
| Faz login via Gov.br (conta Prata ou Ouro) | Confirma dados de matrícula | Envia documentos digitalmente ou comparece à CPSA | Abre conta corrente (se necessário) | Acessa SIFESWeb para confirmar aditamento |
| Preenche dados cadastrais e do grupo familiar | Escolhe percentual de financiamento | Assina o DRI (físico ou eletrônico) | Apresenta documentação e assina o contrato | Assina aditamento digital (Simplificado) ou retira DRM e vai ao banco (Não Simplificado) |
| Seleciona até 3 opções de curso/turno/IES | Seleciona seguradora do Seguro Prestamista | Aguarda análise e aprovação da CPSA | Formaliza adesão ao Seguro Prestamista | Paga mensalmente os encargos de evolução |
| Opta por concorrer ao FIES Social (se elegível) | Visualiza simulação de encargos mensais | — | — | — |

**Prazos críticos do cidadão:**
- Inscrição: 4 dias corridos (conforme edital semestral)
- Complementação: 5 dias corridos após pré-seleção (3 dias para Lista de Espera)
- Validação na CPSA: 5 dias úteis após complementação
- Formalização bancária: 10 dias a partir do 3º dia útil após validação da CPSA
- Confirmação do aditamento: 10 dias após solicitação da CPSA

---

## ─── Linha de Visibilidade (separação frontstage / backstage) ───

---

## Camada 3 — Frontstage (o que o estudante vê do serviço)

| Etapa 1: Inscrição | Etapa 2: Complementação | Etapa 3: Validação (CPSA) | Etapa 4: Formalização Bancária | Etapa 5: Renovação (Aditamentos) |
|---|---|---|---|---|
| Interface do Portal de Acesso Único e sistema FiesSeleção | Boletim de acompanhamento e painel de complementação | Atendimento presencial ou digital da CPSA da IES | Atendimento bancário (balcão ou app) | Interface do SIFESWeb ou SisFIES Aluno |
| Feedback de elegibilidade (liberação ou bloqueio de vagas FIES Social) | Simulação de encargos e percentual de financiamento | Solicitação de documentos e análise do funcionário da CPSA | Análise de crédito do fiador (quando aplicável) | Confirmação digital do aditamento (Simplificado) |
| Mensagem de confirmação de inscrição | Confirmação de complementação realizada | Entrega do DRI assinado | Entrega do contrato assinado / CCB | Entrega do DRM (Não Simplificado) |

---

## ─── Linha de Visibilidade Interna (separação backstage / suporte) ───

---

## Camada 4 — Backstage (o que acontece invisível ao estudante)

| Etapa 1: Inscrição | Etapa 2: Complementação | Etapa 3: Validação (CPSA) | Etapa 4: Formalização Bancária | Etapa 5: Renovação (Aditamentos) |
|---|---|---|---|---|
| Consulta automática ao INEP (notas ENEM via CPF) | Cálculo do percentual de financiamento e coparticipação | Funcionários da CPSA conferem documentos no SisFIES-Gestão | Gerente bancário insere proposta no sistema de crédito | CPSA inicia aditamento no SIFESWeb |
| Consulta ao CadÚnico (MDS/DATAPREV) para FIES Social | Aplicação das regras da Resolução CG-FIES nº 63/2025 (tetos e piso) | Validação de elegibilidade acadêmica e documental | Integração bancária com os dados do DRI | Verificação de aproveitamento acadêmico mínimo (75%) |
| Verificação de renda familiar per capita (limite: 3 SM) | Aplicação da reserva de 50% de vagas para FIES Social | Emissão do DRI no sistema e disponibilização ao banco | Emissão da apólice do Seguro Prestamista pela seguradora | Verificação periódica do CadÚnico para estudantes FIES Social |
| Aplicação das cotas (PPI, PCD, quilombola) | Reordenamento diário da nota de corte | Transmissão eletrônica dos dados do DRI ao agente financeiro | Processamento das garantias (FG-Fies ou fiança convencional/solidária) | Geração digital do DRM (Simplificado) ou emissão física (Não Simplificado) |

---

## ─── Linha de Interação Interna ───

---

## Camada 5 — Processos de Suporte (infraestrutura e sistemas)

| Etapa 1: Inscrição | Etapa 2: Complementação | Etapa 3: Validação (CPSA) | Etapa 4: Formalização Bancária | Etapa 5: Renovação (Aditamentos) |
|---|---|---|---|---|
| Sistema FiesSeleção (MEC/FNDE) | Motor de regras de classificação e nota de corte | SisFIES-Gestão / SIFESWeb (plataformas das IES) | SIFESWeb (Caixa) / Sistema bancário do Banco do Brasil | SIFESWeb / SisFIES Aluno |
| Portal Gov.br (autenticação) | Integração INEP (ENEM) para desempate | Portaria MEC nº 10/2010 (regras da CPSA) | Fundo Garantidor do FIES — FG-Fies (Lei nº 13.530/2017) | Resolução CG-FIES nº 39/2020 (encargos de manutenção) |
| Base INEP (notas ENEM) | Edital semestral do processo seletivo | Portaria MEC nº 167/2024 (isenção documental FIES Social) | Portaria MEC nº 230/2021 (dispensa DRI físico no banco) | Portaria MEC nº 230/2021 (dispensa DRM físico — Simplificado) |
| Base CadÚnico (MDS) | Resolução CG-FIES nº 58/2024 (FIES Social) | — | Seguradoras credenciadas (Mapfre, Wiz, Caixa Seguradora) | FNDE (repasse de CFT-E às mantenedoras) |
| Receita Federal (validação de CPFs) | Resolução CG-FIES nº 63/2025 (Compromisso FIES) | — | CETIP / Tesouro Nacional (custódia dos CFT-E) | — |

---

## ⚠ Fail Points Identificados

| # | Etapa | Camada | Descrição | Tipo |
|---|---|---|---|---|
| ⚠ 1 | Inscrição | Processos de Suporte | Instabilidade do Gov.br no 1º dia de inscrições — erros de timeout e desconexões | Sistema |
| ⚠ 2 | Inscrição | Processos de Suporte | Falha de sincronização CadÚnico-MEC: estudantes elegíveis ao FIES Social não são reconhecidos pelo CPF | Sistema |
| ⚠ 3 **[CRÍTICO]** | Validação (CPSA) | Frontstage + Backstage | **Funil da Documentação Comprobatória**: prazo de 5 dias úteis insuficiente para reunir comprovantes de renda informal; interpretação discricionária e inconsistente das portarias pelas CPSAs | Processo + Pessoas |
| ⚠ 4 | Formalização Bancária | Frontstage | Exigência ilegal de Seguro Prestamista impresso por agências bancárias, contrariando a Portaria MEC nº 230/2021 | Pessoas |
| ⚠ 5 | Formalização Bancária | Processos de Suporte | Instabilidade do SIFESWeb — ausência de processos formais de homologação de mudanças (Acórdão TCU nº 2513/2022) | Sistema |
| ⚠ 6 | Renovação (Aditamentos) | Processos de Suporte | Bloqueio administrativo por irregularidade fiscal da mantenedora: CFT-E suspenso impede aditamentos de todos os alunos da IES | Processo |
| ⚠ 7 | Renovação (Aditamentos) | Processos de Suporte | Conversão indevida de Aditamentos Simplificados em Não Simplificados por falha sistêmica do SIFESWeb | Sistema |

---

## Decisões do Grill-Me que fundamentam este blueprint

1. **Início da jornada no portal federal** (Rodada 1): O primeiro contato formal é no Portal de Acesso Único — divulgação externa (faculdades, redes sociais) é inferência, não mapeada no blueprint.
2. **Validações de elegibilidade como backstage** (Rodada 2): As checagens de ENEM e CadÚnico são processos de retaguarda; o frontstage registra apenas o resultado (liberação ou bloqueio de vagas).
3. **CPSA como fail point crítico** (Rodadas 3 e 8): Identificada como o gargalo de vidro da jornada — marcada com ⚠ [CRÍTICO] na camada de Frontstage + Backstage.
4. **Falhas bancárias segregadas em duas camadas** (Rodada 4): Instabilidade do SIFESWeb → Processos de Suporte; exigência ilegal de documentos físicos → Frontstage.
5. **Repasse CFT-E em Processos de Suporte** (Rodada 5): Invisível ao estudante, mas com fail point que bloqueia aditamentos de toda a IES quando há irregularidade fiscal da mantenedora.

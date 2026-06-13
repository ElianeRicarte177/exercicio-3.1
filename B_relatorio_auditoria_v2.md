# Segunda auditoria da v2 — Operação do FIES

Arquivo auditado: **B_relatorio_assistente_v2.md**.

## Veredito

A v2 **melhorou muito em cobertura operacional**, principalmente porque passou a incluir pré-jornada das mantenedoras, backstage, artefatos, normativos, fail points e renegociação. Mas ela **não está saneada**.

O problema central mudou de forma: a v1 parecia incompleta; a v2 parece completa demais. Ela incorporou muitos pontos da auditoria anterior, mas ainda faz afirmações operacionais fortes sem lastro suficiente, mantém contradições internas e, pior, declara no apêndice que certas falhas foram resolvidas enquanto o corpo do texto ainda as repete.

**Nota técnica:** **7,2/10**.  
Boa estrutura. Ainda frágil para uso como diagnóstico final sem revisão normativa.

---

## 1. Falhas do audit_v1 que foram efetivamente endereçadas

A v2 endereçou de forma satisfatória vários pontos que estavam fracos na versão anterior.

| Bloco auditado | Situação na v2 | Julgamento |
|---|---:|---|
| Seleção de até 3 cursos e pré-seleção em uma opção | Corrigido no fluxo de inscrição | **Saneado** |
| FIES Social como CadÚnico + renda até 0,5 SM | Corrigido | **Saneado** |
| Edital semestral e datas de 2026 | Incluiu Edital nº 3/2026, inscrições de 3 a 6/2 e complementação de 20 a 24/2 | **Saneado em essência** |
| Lista de espera | Passou a tratar prazo próprio de complementação | **Saneado** |
| App FIES CAIXA / SIFESWeb | Substituiu “aplicativo SIFES” por canais mais corretos | **Saneado parcialmente** |
| Pré-jornada da mantenedora | Criou fase específica de adesão/oferta de vagas | **Saneado** |
| Elegibilidade e-MEC/Sinaes | Incluída na pré-jornada | **Saneado** |
| Termo de adesão e termo de participação | Incluídos como artefatos | **Saneado** |
| Seguro prestamista | Entrou no fluxo de contratação | **Saneado parcialmente** |
| CFT-E em vez de LFT-E | Corrigido | **Saneado** |
| Desenrola Fies 2026 | Corrigiu a norma central: MP nº 1.355/2026 + Resolução CG-FIES nº 66/2026 | **Saneado quanto ao enquadramento normativo principal** |
| Fail points | A v2 criou eixo específico de gargalos | **Saneado parcialmente** |
| Artefatos físicos/digitais | Incluiu matriz de evidências | **Saneado parcialmente** |

A correção mais importante foi a do **Desenrola Fies 2026**. Ao contrário da outra v2 de atores, esta versão usa corretamente a **Resolução CG-FIES nº 66/2026** para o Desenrola Fies, voltado a contratos formalizados até 2017 em fase de amortização em 4/5/2026. A Caixa também confirma que as condições valem para contratos até 2017, com renegociação até 31/12/2026, e que a base normativa é a Resolução CG-FIES nº 66/2026.

---

## 2. Falhas que a v2 diz ter corrigido, mas não corrigiu de verdade

Aqui está o ponto crítico.

### 2.1. “Consulta síncrona automática” voltou no corpo do texto

No apêndice, a v2 diz que substituiu linguagem fraca como “APIs síncronas”, “processamento em lote” e “barramentos de integração” por termos mais auditáveis.

Mas no corpo do relatório ela afirma:

> “Para o FIES Social, o sistema do MEC faz uma consulta síncrona automática via CPF à base do Cadastro Único...”

Ou seja: a falha foi declarada como saneada, mas reaparece literalmente no eixo de backstage.

**Julgamento:** **não saneado**.

A redação correta deveria ser mais prudente:

> “O sistema verifica, a partir do CPF, a condição de inscrição ativa no CadÚnico e a renda per capita, conforme base de referência definida no edital. A forma técnica da integração — consulta em tempo real, lote, barramento ou outro mecanismo — deve ser descrita apenas se houver documentação técnica oficial.”

---

### 2.2. Contradição sobre coparticipação quando o curso excede o teto

A v2 acerta em um trecho ao dizer que, se a semestralidade superar o teto do Compromisso Fies, a faculdade **não poderá cobrar taxa ou complemento sobre o excedente**.

Mas a própria tabela da v2 diz, para o FIES Social:

> “Coparticipação apenas se exceder o teto.”

Isso é contraditório. A Resolução MEC nº 63/2025 é clara: se o encargo cobrado for superior ao Compromisso Fies, a remuneração da IES fica limitada ao teto, a coparticipação é calculada exclusivamente sobre esse valor, e é vedada a cobrança da diferença; a eventual diferença não gera obrigação adicional de pagamento ao estudante.

**Julgamento:** **falha grave remanescente**.

A frase “coparticipação sobre o excedente” deve ser eliminada. Ela reintroduz exatamente a distorção que a auditoria anterior tentava corrigir.

---

### 2.3. DRI/DRM: dispensa física no banco versus retirada física para agência

A v2 afirma, na etapa de manutenção, que no aditamento não simplificado o estudante “retira o DRM na CPSA e o apresenta à agência bancária”. Depois, no backstage, diz que a Portaria MEC nº 230/2021 dispensa o banco de exigir apresentação física do DRI/DRM, devendo usar informações eletrônicas registradas no sistema.

Isso é uma contradição operacional. Pode haver presença em agência para assinatura de termo aditivo em aditamento não simplificado; outra coisa é afirmar que o DRM deve ser fisicamente retirado e apresentado como exigência central.

**Julgamento:** **parcialmente saneado, mas ainda contraditório**.

Redação mais segura:

> “Nos aditamentos não simplificados, pode haver necessidade de comparecimento ao agente financeiro para formalização do termo aditivo, conforme o caso. A apresentação física de DRI/DRM ao banco deve ser tratada com cautela, pois a normatização posterior privilegiou a validação eletrônica dos dados registrados nos sistemas.”

---

### 2.4. Gov.br Prata/Ouro como requisito sistêmico é afirmação nova e mal sustentada

A v2 introduz um fail point dizendo que há rejeições porque contas Gov.br não atendem aos níveis “Prata” ou “Ouro” exigidos sistemicamente para autenticação no Portal de Acesso Único.

Isso é problemático. A página oficial do serviço “Obter Financiamento Estudantil” fala em conta Gov.br para inscrição, mas não sustenta, ali, a exigência específica de Prata/Ouro. Já a página oficial de serviço para ofertar vagas no Fies explicita “Bronze, Prata ou Ouro” para login integrado.

**Julgamento:** **falha nova**.

Pode existir atrito com credenciais Gov.br, mas afirmar “Prata/Ouro exigidos sistemicamente” sem prova específica é exagero. O fail point deve virar:

> “Possíveis atritos de autenticação Gov.br, recuperação de senha, validação de CPF e instabilidade de acesso nos dias de pico.”

---

### 2.5. Fail points baseados em denúncia genérica continuam frágeis

A v2 afirma “venda casada bancária” e diz que há denúncias recorrentes de condicionamento a capitalização, cartões ou seguros adicionais.

O problema não é mencionar o risco. O problema é não apresentar base auditável: quantidade de reclamações, período, origem, exemplos, banco, canal, filtro de relevância. No apêndice, a v2 diz que qualificou a venda casada como prática relatada em Reclame Aqui e Banco Central. Mas isso ainda não basta para um relatório técnico, porque Reclame Aqui não é evidência institucional e Banco Central exigiria consulta formal a dados ou relatórios.

**Julgamento:** **parcialmente saneado, mas ainda fraco**.

---

## 3. Falhas novas introduzidas pela v2

### 3.1. “Perda automática e definitiva do financiamento” por desempenho acadêmico

A v2 diz que aproveitamento inferior a 75% em dois aditamentos semestrais consecutivos “resulta na perda automática e definitiva do financiamento”.

Essa redação é perigosa. Pode haver regra de rendimento acadêmico, exigência de justificativa, validação pela CPSA e consequências para manutenção do financiamento, mas “automática e definitiva” é formulação maximalista. Se a norma admite avaliação, justificativa, exceção ou deliberação da CPSA, a palavra “automática” está errada.

**Julgamento:** **falha nova relevante**.

Trocar por:

> “pode impedir a renovação/aditamento do financiamento, conforme regras aplicáveis e deliberação da CPSA, observados os procedimentos normativos.”

---

### 3.2. “Erros graves de sincronização de webservice MDS/Dataprev-MEC”

A v2 fala em “erros graves de sincronização de webservice entre MDS/DATAPREV e MEC”.

Isso é tecnicamente forte demais. Se não há acórdão, relatório de incidente, nota técnica, base de chamados ou publicação oficial documentando esse tipo de erro, o correto é falar em **risco de divergência cadastral ou defasagem de atualização do CadÚnico**, não em erro grave de webservice.

**Julgamento:** **falha nova por excesso de certeza técnica**.

---

### 3.3. “Falhas sistêmicas convertem aditamentos simplificados em não simplificados”

A v2 diz que falhas sistêmicas no SIFESWeb convertem aditamentos simplificados em não simplificados por supostas inconsistências de renda do fiador.

Isso pode acontecer na prática, mas precisa de prova. Sem base documental, parece relato anedótico transformado em diagnóstico sistêmico.

**Julgamento:** **falha nova ou, no mínimo, inferência fraca**.

---

### 3.4. Seguradoras citadas nominalmente sem prova robusta

A v2 cita seguradoras como “Wiz, Mapfre ou Caixa Vida e Previdência” no fluxo de emissão do seguro prestamista. Depois, no apêndice, defende valores de seguro prestamista de R$ 12,50 e R$ 4,05 como tabela praticada por seguradoras credenciadas.

Se esses nomes e valores vierem de cartilha oficial da Caixa, edital ou tabela de seguradoras credenciadas, ótimo. Mas a v2 não apresenta a evidência no corpo nem em referência verificável ali. Do jeito que está, parece granularidade inventada ou colhida de fonte lateral.

**Julgamento:** **ponto novo aberto**.

---

### 3.5. “Canais digitais do Banco do Brasil” na formalização

A v2 inclui “canais digitais do Banco do Brasil” como touchpoint de formalização.

Atenção: para contratos novos do Novo FIES, a Caixa tem papel central como agente operador/financeiro. O Banco do Brasil aparece com muito mais clareza em contratos legados e renegociação. Se a v2 está descrevendo contratação nova 2026, precisa provar exatamente qual canal digital do BB formaliza novo contrato FIES. Senão, isso mistura regimes.

**Julgamento:** **falha nova por possível mistura de Novo FIES e contratos legados**.

---

## 4. Matriz de saneamento das falhas anteriores

### Itens 1 a 23 — erros factuais

| Item | Tema | Julgamento |
|---:|---|---|
| 1 | Seleção de cursos | **Saneado** |
| 2 | FIES Social / vulnerabilidade | **Saneado** |
| 3 | Prazo de 5 dias | **Saneado parcialmente** |
| 4 | Lista de espera / 3 dias úteis | **Saneado** |
| 5 | “Aplicativo SIFES” | **Saneado** |
| 6 | Conta obrigatória | **Parcial** — ainda precisa separar Caixa, BB, digital e agência |
| 7 | Garantia e fiador | **Parcial** |
| 8 | Renda do fiador | **Parcial** — precisa fonte oficial direta |
| 9 | SPC/Serasa | **Saneado** |
| 10 | Integração síncrona | **Não saneado** — reaparece no corpo |
| 11 | CadÚnico/Dataprev | **Parcial** |
| 12 | “Renda mínima” no FIES Social | **Saneado** |
| 13 | Financiamento 100% automático | **Saneado parcialmente** |
| 14 | Resolução 63/2025 | **Saneado** |
| 15 | Composição mensal FIES Social | **Não saneado** — contradição sobre excedente |
| 16–17 | Clicksign | **Parcial** — uso interno pode existir, mas deve sair do fluxo oficial |
| 18 | LFT-E/CFT-E | **Saneado** |
| 19 | Conta de custódia | **Parcial** |
| 20 | Portaria 10/2010 / FG-Fies | **Saneado** |
| 21 | Digitalização e DRI/DRM | **Parcial / contraditório** |
| 22 | Perenidade do FIES Social | **Parcial** — afirmação precisa fonte expressa |
| 23 | MP 1.355/2026 | **Saneado** |

### Itens 24 a 36 — omissões de bastidor

| Item | Tema | Julgamento |
|---:|---|---|
| 24 | Adesão/oferta pelas mantenedoras | **Saneado** |
| 25 | Elegibilidade e-MEC | **Saneado** |
| 26 | Grupos e limites de vagas | **Parcial** — percentuais por conceito precisam fonte direta |
| 27 | Desempate | **Saneado** |
| 28 | Lista de espera como subfluxo | **Saneado** |
| 29 | Vagas remanescentes | **Parcial** — mencionada pouco no corpo |
| 30 | CPSA completa | **Saneado parcialmente** |
| 31 | Seguro prestamista | **Parcial** |
| 32 | LGPD/governança de dados | **Insuficiente** — a v2 diz que saneou, mas o corpo não desenvolve de modo robusto |
| 33 | Canais de atendimento | **Insuficiente** — apêndice diz que incluiu, mas o corpo não mostra matriz clara de recuperação |
| 34 | Transparência/TCU | **Parcial** |
| 35 | Aditamentos especiais | **Parcial** |
| 36 | Amortização/cobrança pós-curso | **Parcial** — o foco ainda é manutenção inicial, não ciclo completo pós-curso |

### Itens 37 a 47 — evidências e normativos

| Item | Tema | Julgamento |
|---:|---|---|
| 37 | Edital semestral | **Saneado** |
| 38 | Termo de adesão | **Saneado** |
| 39 | Comprovante de pré-seleção | **Saneado** |
| 40 | Documentos PCD/cotas | **Parcial** |
| 41 | Boletim ENEM | **Saneado** |
| 42 | Termo de aceite percentual | **Parcial** |
| 43 | Instrumento bancário | **Saneado parcialmente** |
| 44 | CFT-E como evidência | **Parcial** |
| 45 | Acórdãos TCU | **Parcial** — citou, mas não trouxe referência verificável detalhada no corpo |
| 46 | Portaria MEC 209/2018 | **Apêndice diz que sim; corpo não demonstra bem** |
| 47 | Resolução 66/2026 | **Saneado** |

### Itens 48 a 62 — fail points

**Julgamento geral:** **parcialmente saneado**.

A v2 criou um eixo de gargalos, mas vários fail points continuam escritos como se fossem fatos consolidados, sem evidência mensurável. O próprio apêndice diz que todos os 15 fail points foram “devidamente documentados”, mas isso não é verdade: muitos foram apenas **nomeados**.

Os fail points mais bem tratados:

- prazo curto na CPSA;
- inconsistência documental de renda;
- instabilidade de atendimento das IES;
- risco de aditamento não simplificado;
- falhas de SIFESWeb apontadas por auditoria;
- venda casada como risco de atendimento bancário.

Os mais frágeis:

- exigência Gov.br Prata/Ouro;
- webservice MDS/Dataprev-MEC;
- venda casada como recorrência;
- conversão indevida automática de aditamento;
- bloqueio definitivo por rendimento acadêmico.

### Itens 63 a 72 — inferências fracas

| Item | Tema | Julgamento |
|---:|---|---|
| 63–66, 68 | Linguagem técnica de integração | **Não saneado integralmente** — “consulta síncrona” reaparece |
| 67 | Isenção de renda na CPSA | **Saneado em essência** |
| 69 | Valores do seguro | **Aberto** — precisa prova documental |
| 70 | Conversão em não simplificado | **Parcial / fraco** |
| 71 | Instabilidades Gov.br | **Parcial** |
| 72 | Venda casada | **Parcial / fraco** |

---

## 5. Pontos abertos que precisam ser corrigidos antes da versão final

### Prioridade 1 — corrigir erro material ou contradição

1. **Eliminar “consulta síncrona automática”** ou provar com documento técnico oficial.
2. **Eliminar “coparticipação se exceder o teto”**. A Resolução 63/2025 veda cobrança da diferença do estudante.
3. **Reescrever DRI/DRM em aditamento não simplificado**, separando comparecimento ao banco de exigência física de documento.
4. **Remover “perda automática e definitiva”** por desempenho acadêmico.
5. **Corrigir o fail point Gov.br Prata/Ouro** para não afirmar requisito não provado.

### Prioridade 2 — transformar relato em evidência

1. Venda casada: indicar fonte, período, número de reclamações ou tratar apenas como risco.
2. Falhas de SIFESWeb: vincular cada afirmação a achado de acórdão ou relatório.
3. Seguradoras e valores: incluir fonte oficial ou retirar nomes/valores.
4. Canais digitais do BB: provar ou restringir a contratos legados/renegociação.

### Prioridade 3 — melhorar o blueprint

1. Separar claramente:
   - Novo FIES;
   - FIES Social;
   - contratos legados;
   - renegociação/Desenrola.
2. Criar coluna “evidência” para cada etapa:
   - edital;
   - lei/resolução;
   - cartilha Caixa;
   - sistema;
   - evidência física/documental.
3. Criar coluna “grau de certeza”:
   - comprovado;
   - provável;
   - inferido;
   - anedótico;
   - não verificado.

---

## 6. Conclusão brutalmente honesta

A v2 **não é uma versão final saneada**. Ela é uma **boa versão intermediária**, mas com um defeito típico de relatório produzido por IA: o apêndice declara vitória sobre as falhas enquanto o corpo do texto ainda carrega resíduos dessas mesmas falhas.

O relatório está melhor, sim. Mas ainda há frases que, em auditoria séria, seriam atacadas imediatamente:

- “consulta síncrona automática”;
- “Prata/Ouro exigidos sistemicamente”;
- “coparticipação se exceder o teto”;
- “perda automática e definitiva”;
- “erros graves de webservice”;
- “denúncias recorrentes” sem base mensurável.

Minha recomendação: **não use esta v2 como produto final**. Use como base estrutural. A arquitetura está boa. O conteúdo precisa de uma rodada de saneamento jurídico-operacional, retirando excesso de certeza e amarrando cada afirmação sensível a fonte oficial.

# A_meta_prompt.md

## Meta-prompt — Deep Research da Operação do FIES para Service Blueprint AS-IS

Você é um assistente especializado em design de serviços públicos e pesquisa 
aplicada. Preciso que você elabore um **prompt detalhado** para ser usado em 
uma ferramenta de deep research (como Gemini Deep Research ou ChatGPT com 
busca ativada), com o objetivo de coletar informações estruturadas que 
sustentem a construção de um **Service Blueprint AS-IS** do seguinte serviço:

**Serviço:** Contratação do FIES (Fundo de Financiamento Estudantil)  
**Canal:** Portal acesso.gov.br / Portal FIES  
**Órgão responsável:** MEC / FNDE (Fundo Nacional de Desenvolvimento da Educação)  
**Recorte temporal:** Operação atual do FIES — modelo vigente a partir de 2018 
(FIES Social), com as regras em vigor em 2025/2026.

O prompt que você vai elaborar deve instruir o assistente de deep research a 
produzir uma pesquisa estruturada cobrindo obrigatoriamente os seguintes eixos:

### Eixo 1 — Jornada na ótica do estudante (Frontstage)
O prompt deve pedir uma descrição detalhada de cada etapa que o estudante 
percorre, desde o momento em que descobre o FIES até a liberação efetiva do 
crédito à instituição de ensino. A pesquisa deve mapear: o que o estudante 
faz, quais sistemas ele acessa, quais documentos apresenta, quais prazos 
enfrenta e em quais momentos pode desistir ou ser bloqueado.

### Eixo 2 — Processos de bastidor (Backstage)
O prompt deve exigir que a pesquisa vá além do que o estudante vê. Deve cobrir 
o que o FNDE, o MEC, os agentes financeiros (Caixa Econômica Federal, Banco do 
Brasil) e as instituições de ensino fazem nos bastidores: análise 
socioeconômica, verificação no CadÚnico, consulta ao INEP, formalização do 
aditamento contratual, repasse do crédito à IES, auditoria e controle.

### Eixo 3 — Evidências físicas de cada etapa
O prompt deve solicitar a identificação dos elementos tangíveis que o estudante 
encontra em cada etapa: telas do portal, e-mails de confirmação, documentos 
físicos exigidos, contratos assinados, comprovantes, notificações, filas 
presenciais (quando houver) e qualquer outro artefato que marque a passagem de 
uma etapa para a próxima.

### Eixo 4 — Normativos aplicáveis
O prompt deve pedir que a pesquisa identifique as leis, portarias, resoluções 
e instruções normativas que regem cada etapa da jornada — com citação de número 
e ano. Exemplos esperados: Lei 10.260/2001 (lei do FIES), Portaria MEC 
21/2015, Resolução CD/FNDE que define os critérios de seleção, normativo sobre 
carência e amortização.

### Eixo 5 — Fail points e gargalos conhecidos
O prompt deve exigir uma seção específica sobre os pontos de falha do serviço: 
onde o sistema trava, onde os dados não batem entre bases (CadÚnico, INEP, 
Receita Federal), quais etapas concentram mais abandono, onde os prazos são 
sistematicamente perdidos, quais reclamações recorrentes aparecem em portais 
como Reclame Aqui e relatórios de controle (TCU, CGU).

### Formato de saída esperado
O prompt que você elaborar deve instruir o assistente de deep research a 
entregar a resposta em formato estruturado: seções nomeadas por eixo, com 
subtópicos por etapa da jornada, citando fontes verificáveis (URLs de portais 
oficiais, PDFs de normativos, relatórios de auditoria). Prosa livre sem 
estrutura não é aceitável.

### Contexto adicional
Como referência, já possuo um mapa de atores do FIES produzido no exercício 
anterior, que identificou 29 atores distribuídos em 6 camadas sequenciais 
(demanda, acesso/triagem, análise/habilitação, contratação, execução/controle, 
encerramento) e 2 camadas transversais (infraestrutura de TI e 
governança/controle). O prompt de deep research deve ser compatível com esse 
mapeamento — ou seja, os processos de bastidor identificados devem poder ser 
associados aos atores já mapeados.
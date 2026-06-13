# C_grill_transcript.md — Sessão Grill-Me: Service Blueprint AS-IS do FIES

**Serviço:** Contratação do FIES (Fundo de Financiamento Estudantil) pelo portal acesso.gov.br — MEC/FNDE  
**Data:** 12/06/2026  
**Metodologia:** Sessão de entrevista adversarial (grill-me) — uma pergunta por vez  

---

## Rodada 1

**[Claude]** No Service Blueprint do FIES, a jornada começa antes do estudante acessar o portal. Considerando a pesquisa da Parte B, qual é o **primeiro contato real** do estudante com o serviço — e esse contato acontece pelo portal do MEC, por divulgação da faculdade, por redes sociais, ou por outro canal? Você consegue afirmar isso com base na pesquisa ou é uma inferência?

**[Eli]** Com base nos dados de diagnóstico operacional analisados, o primeiro contato real e formal do estudante com o FIES ocorre de maneira digital, por meio do Portal de Acesso Único ao Ensino Superior do MEC (acessounico.mec.gov.br/fies) ou pelo aplicativo oficial Jornada do Estudante, que funcionam como os ambientes centralizados para consulta de cronogramas, requisitos e início de inscrição.

Afirmar que o contato inicial ocorre por meio de divulgação da faculdade, redes sociais ou outros canais de mídia externa é uma inferência. Os normativos regulamentares do FIES, os editais semestrais e os manuais operacionais dos agentes financeiros não monitoram, registram ou estabelecem nenhuma etapa oficial de atração ou descoberta fora do ecossistema de portais integrados do Governo Federal. Embora campanhas publicitárias de faculdades privadas e discussões em redes sociais influenciem a intenção do candidato, a jornada técnica do Service Blueprint (no âmbito de interações e frontstage) inicia-se, factualmente, quando o usuário realiza o login unificado e inicia a inscrição nas plataformas do Ministério da Educação.

---

## Rodada 2

**[Claude]** Na etapa de inscrição, o estudante preenche dados do grupo familiar e escolhe até 3 opções de curso. Mas antes disso, o sistema faz verificações automáticas de elegibilidade — nota do ENEM, CadÚnico, renda. Do ponto de vista do **frontstage** (o que o estudante vê), essas verificações são transparentes ou invisíveis? O estudante recebe algum feedback em tempo real quando é bloqueado — por exemplo, se sua nota do ENEM for insuficiente ou se seu CPF não estiver no CadÚnico — ou só descobre o bloqueio depois de tentar submeter a inscrição?

**[Eli]** Com base no mapeamento operacional e normativo do FIES, é possível analisar o nível de visibilidade dessas validações dividindo o que é um fato comprovado pelos manuais e editais oficiais do que é uma inferência sobre o comportamento em tempo real da interface (UI/UX):

**O que é Fato Comprovado (Backstage e Regras do Sistema)**

- **Consulta ao CadÚnico:** A checagem da base de dados do Cadastro Único (CadÚnico) para o FIES Social é um processo automatizado de bastidor. O sistema realiza essa consulta automaticamente a partir do CPF do candidato no momento em que ele inicia a sua inscrição no processo seletivo.
- **Cálculo da Renda Familiar:** O estudante é obrigado a preencher ativamente os dados cadastrais, CPFs e os rendimentos brutos mensais de cada membro do seu grupo familiar. O sistema utiliza esses dados fornecidos para calcular internamente a renda familiar per capita e avaliar se o perfil atende aos critérios de elegibilidade do programa.
- **Uso dos Dados para Bloqueio de Modos de Vaga:** As verificações tornam-se transparentes (visíveis) para o candidato à medida que o resultado dessas consultas de bastidor dita o que ele pode ou não selecionar no portal. Se o cruzamento automático do CPF não identificar registro ativo no CadÚnico ou se a renda calculada for incompatível, o estudante fica impedido de optar e concorrer às vagas reservadas ao FIES Social.

**O que é Inferência (Frontstage e Comportamento da Interface)**

- **O Momento Exato do Feedback:** Afirmar se o estudante recebe um impedimento visual imediato (como um alerta em vermelho na tela no exato instante em que digita um dado incompatível) ou se ele só descobre o bloqueio ao tentar avançar de etapa ou submeter o formulário final é uma inferência.
- **Comportamento com a Nota do ENEM:** O sistema FiesSeleção exige o login unificado do Gov.br para puxar o histórico de notas do candidato. Embora o edital determine que o candidato que não cumpra os requisitos mínimos de nota do ENEM não possa se inscrever, as instruções passo a passo oficiais não detalham se o sistema exibe uma mensagem de bloqueio imediatamente após o login do Gov.br ou se a validação impede a escolha de opções de curso na etapa seguinte.

**Resumo para o Service Blueprint:** No mapa de processos, o mais seguro é registrar essas validações automáticas (ENEM e CadÚnico) como processos de retaguarda (backstage) que ocorrem de forma integrada no momento do login e preenchimento inicial. O feedback no frontstage deve ser mapeado como a liberação ou bloqueio das opções de concorrência (ampla concorrência vs. vagas reservadas do FIES Social), pois detalhar alertas de campo específicos em tempo real seria uma suposição de design não documentada nos manuais oficiais.

---

## Rodada 3

**[Claude]** A etapa de validação na CPSA da IES é o único momento em que a jornada sai do ecossistema digital federal e vai para dentro da faculdade. Com base na sua pesquisa, essa etapa é um **fail point crítico** ou um ponto de transição normal? Quais são as duas falhas mais graves que você identificou nessa etapa — e para cada uma, você consegue dizer se é um problema de **processo** (regra mal desenhada), de **sistema** (tecnologia que falha), ou de **pessoas** (interpretação inconsistente)?

**[Eli]** A etapa de validação na CPSA da instituição de ensino é, de forma incontestável, um fail point crítico na jornada do FIES, e não um mero ponto de transição normal. A criticidade desse momento reside no fato de que ele atua como um funil burocrático decisivo: o candidato tem um prazo curtíssimo (apenas 5 dias úteis) para comprovar documentalmente todas as informações declaradas na inscrição, sob a penalidade de perder a vaga de forma definitiva caso haja qualquer inconsistência ou decurso de tempo.

Com base no diagnóstico operacional, as duas falhas mais graves identificadas nesta etapa são:

**Falha 1: Indeferimentos equivocados por falha de avaliação da comissão**

- **O que acontece:** Os membros da CPSA frequentemente rejeitam inscrições de estudantes legítimos e que cumprem todos os requisitos do programa. Ocorre o indeferimento incorreto de documentos de comprovação de renda informal, declarações de desemprego ou composições de grupo familiar por falta de alinhamento técnico.
- **Classificação:** Problema de **Pessoas** (interpretação inconsistente). Isso acontece porque os membros das CPSAs de diferentes faculdades privadas não recebem treinamento adequado ou padronizado por parte do MEC/FNDE para aplicar os critérios das portarias, gerando decisões altamente subjetivas, arbitrárias e inconsistentes entre as instituições.

**Falha 2: O gargalo da comprovação de renda informal sob o prazo de 5 dias úteis**

- **O que acontece:** O estudante é obrigado a reunir uma lista exaustiva e complexa de documentos de identificação, residência e rendimentos de todas as pessoas que residem ou compartilham despesas na mesma casa. Reunir essa papelada em apenas 5 dias úteis é um gargalo operacional imenso, especialmente para famílias de baixa renda que vivem de trabalho informal.
- **Classificação:** Problema de **Processo** (regra mal desenhada). O fluxo do serviço é excessivamente rígido: ele não prevê de maneira automatizada um prazo de carência ou uma fase de saneamento preventivo de pendências para que o aluno possa retificar erros simples antes de ter sua inscrição sumariamente cancelada.

---

## Rodada 4

**[Claude]** Na formalização bancária, o estudante vai à Caixa ou ao Banco do Brasil assinar o contrato. A pesquisa identificou que o TCU apontou falhas graves no SIFESWeb e práticas abusivas nas agências. Para o blueprint, preciso que você **decida**: essas falhas bancárias devem ser mapeadas como fail points na camada de **Processos de Suporte** (problema de sistema/TI) ou na camada de **Frontstage** (problema que o estudante experimenta diretamente no balcão)? Justifique sua escolha — e cite pelo menos uma falha concreta de cada camada.

**[Eli]** Para construir um Service Blueprint rigoroso e funcional, estas falhas devem ser mapeadas de forma segregada em duas camadas distintas, dependendo de onde o atrito se manifesta visualmente para o estudante. A divisão correta para o diagrama é distribuir os problemas de sistema na camada de **Processos de Suporte** e os desvios de atendimento na camada de **Frontstage**.

**Justificativa da Escolha**

O Service Blueprint é um mapa de processos cuja principal utilidade é revelar a relação de causa e efeito entre os bastidores e a experiência do usuário. Se você mapear a instabilidade do SIFESWeb no Frontstage, o blueprint apenas registrará que "o estudante esperou muito no balcão", sem apontar a causa técnica. Se você mapear a conduta do gerente no Processo de Suporte, perderá a visibilidade do impacto emocional e do tempo de espera do cliente na agência.

**Falha Concreta na Camada de Processos de Suporte (Problema de TI/Sistemas)**

- **A falha:** A ausência de processos formais e estruturados para registrar, avaliar e homologar as atualizações e mudanças no sistema SIFESWeb mantido pelo agente operador (Acórdão TCU nº 2513/2022).
- **O impacto no Blueprint:** Essa falha de governança de TI gera bugs de processamento na retaguarda, indisponibilidade temporária de rede e atrasos na transmissão dos lotes de dados dos aditamentos, sem que o desenvolvedor consiga rastrear ou corrigir o erro de forma ágil.

**Falha Concreta na Camada de Frontstage (Problema no Balcão/Interação Direta)**

- **A falha:** Exigência ilegal e desnecessária de apresentação física da proposta de adesão do Seguro Prestamista impresso no momento da assinatura do contrato.
- **O impacto no Blueprint:** Embora as regras federais determinem que, desde 2020, o documento físico é totalmente dispensável, os funcionários das agências bancárias desconhecem a simplificação e barram o atendimento do estudante na boca do caixa se ele não apresentar o papel impresso, gerando perda de prazos e deslocamentos frustrados.

---

## Rodada 5

**[Claude]** O repasse financeiro do FNDE para as IES é feito via CFT-E (títulos públicos), não em dinheiro. Isso é um processo completamente invisível para o estudante. Para o blueprint, onde você posiciona esse processo — na camada de **Backstage** ou de **Processos de Suporte**? E mais importante: esse processo de repasse tem algum **fail point** que afeta diretamente a jornada do estudante — ou ele é completamente isolado da experiência do cidadão?

**[Eli]** Para o mapeamento do Service Blueprint, o processo de repasse mensal de CFT-E deve ser posicionado na camada de **Processos de Suporte**, e ele não é isolado; possui um fail point crítico que afeta diretamente o estudante.

**Posicionamento no Blueprint: Processos de Suporte**

Este processo deve ficar na camada de Processos de Suporte pelas seguintes razões: as ações de Backstage são executadas por funcionários da linha de frente que estão apenas "invisíveis" ao cliente (como o funcionário da CPSA digitando dados no sistema). Já o repasse e resgate de títulos envolvem agentes e sistemas puramente estruturais e de liquidação financeira (FNDE, Secretaria do Tesouro Nacional, CETIP e a Caixa Econômica Federal atuando na subcustódia dos papéis), sem qualquer interface de atendimento direta ou indireta com o aluno.

**O Fail Point: Bloqueio Administrativo por Irregularidade Fiscal da Mantenedora**

- **Como ocorre no suporte:** Para receber o repasse mensal de CFT-E, a instituição de ensino é obrigada a manter regularidade fiscal comprovada por CND ou CPEND com a Receita Federal e o INSS. Se a faculdade atrasar o pagamento de seus próprios impostos federais, o FNDE bloqueia imediatamente o processamento de recompra dos títulos.
- **Como o problema atinge o estudante:** Se a irregularidade fiscal persistir, o FNDE/MEC pode determinar o sobrestamento da adesão daquela instituição ao programa. Com a instituição suspensa, o portal SIFESWeb impede a abertura e o processamento de aditamentos de renovação semestral para todos os alunos daquela faculdade. Sem conseguir concluir o aditamento dentro do prazo, o estudante tem o financiamento travado — e passa a ser cobrado diretamente pela faculdade por um colapso financeiro-tributário que ocorreu inteiramente na camada de suporte governamental.

---

## Rodada 6

**[Claude]** Agora vamos consolidar as camadas. Com base em tudo que discutimos, me diga: o blueprint do FIES tem **quantas etapas** na linha do cidadão (Ações do Cidadão)? Liste cada etapa com um nome curto e diga se ela é predominantemente **digital, presencial ou híbrida**.

**[Eli]** Na linha de "Ações do Cidadão" do Service Blueprint do FIES, o fluxo é estruturado em **5 etapas principais**:

1. **Inscrição** — Predominantemente Digital: Ocorre de forma totalmente eletrônica por meio do Portal de Acesso Único ao Ensino Superior do MEC. O candidato realiza o login único via Gov.br, preenche os dados cadastrais e de rendimentos do grupo familiar e indica suas opções de curso.

2. **Complementação** — Predominantemente Digital: O estudante pré-selecionado acessa online o painel de controle do FiesSeleção para complementar a inscrição. Nessa fase, ele insere informações de matrícula, opta pelo percentual de financiamento pretendido, visualiza os encargos simulados e escolhe a seguradora do seguro prestamista.

3. **Validação (CPSA)** — Híbrida: Embora as IES ofereçam portais acadêmicos para que o aluno envie digitalmente os documentos comprobatórios, a validação efetiva e a emissão do DRI exigem interações diretas e, frequentemente, o comparecimento do estudante aos guichês físicos da CPSA.

4. **Formalização Bancária** — Híbrida: O formato varia conforme o perfil do contrato. Estudantes sem fiador podem realizar a contratação 100% digital no "App FIES CAIXA". Estudantes que necessitem de fiadores convencionais devem comparecer presencialmente à agência bancária para assinar fisicamente o contrato.

5. **Renovação (Aditamentos)** — Híbrida: Se o aditamento for "Simplificado" (sem alteração de curso, turno, fiador ou IES), a validação ocorre inteiramente de forma digital no SIFESWeb. Se houver alteração contratual ("Não Simplificado"), o estudante deve retirar fisicamente o DRM na CPSA e comparecer presencialmente à agência bancária.

---

## Rodada 7

**[Claude]** Agora as evidências físicas. Em um Service Blueprint, cada transição entre etapas é marcada por um artefato — algo tangível que o estudante recebe ou produz e que prova que passou de uma etapa para a próxima. Para cada uma das 5 etapas que você listou, me diga qual é o **artefato principal** que marca a conclusão daquela etapa. E me diga: algum desses artefatos é **ambíguo ou problemático** na prática?

**[Eli]** Para cada uma das 5 etapas da jornada do estudante do FIES, os artefatos principais de conclusão são:

| Etapa | Artefato Principal |
|---|---|
| Inscrição | Comprovante de Inscrição (PDF com chave de segurança) |
| Complementação | Comprovante de Complementação da Inscrição (tela de confirmação ou PDF) |
| Validação (CPSA) | Documento de Regularidade de Inscrição — DRI (físico ou digitalizado) |
| Formalização Bancária | Contrato de Financiamento / Cédula de Crédito Bancária — CCB (assinado) |
| Renovação (Aditamentos) | Documento de Regularidade de Matrícula — DRM |

**Artefatos Ambíguos ou Problemáticos na Prática**

Três desses artefatos são altamente dependentes do perfil do estudante e geram bifurcações na operação real:

**1. O DRI (Validação na CPSA) — Ambivalência Digital vs. Física**

A Portaria MEC nº 230/2021 dispensa o agente financeiro de exigir a via física do DRI, determinando validação eletrônica. Porém, muitas agências bancárias continuam retendo o documento em papel por desconhecimento da simplificação normativa, criando um artefato "invisível" para uns e obrigatório para outros.

**2. O Contrato / CCB (Formalização Bancária) — Bifurcação de Canais**

Se o estudante se enquadrar no FIES Social (CadÚnico), o artefato gerado é uma CCB com assinatura puramente eletrônica no celular. Se possuir fiador convencional, o aplicativo o bloqueia e ele é obrigado a gerar um contrato físico tradicional com assinaturas manuscritas nas agências bancárias.

**3. O DRM (Renovação) — Dependência do Tipo de Aditamento**

No Aditamento Simplificado, o DRM é gerado digitalmente. No Aditamento Não Simplificado (com alteração de curso, turno, IES ou dados do fiador), o DRM impresso em papel torna-se obrigatório, exigindo que o estudante retire fisicamente o documento na CPSA e o leve à agência bancária.

---

## Rodada 8

**[Claude]** Última rodada de consolidação. Você mapeou 5 etapas, identificou fail points críticos na CPSA e na formalização bancária, e revelou artefatos ambíguos. Para fechar o blueprint, me diga: se você tivesse que escolher **o fail point mais crítico de toda a jornada** — aquele que mais derruba estudantes antes de conseguirem o financiamento — qual seria? Justifique com base na pesquisa, e diga em qual camada do blueprint ele deve ser marcado com o símbolo ⚠.

**[Eli]** Para consolidar este blueprint, elejo o fail point que atua como o filtro mais impiedoso da jornada: a **Comprovação de Renda e Validação Documental na CPSA**.

**O Fail Point Crítico: "O Funil da Documentação Comprobatória"**

Embora a aprovação inicial no sistema do MEC gere uma expectativa de conquista, a realidade é que o processo de "verificação" é onde o estudante mais frequentemente perde o acesso ao benefício antes mesmo de iniciá-lo. O estudante muitas vezes domina o conceito de "renda bruta", mas não possui a documentação formal necessária para comprovar a realidade de uma família que, frequentemente, vive na informalidade. A interpretação da CPSA é discricionária e rigorosa; se a documentação não espelha perfeitamente a declaração inicial, o sistema "trava" o candidato.

**Localização no Blueprint:** Este ponto deve ser marcado com o símbolo ⚠ na **Camada de Validação e Elegibilidade** (etapa de Validação na CPSA), abrangendo tanto o Frontstage (interação do estudante com a CPSA) quanto o Backstage (conferência documental pelos funcionários).

**Justificativa Estrutural**

- **Ambiguidade Documental:** Diferente da inscrição no ENEM/ProUni, que é autodeclaratória e digital, a CPSA exige a materialização dessa autodeclaração em papel. A falta de literacia financeira ou o acesso a um contador para organizar essa prova documental é o que causa a reprovação imediata.
- **O "Efeito Precipício":** Enquanto falhas acadêmicas (notas, frequência) ocorrem ao longo do curso (evasão contínua), a falha na CPSA é um evento de exclusão abrupta na porta de entrada. Ela impede a matrícula ou a formalização, transformando um estudante aprovado em um estudante "inapto" em questão de dias.
- **Peso do Risco:** A responsabilidade de conferir os documentos recai sobre a IES. Por medo de auditorias do MEC, as universidades tendem a adotar uma postura de "compliance defensivo", indeferindo processos com qualquer inconsistência, o que vitimiza o estudante que não possui suporte para contestar ou retificar sua situação em tempo hábil.

Este fail point é o **gargalo de vidro** da jornada: ele é transparente, parece acessível, mas ao ser tocado pode quebrar o plano do estudante por detalhes técnicos que fogem ao seu controle direto.

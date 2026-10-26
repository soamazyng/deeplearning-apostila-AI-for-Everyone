# IA na prática: aprendendo a criar bons prompts

## Apostila 2 — Guia simples do curso *AI Prompting for Everyone*

**Curso de referência:** [AI Prompting for Everyone](https://www.deeplearning.ai/courses/ai-prompting-for-everyone), apresentado por **Andrew Ng**, da **DeepLearning.AI**.  
**Público:** qualquer pessoa que queira obter respostas melhores da IA, inclusive quem não programa.  
**Formato:** explicações em português simples, analogias do cotidiano, exemplos de prompts, exercícios, gabarito, glossário e desafio final.  
**Origem:** adaptação didática **independente e não oficial**, construída a partir das transcrições de estudo fornecidas e do programa oficial do curso. Os prompts e exemplos de squads, quando não atribuídos ao curso, são **criações pedagógicas desta apostila**.

> **Ideia principal:** a qualidade da resposta não depende apenas de como você faz a pergunta. Depende também do contexto, das fontes, das ferramentas, das verificações e das conversas que vêm depois dela.

---

## O que você vai aprender

| Módulo | No curso | Ao terminar, você conseguirá... |
|---|---|---|
| **1. Encontrando informações** | *Finding Information* | Escolher entre conhecimento do modelo, busca na web e pesquisa aprofundada; avaliar fontes |
| **2. IA como parceira de pensamento** | *AI as a Thought Partner* | Conversar, planejar, fazer brainstorming, revisar textos, dar contexto e pedir críticas justas |
| **3. Imagens, dados e código** | *Working with Multimedia & Code* | Enviar imagens, criar imagens, construir pequenos aplicativos e analisar planilhas com ajuda da IA |

**Como estudar:** dedique um encontro a cada módulo. Leia, copie um prompt do laboratório, altere para sua realidade e compare as respostas. Faça os exercícios antes do gabarito. O objetivo não é decorar fórmulas: é formar bons hábitos.

**Importante:** funcionalidades, nomes de produtos, custos e limites de ferramentas mudam. A apostila explica **conceitos**, não promete que todo aplicativo oferece os mesmos recursos. Questões médicas, financeiras ou jurídicas exigem fontes e profissionais adequados. Nunca envie dados confidenciais da empresa para uma ferramenta não autorizada.

## Índice

1. [Módulo 1 — Encontrando informações](#módulo-1--encontrando-informações)
2. [Módulo 2 — IA como parceira de pensamento](#módulo-2--ia-como-parceira-de-pensamento)
3. [Módulo 3 — Imagens, dados e código](#módulo-3--imagens-dados-e-código)
4. [Laboratório — Biblioteca de prompts](#laboratório--biblioteca-de-prompts)
5. [Projeto final — Pesquisa, decisão e aplicativo](#projeto-final--pesquisa-decisão-e-aplicativo)
6. [Glossário](#glossário)
7. [Avaliação — 30 questões](#avaliação--30-questões)
8. [Gabarito comentado](#gabarito-comentado)
9. [Créditos e próximos passos](#créditos-e-próximos-passos)

### Um jeito simples de estudar em equipe

| Encontro | Leia | Experimente |
|---|---|---|
| **1** | Módulo 1 | Uma pergunta sem busca e a mesma pergunta com fontes oficiais |
| **2** | Módulo 2 | Quatro rodadas de brainstorming e uma rubrica de avaliação |
| **3** | Módulo 3 | Um protótipo pequeno ou um gráfico com dados fictícios |

**Dica:** crie um arquivo de anotações para registrar o prompt inicial, a resposta obtida, o que você mudou e qual foi a diferença. Você estará construindo seu próprio repertório — muito mais útil que decorar uma lista de “prompts infalíveis”.

---

# Módulo 1 — Encontrando informações

**Pergunta-guia:** quando a IA responde, de onde vem aquilo que ela diz?

## 1. De iniciante a usuário avançado de IA

Pense em duas pessoas que vão contratar um serviço para reformar a cozinha.

- A primeira pergunta: **“Qual é a melhor bancada?”** Recebe recomendações genéricas.
- A segunda conta a metragem, orçamento, hábitos da família, materiais que prefere, fotos do ambiente e prazo. Pede três opções, vantagens, desvantagens e quais pontos ainda precisam ser verificados.

A diferença não é saber uma palavra secreta. É **saber trabalhar com a IA**.

No curso, Andrew Ng chama de **AI power user** a pessoa que consegue usar recursos mais poderosos que uma pergunta curta: acrescenta informações, pede análises mais difíceis, usa documentos e ferramentas, faz perguntas neutras e melhora o resultado em várias rodadas.

**Analogia do cotidiano:** imagine pedir a um cozinheiro “faça o jantar” versus “tenho quatro convidados, uma pessoa não come lactose, só tenho 40 minutos, estes ingredientes estão na geladeira, e gostaria de duas opções simples”. A segunda instrução dá condições para que ele acerte.

**Prompt fraco:**

> Faça uma autoavaliação profissional para mim.

**Prompt melhor:**

> Vou preparar minha autoavaliação. Abaixo estão minhas entregas, feedbacks e dificuldades do período. Primeiro, organize as evidências por impacto e competência. Depois, mostre informações que faltam. Só então escreva um rascunho objetivo, sem inventar conquistas.

**Cuidado:** fornecer mais contexto não significa despejar tudo. É preciso selecionar as informações úteis e respeitar a privacidade.

## 2. O que o modelo já sabe: conhecimento pré-treinado

Imagine uma pessoa que passou anos lendo livros, artigos, notícias, fóruns e enciclopédias. Ela aprende padrões e fatos, mas **não sabe automaticamente o que aconteceu hoje na sua rua**. O conhecimento pré-treinado da IA funciona, em parte, como essa bagagem de leitura.

Os modelos aprendem com grandes coleções de exemplos. Eles podem explicar coisas amplamente documentadas, como uma receita popular, conceitos de matemática ou fenômenos naturais. Mas informação de nicho pode ser rara, mal explicada ou inexistente no treinamento.

**Três situações diferentes:**

| Pergunta | Principal dificuldade | O que fazer |
|---|---|---|
| “Por que um bolo cresce?” | Conhecimento geral | Uma explicação do modelo costuma ser um bom começo |
| “Qual regra entrou em vigor neste mês?” | Informação recente | Pesquisar e conferir fonte oficial |
| “O que foi decidido na reunião do meu time?” | Informação privada | Fornecer uma ata autorizada ou usar integração corporativa permitida |

**Analogia:** o modelo pode conhecer receitas em geral, mas não sabe que você acabou de comprar farinha de amêndoas até que você conte.

A transcrição explica que textos mais frequentes no treinamento **podem** aumentar a familiaridade do modelo com um tema. Isso é uma intuição útil, mas não é uma garantia de precisão: uma ideia repetida milhares de vezes pode continuar errada. Modelos também podem interpretar frases com erros de digitação — não é necessário escrever como um professor de português para conseguir ajuda.

**Exemplo prático:**

> Explique o que é cache como se eu tivesse 12 anos. Dê um exemplo com uma geladeira e outro com um aplicativo. No final, diga em qual ponto a analogia deixa de funcionar.

Isso usa conhecimento geral; não precisa necessariamente acessar a internet.

## 3. A data de corte: por que a IA pode não saber o que aconteceu ontem

O treinamento de um modelo termina em alguma data, e fatos posteriores podem não estar nele. Mesmo quando o modelo tem acesso a atualizações ou ferramentas, **não devemos assumir que todo fato recente está correto sem verificar**.

**Analogia:** uma edição antiga de um guia de restaurantes pode explicar perfeitamente o que é risoto, mas não pode garantir que um restaurante continua aberto hoje.

No curso, o exemplo do meme “6-7” ilustra algo que apareceu depois da base de conhecimento de determinados modelos. Perguntas sobre memes recentes, notícias, preços, normas, vagas de emprego e horários locais geralmente pedem **busca atualizada**.

**Prompt melhor para fatos recentes:**

> Pesquise a informação mais recente sobre este assunto. Informe a data dos fatos, consulte fontes primárias e mostre links que sustentem cada conclusão. Se as fontes discordarem, explique a divergência.

**Erro comum:** um resultado parecer convincente não garante que tenha sido verificado.

## 4. Web search: uma pesquisa na internet feita com ajuda da IA

**Web search** significa pesquisar páginas na internet para complementar o que o modelo já sabe. Isso pode ocorrer automaticamente, quando a ferramenta permite, ou porque você pediu explicitamente.

**Analogia:** em vez de responder somente de memória, a IA vai até uma biblioteca atualizada, consulta alguns livros e volta com uma síntese.

**Exemplo do dia a dia:** você quer escolher uma academia perto da sua casa. O modelo, sozinho, pode conhecer os principais critérios de escolha; com pesquisa, pode procurar endereços, valores divulgados e horários. Mesmo assim, condições podem mudar e convém confirmar com o estabelecimento.

**Exemplo no trabalho (criado para esta apostila):**

> Busque na documentação oficial as versões atualmente suportadas de [biblioteca]. Resuma as diferenças que afetam uma aplicação Java, indique a data da documentação e forneça os links. Não trate uma postagem antiga como fonte definitiva.

**Perguntas para conferir uma pesquisa:** quem publicou? Quando? É fonte original ou alguém comentando a fonte? O texto realmente apoia a conclusão? A informação ainda vale?

## 5. Fontes confiáveis: nem tudo que está na internet merece confiança

Uma pesquisa pode encontrar páginas populares antes das melhores páginas. Um fórum contém boas experiências pessoais, mas nem sempre é a fonte certa para responder sobre segurança de um medicamento, legislação ou especificação técnica.

**Analogia:** uma pessoa pode recomendar uma pomada que funcionou para ela. Isso não transforma a experiência em evidência científica de segurança para todo mundo.

O curso contrasta informações de fóruns, páginas comerciais e organizações oficiais. A lição central é **orientar a busca para fontes apropriadas ao risco da pergunta**.

| Assunto | Fontes preferíveis |
|---|---|
| Saúde | Órgãos de saúde, diretrizes, revisões científicas e profissionais |
| Biblioteca ou linguagem | Documentação oficial e notas de lançamento |
| Produto | Fabricante para especificações; avaliações independentes para experiências |
| Regra ou política | Texto legal ou norma oficial, com data e jurisdição |
| Opiniões de usuários | Comunidades e avaliações — deixando claro que são relatos |

**Prompt com critério de fonte:**

> Quero uma resposta fundamentada. Priorize documentação oficial e fontes primárias publicadas ou atualizadas recentemente. Distinga fatos, hipóteses e opiniões. Inclua os links e a data de cada fonte importante. Se a evidência for insuficiente, diga isso.

**Cuidado:** até uma resposta com citações pode resumir mal o material. Abra as fontes críticas. A transcrição descreve uma implementação de busca em que um modelo recebe resumos trazidos por outro componente; isso é **um modo possível de funcionamento**, e os detalhes variam entre produtos.

## 6. Conhecimento do modelo, busca e Deep Research: qual escolher?

**Deep Research** é uma modalidade de pesquisa mais extensa: planeja subperguntas, examina diversas fontes, volta a pesquisar conforme o que descobre e tenta entregar uma síntese organizada com referências. É especialmente útil quando existem **várias dimensões** a analisar.

**Analogia:**

- **Conhecimento do modelo:** perguntar algo a um amigo que leu muito.
- **Web search:** pedir a esse amigo que consulte alguns sites antes de responder.
- **Deep Research:** contratar um pesquisador para montar um dossiê com fontes e comparação de alternativas.

| Modo | Bom para | Exemplo de pedido |
|---|---|---|
| **Conhecimento do modelo** | Conceitos relativamente estáveis | “Explique o que é latência com analogias” |
| **Busca na web** | Questão localizada, atual ou específica | “Encontre a documentação da versão atual” |
| **Pesquisa aprofundada** | Decisão complexa, fontes múltiplas | “Compare três arquiteturas, custo, riscos e manutenção” |

**Exemplo de Deep Research (criado):**

> Pesquise abordagens de adoção de IA para equipes de engenharia. Primeiro proponha perguntas de pesquisa. Compare oportunidades, riscos, métricas de resultado e pré-requisitos. Priorize estudos e documentação confiáveis; separe fatos de recomendações e indique limites das evidências. Apresente uma síntese executiva e uma matriz de decisão.

**Quando não usar:** não vale acionar uma investigação extensa para perguntar o significado de uma palavra simples. Mais etapas também podem gerar mais oportunidades de erro; a verificação permanece importante.

## 7. Laboratório do módulo 1 — a mesma pergunta, três maneiras

**Experimento do curso, adaptado:** comparar respostas com e sem busca e, depois, com pesquisa aprofundada.

**Passo 1.** Pergunte: “Quais mudanças recentes afetaram esta ferramenta?” sem solicitar busca. Anote data, fontes e grau de detalhe.  
**Passo 2.** Repita com: “Pesquise na web e cite as notas de lançamento oficiais”.  
**Passo 3.** Para uma questão complexa, peça uma pesquisa aprofundada comparando impactos, alternativas e riscos.  
**Passo 4.** Confira duas afirmações importantes diretamente nas fontes.

**Registre:** o que mudou? Qual resposta tinha evidências verificáveis? Qual parecia certa, mas não estava bem sustentada?

### Resumo do módulo 1

A IA não sabe tudo de forma automática. Aprenda a escolher a origem da informação, especificar as fontes e conferir afirmações importantes. **Prompt bom também é prompt que sabe quando pesquisar.**

### Exercícios do módulo 1

**1.** Por que um modelo pode explicar bem um conceito e errar o horário de uma loja?  
**2.** Em quais situações uma página oficial deve prevalecer sobre um fórum?  
**3.** Qual modo você usaria para comparar o impacto de cinco soluções técnicas em custo, segurança e implantação?  
**4.** Qual detalhe você acrescentaria a “Me diga se esta notícia é verdadeira”?  
**5.** Por que uma citação não garante que uma resposta está correta?

---

# Módulo 2 — IA como parceira de pensamento

**Pergunta-guia:** como transformar um chatbot em um parceiro que ajuda a decidir, escrever e melhorar ideias, em vez de apenas concordar?

## 8. Brainstorming: mais do que pedir uma lista de ideias

**Brainstorming** é gerar possibilidades antes de escolher. A IA consegue sugerir muitas opções, mas as melhores ideias normalmente aparecem quando você conversa, reage e refina os resultados.

No curso, Andrew Ng usa o desafio de encontrar vários usos para um tijolo. Fazer uma lista longa é relativamente fácil para um modelo; escolher a ideia que resolve **o seu** problema é a parte importante.

**Analogia:** imagine provar sabores em uma sorveteria. A atendente apresenta várias opções, você diz “esse é doce demais, gostei do azedinho”, e ela recomenda algo mais próximo do seu gosto. O feedback melhora a próxima sugestão.

**Prompt básico:**

> Me dê ideias para melhorar nossas reuniões.

**Prompt com contexto:**

> Temos uma reunião semanal de 45 minutos, 12 participantes, muitos assuntos repetidos e poucas decisões. Sugira cinco formatos alternativos. Para cada um, dê objetivo, duração, vantagem, desvantagem e risco. Evite ideias que dependam de ferramentas pagas.

**Segunda rodada:**

> Gostei das opções 2 e 4. A opção 1 exige muita preparação e a 3 não resolve o problema das decisões. Combine os pontos fortes das opções 2 e 4 e traga duas variações ainda mais simples.

A transcrição também traz planos de treino com um trampolim e até com um gato. A intenção do exemplo não é prescrever treino, e sim mostrar como **detalhes inesperados no contexto geram ideias diferentes**.

## 9. Iteração: a conversa é parte da solução

Uma estratégia prática de brainstorming é:

**Contexto → 3 a 5 opções → feedback → novas opções → escolha → detalhamento.**

**Analogia:** escolher um apartamento. Na primeira rodada você diz “quero algo perto do metrô”. Depois de visitar opções, percebe que precisa de silêncio, vaga e um mercado próximo. Você não sabia exatamente todos os critérios antes de comparar as primeiras alternativas.

No curso, o exemplo da organização de dívidas ilustra o mesmo processo: primeiro surgem opções diferentes (preservar dinheiro, pagar juros mais altos, priorizar compromisso familiar). Ao acrescentar informação sobre uma mudança de casa, a análise muda. **A recomendação não deveria ser automática: as prioridades e restrições da pessoa importam.**

**Prompt para explorar:**

> Não escolha por mim ainda. Apresente quatro opções bastante diferentes. Em seguida, diga quais informações adicionais poderiam mudar a recomendação. Espere meu feedback antes de refinar.

**Você aprendeu se...** consegue melhorar um resultado sem reiniciar do zero nem aceitar a primeira resposta como definitiva.

## 10. Contexto: a matéria-prima de uma resposta personalizada

**Contexto** é tudo que o modelo pode levar em conta para produzir aquela resposta: sua pergunta, instruções disponíveis, partes da conversa, arquivos, resultados de ferramentas e outros dados fornecidos.

**Analogia:** um médico que recebe histórico, exames e sintomas consegue trabalhar com informações mais relevantes do que alguém que só ouve “não estou bem”. Isso não significa que a IA substitua um médico; apenas mostra por que contexto importa.

Pense em quatro camadas:

1. **Objetivo:** o que você quer decidir ou produzir?
2. **Situação:** qual é o problema, para quem, onde e por quê?
3. **Restrições:** prazo, orçamento, formato, riscos, informações proibidas.
4. **Evidências:** arquivos, números, exemplos, critérios e fontes.

**Exemplo (criado):**

> Objetivo: escolher uma forma de acompanhar indicadores de delivery. Contexto: cinco equipes trabalham com ritmos diferentes. Restrições: não quero métricas que estimulem comparações injustas entre pessoas. Evidências: estas são as definições de lead time, throughput e retrabalho. Gere propostas e explicite possíveis incentivos ruins.

A transcrição explica que modelos podem trabalhar com janelas de contexto muito grandes, mas seus limites **variam por sistema**. Maior capacidade de receber texto não garante que ele use cada detalhe corretamente.

## 11. Quando começar uma conversa nova

O histórico pode ajudar ou atrapalhar. Se você passa uma hora conversando sobre sua alimentação e de repente pede um documento jurídico, partes da conversa anterior talvez sejam **ruído**.

**Analogia:** não é necessário deixar todos os cadernos do semestre abertos sobre a mesa para resolver uma conta simples.

**Regra útil:** quando muda radicalmente de objetivo, avalie abrir uma conversa nova. Quando continua o mesmo problema, mantenha o histórico e acrescente feedback. Em trabalhos longos, crie um resumo do que foi decidido para preservar apenas o que importa.

**Prompt para reduzir ruído:**

> Resuma o objetivo, as decisões, as restrições e as pendências desta conversa. Exclua hipóteses rejeitadas. Vou usar esse resumo para continuar o trabalho em uma conversa nova.

**Cuidado:** resumos podem omitir detalhes; confira os pontos mais importantes antes de confiar neles.

## 12. Aplicativos com acesso a arquivos: a IA pode buscar contexto sozinha

Na transcrição, ferramentas de IA para desktop conseguem, **quando autorizadas e tecnicamente habilitadas**, localizar, ler, renomear ou editar arquivos. Em vez de escolher manualmente todos os documentos que serão enviados, o sistema pode encontrar os relevantes durante a tarefa.

**Analogia:** uma assistente que entra em um arquivo físico autorizado, procura as pastas certas e propõe como organizar tudo — mas que também pode mover a pasta errada se não houver supervisão.

**Processo recomendado pelo curso:**

**Pedido → plano proposto → revisão humana → execução autorizada → conferência.**

**Exemplo criado:**

> Examine apenas a pasta `documentos-estudo/`. Antes de modificar qualquer coisa, liste duplicatas prováveis, sugira uma organização e indique quais arquivos seriam movidos ou renomeados. Não exclua arquivos. Aguarde minha aprovação explícita para executar.

**Cuidados indispensáveis:**

- Dê acesso à **menor pasta necessária**, nunca ao computador inteiro por conveniência.
- Leia as permissões de leitura, alteração e exclusão.
- Faça backup e use versionamento quando possível.
- Não suponha que um arquivo excluído poderá ser recuperado pela lixeira.
- Em contexto corporativo, siga políticas de segurança e use apenas ferramentas autorizadas.

A capacidade descrita depende do aplicativo. Um chat sem acesso a arquivos locais **não pode** realizar essas ações por mera instrução textual.

## 13. Raciocínio com IA: delegue um problema, não apenas uma resposta

O curso mostra que modelos modernos conseguem trabalhar em tarefas mais difíceis, consultar ferramentas e testar alternativas. Isso pode envolver comparar documentos, critérios conflitantes e caminhos de solução.

**Analogia:** escolher um carro não é perguntar “qual carro é bom?”. É comparar financiamento, manutenção, consumo, seguro, conforto e o uso previsto. O melhor carro depende do que você valoriza.

**Prompt:**

> Preciso escolher entre três alternativas. Leia os materiais que enviei. Primeiro, crie critérios de decisão; depois, compare alternativas em uma matriz. Mostre compromissos e riscos, diga quais fatos ainda precisam ser confirmados e recomende uma próxima ação reversível. Não invente dados ausentes.

O curso comenta que conselhos antigos como “pense passo a passo” se tornaram menos centrais conforme os modelos e modos de raciocínio evoluíram. O que continua importante é **dar o contexto necessário, escolher o modo apropriado e pedir uma saída verificável**. Frases como “analise com cuidado” podem orientar o nível de profundidade, mas não garantem acerto.

**Exemplo no trabalho (criado):**

> Avalie alternativas de arquitetura considerando desempenho, custo de manutenção, observabilidade, segurança e facilidade de evolução. Não decida apenas com base na elegância técnica; inclua os custos de migração e como validar as hipóteses num piloto.

**Cuidado:** um relatório longo e detalhado pode estar errado. Critérios e evidências importam mais que a quantidade de páginas.

## 14. Sicofancia: quando a IA concorda demais

**Sicofancia** (do inglês *sycophancy*) é a tendência de responder do jeito que agrada ao usuário, mesmo quando deveria contestar ou apresentar reservas.

**Analogia:** você pergunta “minha ideia é genial, não é?” a alguém que quer muito te agradar. A resposta pode ser simpática e pouco útil.

**Pergunta enviesada:**

> Minha ideia de usar IA em todas as reuniões é excelente, certo?

**Pergunta neutra:**

> Avalie a proposta de usar IA para registrar reuniões. Use os critérios de privacidade, custo, precisão, consentimento, utilidade e esforço de revisão. Dê argumentos favoráveis e contrários e identifique condições em que não valeria a pena.

**Outra técnica:** forneça uma rubrica, isto é, **uma lista de critérios** que a resposta deve seguir. Isso desloca o foco de “me faça feliz” para “avalie os fatos”.

**Prompt antissicofancia:**

> Quero uma avaliação objetiva. Não presuma que minha hipótese está certa. Identifique as três principais fragilidades, apresente contraexemplos e diga quais evidências fariam você mudar de conclusão.

**Cuidado:** pedir que “seja crítico” não substitui fontes nem critérios claros. O objetivo não é fazer a IA discordar sempre, e sim avaliar melhor.

## 15. Escrever com IA sem produzir texto vazio

O curso usa a expressão **AI slop** para descrever textos gerados em grande quantidade que parecem elaborados, mas ficam vagos, repetitivos ou com frases feitas. O problema não é usar IA; é publicar algo que você nem teve trabalho de pensar ou conferir.

**Analogia:** um bolo com cobertura linda e sem sabor por dentro. Parece pronto, mas falta substância.

**Fluxo que o curso recomenda:**

**Notas e objetivo → opções de estrutura → escolha do esboço → tópicos por seção → texto completo → edição.**

**Prompt ruim:**

> Escreva um artigo incrível sobre produtividade.

**Prompt melhor:**

> Vou escrever um artigo curto para líderes de engenharia sobre interrupções no trabalho. Estas são minhas notas e exemplos. Primeiro proponha três estruturas, com uma tese específica e um contra-argumento em cada uma. Não escreva o artigo ainda. Quero escolher a estrutura antes de expandir.

**Segunda etapa:**

> Escolho a segunda estrutura. Amplie cada seção em até cinco tópicos factuais. Marque em quais pontos preciso incluir uma experiência pessoal ou fonte verificável.

**Terceira etapa:**

> Agora escreva a versão completa com linguagem direta, sem exageros, sem afirmar resultados que não constam das minhas notas e sem frases de efeito vazias. Preserve minha voz.

Essa sequência é mais trabalhosa que um comando só, mas permite melhorar o raciocínio **antes** de produzir páginas de texto.

## 16. Revisar e criticar: peça um diagnóstico antes da reescrita

Na aula de crítica, o curso apresenta duas práticas: **revisar por partes** e **avaliar segundo rubricas**. Fazer dezenas de alterações de uma vez torna difícil descobrir o que realmente melhorou.

**Analogia:** se um prato está sem sal, você ajusta o tempero antes de trocar todos os ingredientes da receita.

**Prompt para edição por partes:**

> Leia o texto abaixo. Não reescreva tudo. Aponte até cinco problemas concretos de clareza, estrutura ou evidência, citando trechos. Sugira alternativas para apenas o primeiro parágrafo. Depois espere minha escolha.

**Prompt de rubrica:**

> Avalie este texto usando notas de 0 a 5 para clareza, precisão factual, organização, exemplos e adequação ao público iniciante. Para cada nota, explique o motivo e proponha uma melhoria que possa ser verificada. Não elogie automaticamente.

A transcrição mostra o uso de rubricas até para histórias de ficção: desenvolvimento de personagens, coerência e outros aspectos. Podemos adaptar o método para documentação técnica, propostas e apresentações.

**Rubrica simples de documento técnico (exemplo criado):**

| Critério | O que verificar |
|---|---|
| Objetivo | Está claro qual problema será resolvido? |
| Evidência | Afirmações importantes têm fonte ou dado? |
| Clareza | Um leitor sem contexto consegue compreender? |
| Riscos | Restrições e modos de falha aparecem? |
| Ação | Está claro o que acontece depois? |

O curso também observa que modelos diferentes podem criticar de forma diferente. Pedir uma segunda avaliação pode ajudar em decisões importantes, mas duas IAs concordando **não prova** que a conclusão está certa.

## 17. Laboratório do módulo 2 — melhore uma ideia em quatro rodadas

**Objetivo:** experimentar brainstorming, contexto, neutralidade e crítica como um só fluxo.

**Rodada A — abra possibilidades:** escolha um problema simples e peça cinco soluções com restrições claras.  
**Rodada B — dê feedback:** diga quais duas opções gostou, quais rejeitou e por quê. Peça novas opções.  
**Rodada C — questione:** aplique rubrica de custo, facilidade, impacto, risco e reversibilidade.  
**Rodada D — produza:** construa um plano de ação de uma página, com hipótese, próximo passo e como saber se funcionou.

**Exemplo de tema:** reduzir o tempo desperdiçado em reuniões recorrentes, sem prejudicar a comunicação do time.

### Resumo do módulo 2

A IA se torna mais útil quando você traz o problema real, aceita explorar caminhos e exige críticas fundamentadas. **Primeira resposta não é versão final** — e elogio não é evidência.

### Exercícios do módulo 2

**6.** O que significa iterar em uma conversa?  
**7.** Cite quatro tipos de contexto úteis.  
**8.** Por que pode valer abrir um chat novo?  
**9.** Qual o risco de autorizar uma IA a reorganizar toda sua pasta pessoal?  
**10.** Reescreva de forma neutra: “Minha arquitetura é melhor, concorda?”  
**11.** Qual a vantagem de fazer um esboço antes do artigo?  
**12.** O que é uma rubrica e como ela reduz o risco de respostas agradáveis porém inúteis?

---
# Módulo 3 — Imagens, dados e código

**Pergunta-guia:** e se, em vez de só escrever respostas, a IA pudesse ver, desenhar, analisar números e construir algo que funciona?

## 18. Multimodalidade: a IA trabalha com mais do que texto

*Multimodal* é um nome complicado para uma ideia simples: **misturar formatos diferentes de informação**. Texto é uma modalidade; imagem, áudio e vídeo são outras.

**Analogia:** explicar um problema do carro por mensagem é uma coisa. Enviar uma foto, um vídeo do barulho e uma descrição do momento em que acontece pode deixar a explicação mais clara.

O curso mostra exemplos de imagens de bolo usadas para explorar ideias de aniversário, vídeos, música e até vozes sintetizadas. Alguns sistemas aceitam imagens e áudio como entrada; outros geram imagens, sons, vídeos ou código como saída. **Nem todos fazem tudo**, e acesso e custos variam.

| Entrada | Pedido possível | Saída esperada |
|---|---|---|
| Foto de uma planta | “Descreva o que aparece e o que não dá para afirmar” | Explicação em texto |
| Áudio de reunião autorizado | “Resuma decisões e tarefas” | Texto estruturado |
| Tabela de vendas | “Encontre tendências e faça um gráfico” | Análise e gráfico |
| Descrição de uma festa | “Crie três estilos de convite” | Imagens |
| Ideia de jogo | “Crie uma página interativa simples” | Código ou aplicativo |

**Regra de ouro:** quanto mais importantes os dados, maior a necessidade de consentimento, privacidade e validação. Clonagem de voz e imagens realistas, por exemplo, podem ser úteis em contextos autorizados, mas também podem permitir golpes e falsificações.

## 19. Entendendo imagens: mostrar pode ser melhor que descrever

Na transcrição, Andrew Ng usa uma fotografia de um quadro branco com texto e matemática para mostrar que sistemas capazes de analisar imagens podem responder sobre o conteúdo visual. A mesma ideia vale para um desenho, um recibo ou um rascunho de interface.

**Analogia:** é mais rápido mostrar uma foto de um móvel quebrado do que tentar explicar a posição exata de cada parafuso.

**Prompt que funciona:**

> Observe a imagem anexada. Primeiro descreva o que realmente está visível. Depois identifique os elementos relevantes para [objetivo]. Se alguma parte estiver ilegível ou incerta, sinalize em vez de adivinhar. Separe observações de interpretações.

**Exemplo de engenharia (criado):**

> Analise esta captura de uma tela. Identifique possíveis problemas de hierarquia visual e acessibilidade. Para cada problema, diga o elemento da imagem que levou à observação. Não presuma como a funcionalidade se comporta se isso não for visível.

**Cuidado:** um modelo pode ler algo incorretamente, ignorar um item pequeno ou interpretar mal um gráfico. Quando valores forem decisivos, confirme na fonte original ou forneça a tabela de dados em vez de apenas a foto.

## 20. Gerar imagens: descreva a cena e refine o resultado

A aula mostra como criar convites, cenas fantásticas e versões estilizadas de fotografias. Também usa exemplos de linguagens visuais como *anime* e *cyberpunk*. Você não precisa ser designer para testar ideias, mas dar detalhes relevantes ajuda.

**Analogia:** pedir a um ilustrador “desenhe uma casa bonita” deixa inúmeras escolhas abertas. Se você explica que quer uma casa térrea, estilo aquarela, fim de tarde e jardim com flores amarelas, o espaço de possibilidades fica mais definido.

**Uma estrutura simples de prompt de imagem:**

- **Assunto:** quem ou o que aparece?
- **Ação / composição:** o que está acontecendo? Como os elementos estão posicionados?
- **Estilo:** fotografia, aquarela, ilustração, desenho técnico etc.
- **Ambiente / luz:** onde acontece e com qual atmosfera?
- **Restrições:** proporção, ausência de texto, cores, elementos a manter.

**Prompt ilustrativo:**

> Crie uma ilustração acolhedora de um gato curioso observando estrelas pela janela. Estilo aquarela com cores suaves, luz noturna, enquadramento horizontal 16:9. Sem frases nem logotipos. Preserve o foco no gato e na janela.

**Prompt de revisão:**

> Mantenha a composição e os personagens. Aumente um pouco o contraste das estrelas e deixe a iluminação interna mais quente. Não adicione objetos novos.

Você também pode usar a IA de texto para **ajudar a escrever o prompt visual**, quando não sabe descrever o estilo que tem em mente.

**Como funciona, em termos intuitivos?** A transcrição apresenta modelos de difusão: aprendem padrões de imagens e podem gerar novas imagens por um processo iterativo relacionado à remoção de ruído. **Isso é uma explicação simplificada, não uma regra válida para todos os geradores.**

**Limites:** a aparência de um personagem pode mudar entre imagens, textos longos dentro de imagens podem sair errados, e imagens aparentemente plausíveis podem conter objetos fisicamente estranhos. Faça inspeção visual antes de compartilhar.

## 21. Gerar aplicativos: você descreve, a IA tenta construir

O curso demonstra o uso de linguagem natural para criar pequenos jogos, sites e utilitários. Isso aproxima pessoas sem experiência em programação do desenvolvimento de protótipos; **não torna engenharia profissional desnecessária**.

**Analogia:** montar um móvel seguindo instruções é diferente de projetar um prédio. Criar um calculador simples é um bom primeiro projeto; criar um sistema bancário é outro nível de responsabilidade.

**Comece com algo pequeno:** calculadora para dividir conta entre amigos, aplicativo de flashcards, paleta de cores ou um jogo de obstáculos. O curso usa, entre outros exemplos, um pequeno aplicativo de fogos de artifício.

**Prompt base para prototipar:**

> Construa um aplicativo web simples para dividir uma conta de restaurante. Deve receber valor total, número de pessoas e percentual de serviço; mostrar o total por pessoa; validar números negativos e divisão por zero; funcionar bem no celular. Antes de implementar, resuma as funcionalidades. Depois entregue uma forma de testar o resultado.

**Por que os detalhes ajudam?** Porque a IA precisa escolher comportamento, aparência, entradas e regras. Sem isso, ela preenche os espaços em branco por conta própria.

**Para um projeto um pouco mais técnico (exemplo criado):**

> Crie um protótipo sem autenticação e sem banco de dados. Use dados fictícios. Separe interface, regras e testes básicos. Liste limitações de segurança e o que faltaria para um uso real. Não inclua credenciais nem serviços pagos.

**Cuidado com aplicativos gerados:** valide acessibilidade, comportamento em erros, privacidade, licenças, exposição de chaves e tratamento de dados. Se for para produção, revise o código, teste e aplique controles adequados.

## 22. Analisando dados: perguntas bem feitas viram gráficos úteis

Quando você fornece uma planilha, alguns sistemas de IA podem escrever e executar código para calcular estatísticas, filtrar dados e produzir gráficos. A transcrição mostra exemplos com dados de treino e vendas de uma loja de bebidas.

**Analogia:** uma planilha é como uma gaveta cheia de notas fiscais. A IA pode ajudar a separar, somar e procurar padrões; mas é sua responsabilidade conferir se as contas estão certas.

**Exemplo: loja de bebidas (inspirado no curso):** imagine uma tabela com mês, sabor, unidades e receita. A pergunta “Quais sabores venderam melhor?” pode ser melhorada para:

> Leia a tabela. Verifique valores ausentes, duplicados e datas. Calcule a receita mensal por produto, compare os últimos seis meses e identifique até três mudanças relevantes. Faça um gráfico com título, unidades e legenda. Mostre a fórmula de cada indicador e diga quais conclusões **não** podem ser tiradas apenas desses dados.

**Exemplo de squads (criado):**

> Com base nesta tabela fictícia de histórias, calcule a mediana do lead time por mês e a evolução do retrabalho. Não compare produtividade de indivíduos. Mostre o número de itens por mês, valores ausentes, possíveis distorções e um gráfico claro. Separe observações de hipóteses.

**Passos de uma análise responsável:**

1. Entenda o significado de cada coluna e a unidade de medida.
2. Verifique dados ausentes, duplicados, períodos e filtros.
3. Defina a pergunta exata antes de gerar gráficos.
4. Confira as contas e amostras manualmente.
5. Escreva conclusões proporcionais ao que os dados demonstram.

**Cuidado:** um gráfico bonito pode esconder filtro errado, soma duplicada ou denominador ausente. “A receita subiu” é diferente de “a campanha causou a alta da receita”. Associação **não** prova causa.

## 23. Como saber se a IA realmente executou o cálculo?

Nem todo sistema que fala sobre análise de dados executa código. Alguns apenas descrevem como fariam. Outros têm ferramentas específicas para realizar cálculos de verdade. **Pergunte qual caminho foi usado e solicite evidências verificáveis.**

**Prompt:**

> Informe se você executou código ou estimou os resultados a partir do texto. Se executou, mostre os cálculos, as colunas usadas e uma amostra dos dados transformados. Se não executou, sinalize isso e forneça as fórmulas para conferência.

Essa diferença importa muito quando uma decisão depende de centavos, percentuais, prazos ou indicadores de negócio.

## 24. Projeto integrado: pesquise, aprenda e construa

O laboratório final do curso combina técnicas de módulos anteriores: escolher uma pergunta, explorar alternativas, pesquisar informações e criar um pequeno aplicativo inspirado nos resultados. O exemplo apresentado envolve formular uma questão de pesquisa, produzir um relatório e criar um quiz interativo.

**Uma adaptação para o seu estudo:**

**Etapa 1 — Ideia:** “Quero aprender mais sobre carreiras em IA”. Peça três perguntas de pesquisa, escolha uma e refine-a.  
**Etapa 2 — Fontes:** use busca ou pesquisa aprofundada para reunir fontes confiáveis.  
**Etapa 3 — Síntese:** solicite uma comparação, explicações e pontos ainda incertos.  
**Etapa 4 — Construção:** crie um quiz de cinco perguntas ou um minissite de revisão usando os resultados verificados.  
**Etapa 5 — Testes:** confira se perguntas, respostas e referências correspondem às fontes.

**Prompt da etapa de construção:**

> Com base exclusivamente no resumo verificado abaixo, crie um quiz interativo de cinco questões de múltipla escolha. Cada pergunta deve explicar a resposta correta após o clique. Use layout simples e responsivo. Não invente fatos nem faça chamadas a serviços externos. Inclua um botão para recomeçar.

**Lição:** a IA pode ajudar em várias etapas do mesmo trabalho: pesquisar, pensar, escrever, visualizar e construir. O segredo é não pular as conferências entre elas.

### Resumo do módulo 3

A IA não é somente um chat de texto. Ela pode receber imagens e arquivos, produzir ilustrações, criar protótipos e ajudar a analisar números. Quanto maior o impacto da tarefa, mais indispensável é verificar o resultado e controlar o acesso a dados e ferramentas.

### Exercícios do módulo 3

**13.** O que significa multimodal?  
**14.** Por que uma foto pode ajudar mais do que uma descrição em texto?  
**15.** Cite cinco partes de um prompt de geração de imagem.  
**16.** Por que começar por um aplicativo pequeno?  
**17.** Qual a diferença entre um gráfico convincente e uma análise correta?  
**18.** Como conferir se a IA executou um cálculo ou apenas o descreveu?

---

# Laboratório — Biblioteca de prompts

Os prompts abaixo são **modelos originais desta apostila**, criados para praticar as técnicas aprendidas. Substitua os campos entre colchetes e não inclua informações confidenciais em ferramentas não autorizadas. O objetivo é observar como a resposta muda com **contexto, critérios, fontes e feedback**.

## Modelo 1 — Aprender qualquer conceito

```text
Explique [conceito] para alguém que está começando.
1. Comece com uma frase muito simples.
2. Use duas analogias do dia a dia.
3. Traga um exemplo em [contexto de interesse].
4. Mostre os limites das analogias.
5. Faça três perguntas curtas para eu conferir se entendi.
Evite jargões sem explicação.
```

**Teste com:** contexto de API, Git, cache, inflação ou astronomia.

## Modelo 2 — Pesquisa atualizada e verificável

```text
Pesquise [pergunta] usando fontes atuais.
Priorize [fontes oficiais adequadas].
Informe a data das evidências, apresente links diretos
para afirmações importantes e explique divergências.
Separe fatos confirmados, interpretações e lacunas.
Não invente informação se não encontrar.
```

**Teste com:** versão atual de uma biblioteca, norma pública ou programação de um evento.

## Modelo 3 — Deep Research para uma decisão

```text
Quero decidir [decisão].
Contexto: [objetivo e cenário].
Restrições: [orçamento, prazo, risco].
Crie um plano de pesquisa com perguntas e critérios.
Consulte fontes variadas, privilegie fontes primárias,
compare alternativas e aponte incertezas.
Entregue uma matriz de decisão, síntese executiva
e uma lista do que precisa ser validado por mim.
```

**Teste com:** escolha de tecnologia ou desenvolvimento de uma habilidade profissional.

## Modelo 4 — Brainstorming com várias rodadas

```text
Preciso resolver [problema].
Tenho [contexto e restrições].
Sugira cinco alternativas diferentes, inclusive uma
mais conservadora e uma mais ousada.
Para cada alternativa, informe vantagem, risco e esforço.
Não escolha ainda: espere meu feedback para refinar.
```

**Segunda mensagem:** “Gostei da 2 pela simplicidade; rejeitei a 3 pelo custo. Misture pontos fortes de 1 e 2 e apresente três novas opções.”

## Modelo 5 — Crítica neutra a uma ideia

```text
Avalie esta proposta sem presumir que é boa ou ruim:
[proposta].
Use os critérios: valor, viabilidade, custo,
riscos, reversibilidade e evidências disponíveis.
Aponte três fragilidades e três condições
que poderiam torná-la mais forte.
Diga quais dados poderiam mudar sua avaliação.
```

**Teste com:** automatizar uma cerimônia do time ou adotar um novo processo.

## Modelo 6 — Escrever sem cair no genérico

```text
Vou escrever para [público] sobre [tema].
Minhas notas: [notas].
Objetivo: [efeito desejado no leitor].
Não escreva a versão final ainda.
Proponha três estruturas com título, tese,
exemplos e um contra-argumento cada.
Marque onde preciso trazer evidências.
Espere minha escolha para expandir.
```

**Segunda mensagem:** “Escolho a estrutura 2. Expanda em tópicos, sem virar prosa.”  
**Terceira mensagem:** “Agora escreva, preserve minha voz e elimine frases vazias.”

## Modelo 7 — Revisão com rubrica

```text
Leia [texto]. Não reescreva tudo ainda.
Avalie de 0 a 5: clareza, concisão,
correção, organização e aderência ao público.
Cite trechos que justificam cada nota.
Sugira três melhorias priorizadas pelo impacto.
Espere minha autorização antes de editar.
```

**Teste com:** um README, uma proposta, um aviso ao time ou um texto de apresentação.

## Modelo 8 — Trabalho com arquivos, com segurança

```text
Quero organizar [pasta autorizada].
Primeiro leia somente os nomes e metadados necessários.
Proponha um plano que mostre antes/depois de cada mudança.
Não exclua, mova ou sobrescreva nada nesta etapa.
Espere minha aprovação explícita e respeite
as permissões e pastas delimitadas.
```

**Importante:** este prompt só pode resultar em operações reais se o aplicativo tiver acesso autorizado à pasta. Faça backup.

## Modelo 9 — Explicar uma imagem sem adivinhar

```text
Analise a imagem anexada.
Separe: (1) o que está visível,
(2) interpretações plausíveis,
(3) pontos ilegíveis ou incertos.
Meu objetivo é [objetivo].
Não invente textos ou números não legíveis.
```

**Teste com:** um fluxograma criado por você ou um quadro branco sem dados sensíveis.

## Modelo 10 — Briefing visual para gerar uma imagem

```text
Crie uma imagem de [assunto] realizando [ação].
Estilo: [estilo].
Ambiente: [local].
Iluminação e cores: [detalhes].
Composição: [enquadramento].
Restrições: [o que não incluir].
Proporção: [ex.: horizontal 16:9].
```

**Teste com:** capa de um caderno de estudo ou convite de aniversário.

## Modelo 11 — Aplicativo simples e testável

```text
Crie um aplicativo de [objetivo].
Usuário principal: [quem].
Entradas: [campos].
Saídas: [resultados].
Regras: [validações e lógica].
Restrições: não usar dados reais nem credenciais.
Primeiro apresente um escopo mínimo.
Depois implemente e mostre como testar casos normais
e casos de erro. Liste o que não está pronto para produção.
```

**Teste com:** quiz, cronômetro de estudo ou calculadora de divisão de contas.

## Modelo 12 — Analisar uma planilha sem se enganar

```text
Analise a planilha anexada para responder:
[pergunta].
Primeiro descreva colunas e unidades.
Verifique ausentes, duplicados e filtros.
Mostre os cálculos e gere um gráfico simples.
Separe observações dos possíveis motivos.
Não infira causalidade sem evidência.
Diga quais números eu devo conferir na fonte.
```

**Teste com:** dados fictícios de vendas ou indicadores sintéticos do time.

## Modelo 13 — Facilitar discussão de arquitetura (extra para equipes)

```text
Sou responsável por discutir [decisão arquitetural].
Contexto: [sistema, restrições e requisitos].
Alternativas: [A, B e C].
Avalie simplicidade, manutenção, riscos, desempenho,
segurança, observabilidade e reversibilidade.
Não favoreça nenhuma opção só porque eu a propus.
Crie uma matriz de trade-offs, sugestões de piloto
e perguntas que a equipe precisa responder.
```

**Experimento:** peça em uma segunda rodada um argumento forte **contra** a alternativa preferida.

## Modelo 14 — Plano de aprendizagem individual (extra)

```text
Quero estudar [assunto] durante [tempo].
Meu nível atual: [nível].
Tenho [minutos] por sessão, [dias] por semana.
Crie etapas pequenas, exercícios práticos e revisão.
Após cada etapa, faça uma pergunta de checagem
e adapte a seguinte ao que eu responder.
Não avance automaticamente se eu ainda estiver confuso.
```

## Modelo 15 — Auditoria de uma resposta da IA (extra)

```text
Revise sua resposta anterior como um auditor.
Liste cinco afirmações importantes.
Para cada uma, diga: evidência apresentada,
incerteza, possível erro e como verificar.
Se houver algum dado sem fonte, identifique-o.
Em seguida, reescreva somente as conclusões
que continuam sustentadas pelas evidências.
```

### Checklist que serve para quase qualquer prompt

Antes de enviar, pergunte a si mesma(o): **(a)** Está claro o objetivo? **(b)** Dei contexto suficiente? **(c)** Defini as restrições? **(d)** Indiquei a fonte correta? **(e)** Sei como conferir a resposta? **(f)** Há algum dado que eu não deveria compartilhar? **(g)** Vale pedir opções ou uma pergunta de esclarecimento antes de agir?

---

# Projeto final — Pesquisa, decisão e aplicativo

## Desafio: criar um pequeno guia interativo de estudo para o time

**Situação fictícia:** uma equipe quer aprender uma ferramenta ou prática nova, mas os materiais estão espalhados. Você precisa propor uma forma simples e verificável de ajudar as pessoas a estudar.

**Entrega 1 — problema e contexto.** Escreva um parágrafo sobre quem vai estudar, o que precisa aprender, o que já sabe e quais restrições existem.

**Entrega 2 — pesquisa.** Defina uma pergunta que precise de fontes externas. Procure documentação oficial, anote datas e produza um resumo de uma página. Registre **três fontes conferidas manualmente**.

**Entrega 3 — ideias.** Peça cinco formas de transformar o material em algo útil. Dê feedback sobre pelo menos duas opções e peça uma segunda rodada de brainstorming.

**Entrega 4 — crítica.** Crie uma rubrica de cinco critérios: clareza, utilidade, esforço, risco de informação errada e facilidade de atualização. Pontue as propostas e registre a decisão.

**Entrega 5 — protótipo.** Peça um quiz simples de cinco perguntas baseado **apenas** nas informações conferidas. Inclua feedback de resposta certa e errada.

**Entrega 6 — verificação.** Teste uma pergunta, um erro proposital, a navegação no celular e a correspondência entre respostas do quiz e fontes.

### Modelo para entregar ao grupo

| Campo | Preencher |
|---|---|
| Problema | Qual dificuldade real queremos reduzir? |
| Público | Quem usará o material? |
| Evidências | Quais fontes conferimos? |
| Alternativas | Quais opções surgiram nas rodadas? |
| Rubrica | Como comparamos as opções? |
| Resultado | O que construímos e testamos? |
| Limites | O que não foi verificado ou automatizado? |
| Próximo passo | Qual experimento pequeno podemos fazer? |

**Critério de conclusão:** não é “a IA fez um aplicativo bonito”. É **“consigo explicar o resultado, conferir as fontes e mostrar que o protótipo funciona”**.

---

# Glossário

| Termo | Em linguagem simples |
|---|---|
| **Prompt** | A instrução, pergunta ou pedido enviado à IA |
| **AI power user** | Pessoa que usa contexto, ferramentas e revisão para obter resultados mais úteis |
| **Modelo** | Sistema treinado para produzir respostas ou outras saídas |
| **Pré-treinamento** | Parte do aprendizado anterior ao uso que você faz do sistema |
| **Data de corte** | Referência temporal após a qual determinados fatos podem não integrar o treinamento |
| **Web search** | Pesquisa na internet para trazer informação adicional |
| **Fonte primária** | Documento ou registro original de uma informação |
| **Deep Research** | Pesquisa extensa com diversas buscas e síntese de fontes |
| **Síntese** | Reunir várias informações em uma explicação coerente |
| **Brainstorming** | Gerar e explorar alternativas antes de escolher |
| **Iteração** | Fazer uma nova rodada usando feedback da rodada anterior |
| **Contexto** | Informações disponíveis para orientar uma resposta |
| **Janela de contexto** | Limite do conteúdo que um sistema consegue considerar em determinado momento |
| **Histórico de chat** | Mensagens anteriores de uma conversa |
| **Ferramenta** | Recurso usado pela IA para pesquisar, calcular, ler ou agir |
| **Agêntico** | Sistema que pode selecionar etapas e ferramentas para avançar numa tarefa |
| **Raciocínio** | Processo de analisar condições e alternativas para chegar a uma resposta |
| **Sicofancia** | Tendência de concordar ou agradar em vez de avaliar criticamente |
| **Rubrica** | Lista de critérios usada para avaliar algo de forma consistente |
| **AI slop** | Conteúdo gerado sem substância, frequentemente genérico ou repetitivo |
| **Esboço** | Estrutura inicial que vem antes do texto completo |
| **Multimodal** | Que usa mais de um formato, como texto e imagem |
| **Entrada / saída** | Informação fornecida ao sistema / resultado produzido |
| **Modelo de difusão** | Tipo de modelo usado em geração de imagens, explicado de modo intuitivo como refinamento a partir de ruído |
| **Protótipo** | Versão pequena criada para experimentar uma ideia |
| **Vibe coding** | Construir software com forte ajuda de IA por meio de instruções em linguagem natural |
| **Insight** | Observação útil que ajuda a entender ou decidir algo |
| **Correlação** | Variação conjunta de fatores, sem demonstrar necessariamente causa |
| **Alucinação** | Resposta incorreta ou inventada apresentada como se fosse verdadeira |
| **Verificação** | Conferência de fatos, números, código e resultados com evidências |

---

# Avaliação — 30 questões

Responda antes de ler o gabarito. As questões pedem aplicação de conceitos, não a memorização de frases das aulas.

## Módulo 1 — Informação

1. O que diferencia uma pergunta curta de um bom processo de prompting?
2. O que significa conhecimento pré-treinado?
3. Por que muitos textos sobre um tema não garantem que a IA esteja certa?
4. Qual é o risco de confiar em informações posteriores ao treinamento do modelo?
5. Que tipo de pergunta costuma pedir web search?
6. Qual a diferença entre fonte primária e comentário de fórum?
7. Para que serve Deep Research?
8. Por que você deveria conferir links citados pela IA?
9. Em qual situação o conhecimento geral do modelo é suficiente como ponto de partida?
10. Reescreva o pedido “me fale das leis de IA” para aumentar a confiabilidade.

## Módulo 2 — Pensamento

11. Como o feedback muda um brainstorming?
12. Por que pedir várias opções pode ser melhor que pedir uma resposta única?
13. Quais são os quatro grupos de contexto apresentados nesta apostila?
14. Quando convém abrir um novo chat?
15. Que cuidados você tomaria antes de autorizar edição de arquivos?
16. Qual é a diferença entre uma recomendação fundamentada e um texto longo?
17. Explique sicofancia com uma frase sua.
18. Como formular uma pergunta sem revelar qual resposta você quer ouvir?
19. Qual é a sequência de escrita progressiva ensinada?
20. Como uma rubrica ajuda na revisão?

## Módulo 3 — Multimídia e construção

21. O que significa multimodalidade?
22. Que cuidado ter ao pedir leitura de uma foto com texto pequeno?
23. Quais informações compõem um bom pedido de imagem?
24. Por que imagens geradas podem exigir revisões mesmo quando parecem bonitas?
25. Qual é um bom primeiro aplicativo para gerar com IA e por quê?
26. O que falta entre um protótipo gerado e uma aplicação segura em produção?
27. Que verificações fazer antes de analisar uma planilha?
28. Explique por que “vendas subiram após uma campanha” não comprova que a campanha causou a alta.
29. Como descobrir se o modelo executou código para calcular os resultados?
30. No projeto final, o que importa mais: aparência do protótipo ou evidências e funcionamento? Justifique.

---

# Gabarito comentado

## Respostas do módulo 1

**1.** O processo inclui objetivo, contexto, ferramentas, critérios, revisão e feedback — não apenas a primeira pergunta.  
**2.** É a bagagem de padrões e informações aprendida no treinamento, anterior à conversa.  
**3.** Frequência não é prova: conteúdos repetidos podem conter erros ou estar desatualizados.  
**4.** O modelo pode não saber ou confundir fatos recentes; é preciso pesquisar e confirmar a data.  
**5.** Notícias, preços atuais, horários, regras recentes, endereços e informações muito específicas.  
**6.** Fonte primária registra diretamente o fato; fórum relata experiências ou interpretações de terceiros.  
**7.** Investigar questões complexas que pedem diversas fontes, comparação e síntese.  
**8.** A citação pode ser antiga, irrelevante ou não sustentar a afirmação citada.  
**9.** Para entender o conceito de fila, cache, fração ou outra noção relativamente estável.  
**10.** Resposta possível: “Pesquise as regras vigentes sobre IA no Brasil, informe as datas, priorize textos legais e órgãos oficiais, com links e ressalvas de aplicação.”

## Respostas do módulo 2

**11.** Ele informa o que gostamos, rejeitamos e quais restrições faltavam, tornando as novas opções mais relevantes.  
**12.** Mostra compromissos distintos; você pode comparar antes de detalhar ou escolher.  
**13.** Objetivo, situação, restrições e evidências.  
**14.** Quando o assunto muda bastante e o histórico anterior pode contaminar ou distrair a resposta.  
**15.** Limitar pasta e permissões, fazer backup, revisar o plano e aprovar mudanças antes de executar.  
**16.** A recomendação fundamentada usa critérios, fontes, incertezas e trade-offs; comprimento sozinho não garante qualidade.  
**17.** É quando a IA procura concordar comigo em vez de avaliar se eu realmente tenho razão.  
**18.** “Compare alternativas usando critérios objetivos, pontos fortes, fracos e evidências, sem presumir a vencedora.”  
**19.** Objetivo/notas → esboço → feedback → tópicos → texto final → revisão.  
**20.** Ela exige avaliar critérios específicos e explicar notas, reduzindo críticas vagas e elogios automáticos.

## Respostas do módulo 3

**21.** Trabalhar com diferentes formatos de informação, como texto, imagens, vídeo, áudio e código.  
**22.** Verificar o original e pedir que o modelo sinalize trechos ilegíveis, sem inventá-los.  
**23.** Assunto, ação/composição, estilo, ambiente/luz e restrições; proporção pode ajudar.  
**24.** Personagens, textos e detalhes podem sair inconsistentes, errados ou inadequados ao uso.  
**25.** Um quiz simples, calculadora ou flashcards: escopo limitado, fácil de testar e refinar.  
**26.** Testes, revisão de código, acessibilidade, segurança, privacidade, manutenção e controles de produção.  
**27.** Verificar significado das colunas, unidades, ausentes, duplicações, períodos e filtros.  
**28.** Pode haver fatores diferentes atuando no mesmo período; correlação temporal não demonstra causa.  
**29.** Pedindo evidências de execução, código, fórmulas e amostras; verificar se a ferramenta de cálculo foi usada.  
**30.** Evidências e funcionamento. O visual ajuda na utilização, mas não substitui dados confiáveis nem testes.

---

# Créditos e próximos passos

**Base de estudo:** [AI Prompting for Everyone — DeepLearning.AI](https://www.deeplearning.ai/courses/ai-prompting-for-everyone), ministrado por **Andrew Ng**. A estrutura desta apostila segue os três módulos oficiais. As explicações foram reescritas de forma independente, em português simples, com base nas transcrições fornecidas para este estudo. As analogias e a biblioteca de prompts foram desenvolvidas como material didático adicional; **não são cópias literais de aulas, slides ou laboratórios oficiais**.

**Não oficial:** este guia não representa, substitui nem é endossado pela DeepLearning.AI ou pelo instrutor. Exemplos de produtos são ilustrativos; recursos podem mudar. Trechos da transcrição automática podem apresentar erros de reconhecimento, especialmente em nomes técnicos; por isso foram priorizados conceitos claramente sustentados e o programa oficial do curso.

**Para continuar estudando:** use esta apostila como segunda etapa após [Inteligência Artificial para Todas as Pessoas — AI for Everyone](../01-ai-for-everyone/AI_FOR_EVERYONE_APOSTILA.md). Depois, pratique com seus próprios dados **não sensíveis**, documente o que funcionou e compartilhe com colegas como reproduzir o resultado.

**Licença:** consulte o arquivo [`LICENSE.md`](../../LICENSE.md) do repositório. Nenhum material original protegido de terceiros — vídeo, slide, imagem ou transcrição integral — é redistribuído aqui.

> **Fórmula para levar para a vida:** dê contexto, peça opções, verifique fontes, critique a resposta, refine e só depois publique ou execute.

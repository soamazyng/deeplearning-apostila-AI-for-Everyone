# IA generativa para todas as pessoas

**Apostila 03 · Generative AI for Everyone**  
*Um guia para entender, experimentar e aplicar IA generativa sem complicação*

**Base de estudo:** curso *Generative AI for Everyone*, de Andrew Ng, publicado pela DeepLearning.AI.  
**Idioma:** português brasileiro · **Nível:** iniciante · **Formato:** explicações, analogias, exemplos, exercícios e gabarito.

> **Material independente e não oficial.** Este guia é uma elaboração didática original baseada na transcrição fornecida para estudo, organizada conforme as três semanas do curso. Não é a transcrição nem uma reprodução dos slides. Exemplos identificados como *exemplo criado para a apostila* e atividades do laboratório são complementos autorais. Produtos, nomes e valores citados no curso refletem o momento em que as aulas foram gravadas: valide recursos, preços e regras atuais antes de tomar decisões.

---

## Como usar esta apostila

Se você acha que precisa entender matemática avançada para aprender IA generativa, temos uma boa notícia: **não precisa**. A ideia é adquirir um modelo mental simples — isto é, uma explicação que ajude você a prever quando a tecnologia é útil, quando pode errar e como usá-la com responsabilidade.

Em cada capítulo, siga quatro passos: **entenda a ideia**, **leia a analogia**, **experimente um exemplo** e **explique com suas palavras**. Se conseguir ensinar um conceito para alguém que nunca usou IA, você provavelmente entendeu de verdade.

**Nossa história-guia (exemplo criado para esta apostila):** imagine uma equipe que recebe dezenas de perguntas sobre políticas, processos e procedimentos internos. Vamos acompanhar, pouco a pouco, como essa equipe pode sair do famoso “pergunta no chat” até um assistente que busca documentos, gera respostas e deixa claro quando não sabe. Não é um projeto implantado; é um cenário fictício para estudo.

### Mapa da jornada

| Semana oficial | O que vamos aprender | Pergunta central |
|---|---|---|
| **1 · Introdução à IA generativa** | O que é, como funciona, aplicações e limites | “Como usar sem acreditar em mágica?” |
| **2 · Projetos de IA generativa** | Construção, custos, RAG, fine-tuning, modelos e ferramentas | “Como transformar uma ideia em um produto útil?” |
| **3 · IA nos negócios e na sociedade** | Tarefas, oportunidades, equipes, riscos e responsabilidade | “Como gerar valor sem deixar pessoas e segurança de lado?” |

### Sumário

1. [Semana 1 — Conhecendo a IA generativa](#semana-1--conhecendo-a-ia-generativa)
   - [1. O que é IA generativa?](#1-o-que-é-ia-generativa)
   - [2. Como um LLM aprende a escrever?](#2-como-um-llm-aprende-a-escrever)
   - [3. Três grandes famílias de tarefas](#3-três-grandes-famílias-de-tarefas)
   - [4. O que a IA faz bem — e o que pode falhar](#4-o-que-a-ia-faz-bem--e-o-que-pode-falhar)
   - [5. Como escrever instruções melhores](#5-como-escrever-instruções-melhores)
   - [6. Como a IA cria imagens](#6-como-a-ia-cria-imagens)
2. [Semana 2 — Construindo projetos](#semana-2--construindo-projetos)
   - [7. Da conversa ao aplicativo](#7-da-conversa-ao-aplicativo)
   - [8. O ciclo de vida de um projeto](#8-o-ciclo-de-vida-de-um-projeto)
   - [9. Tokens, custos e escala](#9-tokens-custos-e-escala)
   - [10. RAG: a IA consulta a biblioteca](#10-rag-a-ia-consulta-a-biblioteca)
   - [11. Fine-tuning: especializando comportamentos](#11-fine-tuning-especializando-comportamentos)
   - [12. Escolhendo um modelo](#12-escolhendo-um-modelo)
   - [13. Instruções, ferramentas e agentes](#13-instruções-ferramentas-e-agentes)
3. [Semana 3 — Trabalho, empresas e sociedade](#semana-3--trabalho-empresas-e-sociedade)
   - [14. Onde a IA ajuda no trabalho](#14-onde-a-ia-ajuda-no-trabalho)
   - [15. Automatize tarefas, não pense apenas em cargos](#15-automatize-tarefas-não-pense-apenas-em-cargos)
   - [16. Reinventando processos](#16-reinventando-processos)
   - [17. Pessoas, funções e governança](#17-pessoas-funções-e-governança)
   - [18. Empregos, riscos e o futuro da IA](#18-empregos-riscos-e-o-futuro-da-ia)
   - [19. IA responsável no dia a dia](#19-ia-responsável-no-dia-a-dia)
4. [Laboratório de prompts e desafios](#laboratório-de-prompts-e-desafios)
5. [Projeto final: assistente de informações confiáveis](#projeto-final-assistente-de-informações-confiáveis)
6. [Revisão de conhecimentos](#revisão-de-conhecimentos)
7. [Gabarito comentado](#gabarito-comentado)
8. [Glossário sem complicação](#glossário-sem-complicação)
9. [Referências, créditos e próximos passos](#referências-créditos-e-próximos-passos)

---

# Semana 1 — Conhecendo a IA generativa

> **Objetivo desta semana:** compreender o que a IA generativa produz, como modelos de linguagem funcionam em uma explicação simplificada, onde ela agrega valor e por que não podemos confiar cegamente em toda resposta.

## 1. O que é IA generativa?

Pense numa **caixa de ferramentas**. Nela, há uma ferramenta para identificar se uma mensagem parece golpe, outra para traduzir uma frase e outra para criar uma ilustração. **Inteligência artificial (IA)** é o grande campo dessas técnicas. **IA generativa** é o conjunto de técnicas especialmente conhecido por **criar conteúdo**: textos, imagens, sons e, em muitos sistemas, vídeos e código.

A palavra *generativa* ajuda a lembrar o verbo **gerar**. Você fornece uma instrução, também chamada *prompt*, e recebe um conteúdo novo como resposta. Esse conteúdo pode parecer muito bem feito sem necessariamente ser verdadeiro.

**Uma analogia simples:** uma calculadora recebe números e executa uma operação bem definida. Um aplicativo de IA generativa é mais parecido com um ajudante que leu muitos exemplos de como as pessoas escrevem e pode produzir uma nova proposta de texto a partir do seu pedido. Ele não conhece automaticamente a política interna da sua empresa, não acessa arquivos privados sem permissão e pode se enganar.

### IA tradicional e IA generativa são a mesma coisa?

Não exatamente. Compare:

| Exemplo | Entrada | Saída | O que ele faz |
|---|---|---|---|
| Filtro de spam | Mensagem de e-mail | “spam” ou “não spam” | Classifica |
| Previsão de clique | Anúncio e características relevantes | Probabilidade de clique | Prevê |
| Gerador de texto | Pedido para escrever um e-mail | Rascunho do e-mail | Gera |
| Gerador de imagens | Descrição de uma cena | Imagem nova | Gera |

O curso apresenta a **aprendizagem supervisionada** — aprender com pares de entrada e saída — como uma base importante de muitos sistemas de IA. A IA generativa amplia o tipo e a complexidade do resultado que podemos pedir.

### Uma tecnologia de uso geral

**A eletricidade não serve apenas para lâmpadas.** Ela move elevadores, geladeiras, computadores e fábricas. Andrew Ng usa essa comparação para explicar por que a IA generativa é uma **tecnologia de uso geral**: não existe uma única finalidade. Pode ajudar a escrever, revisar, classificar, resumir, traduzir, analisar e conversar.

**Exemplo do dia a dia:** a mesma ferramenta pode ajudar você a planejar uma festa, reescrever uma mensagem para torná-la mais clara e estudar um assunto. **Exemplo de equipe:** pode explicar uma documentação técnica, sugerir casos de teste e resumir feedback de usuários. Em ambos os casos, uma pessoa precisa conferir as partes importantes.

### Interface de chat ou IA dentro de um software?

Há duas formas muito comuns de uso:

- **Chat aberto:** você entra em uma interface, descreve o que quer e vê a resposta. É ótimo para aprender, explorar ou produzir rascunhos.
- **Aplicação integrada:** um sistema de software envia solicitações a um modelo automaticamente para executar partes de um processo, por exemplo, categorizar mensagens recebidas.

**Analogia:** pedir ao assistente uma receita em uma conversa é diferente de embutir esse assistente no sistema de pedidos de um restaurante. No segundo caso, é preciso tratar permissões, erros, disponibilidade, custos e integração com outros sistemas.

**Verifique se entendeu:** explique a um colega por que um filtro de spam e um assistente que escreve respostas podem usar IA, embora façam trabalhos diferentes.

## 2. Como um LLM aprende a escrever?

**LLM** é a sigla de *Large Language Model*, ou **grande modelo de linguagem**. É uma das tecnologias por trás de sistemas capazes de produzir textos e responder a perguntas.

Imagine um jogo de completar frases:

> “Hoje, antes de sair de casa, peguei meu...”

Você talvez complete com “casaco”, “celular” ou “guarda-chuva”. Para decidir, usa padrões aprendidos ao ler, ouvir e conversar. Um LLM é treinado, em escala gigantesca, para prever partes seguintes de sequências de texto. Na prática, essas partes são chamadas de **tokens**, que podem ser palavras, pedaços de palavras ou sinais.

**Como acontece o aprendizado, numa versão simplificada:**

1. O treinamento usa muitos textos.
2. O sistema recebe um trecho inicial.
3. Tenta prever o próximo token.
4. Compara sua previsão com o que aparece nos exemplos e ajusta os parâmetros do modelo.
5. Repete isso incontáveis vezes.

Exemplo didático:

| Contexto fornecido | Continuação de referência |
|---|---|
| “A receita pede duas” | “xícaras” |
| “A receita pede duas xícaras de” | “leite” |
| “A receita pede duas xícaras de leite” | “e” |

Depois do treinamento, o modelo pode produzir continuações e respostas que nunca estavam escritas exatamente daquela forma no material de treino.

### Então é só um corretor automático gigante?

A comparação ajuda a começar, mas é **incompleta**. O curso utiliza a previsão do próximo token como uma forma intuitiva de entender os LLMs. Sistemas usados como assistentes passam também por etapas adicionais de treinamento e ajustes para seguir instruções e reduzir comportamentos inadequados. Essa explicação básica não descreve todos os mecanismos de modelos modernos.

### Por que o tamanho e os dados importaram?

O curso conta como **dados em maior escala, modelos maiores e máquinas mais potentes** contribuíram para melhorias importantes. Imagine estudar para uma prova: ter mais material pode ajudar, mas você também precisa de capacidade para processar aquele material. Não adianta despejar milhares de livros num armário e esperar que ele aprenda.

**Alerta:** “maior” não significa automaticamente “melhor para qualquer tarefa”. Modelos diferentes podem variar em qualidade, velocidade, custo, privacidade e adequação a uma aplicação.

### Por que a resposta muda quando repetimos a pergunta?

O modelo pode escolher continuações alternativas que parecem plausíveis. Por isso, duas solicitações iguais podem produzir textos diferentes. Pense num cozinheiro capaz de inventar três versões de uma receita com os mesmos ingredientes. **Variedade** é interessante para criação; **consistência e verificabilidade** são essenciais quando a saída vira parte de um processo de negócio.

**Verifique se entendeu:** um LLM que escreve uma data com muita confiança necessariamente a verificou numa fonte oficial? **Não.** Fluência e verificação são coisas diferentes.

## 3. Três grandes famílias de tarefas

O curso apresenta uma estrutura fácil de memorizar: **escrever, ler e conversar**.

### Escrever: produzir um texto

A pessoa fornece um pedido e o modelo gera algo novo. Exemplos: lista de ideias, e-mail, comunicado, tradução e versões alternativas de uma mensagem.

**Analogia:** como pedir a um colega um primeiro rascunho para depois vocês melhorarem juntos.

**Exemplo criado:** “Escreva três opções de convite para a reunião de revisão da sprint: uma curta, uma amigável e uma formal. Não invente data nem horário.” Você recebe alternativas e decide qual serve melhor.

### Ler: receber muito conteúdo e devolver uma síntese

É o caso de resumir um artigo, revisar gramática, reconhecer o sentimento de uma avaliação ou classificar uma solicitação. A entrada pode ser longa e a resposta, curta.

**Analogia:** você pede que alguém leia 20 bilhetes e separe em três pilhas: agradecimentos, dúvidas e reclamações.

**Exemplo criado:** um atendimento recebe “Comprei o produto e a entrega atrasou dois dias”. O modelo devolve **tipo: reclamação sobre entrega**. Isso pode ajudar a direcionar a mensagem, desde que a lista de categorias seja conhecida e o resultado seja validado.

### Conversar: manter uma troca de mensagens

Aqui, o sistema responde a perguntas e ajusta o diálogo com base no que já foi informado. Pode atuar num assistente geral ou num atendimento especializado.

**Analogia:** numa livraria, o atendente pergunta que gênero você prefere antes de sugerir o livro. Num chatbot, a conversa fornece contexto para respostas mais relevantes.

### Por que as três categorias importam?

Elas ajudam a enxergar oportunidades que passariam despercebidas. Um processo pode ter uma etapa de **leitura** para classificar uma solicitação, outra de **escrita** para preparar uma resposta, e uma etapa de **conversa** para esclarecer dúvidas.

| Rotina | Tarefa de IA | Cuidados |
|---|---|---|
| Reunião de equipe | Resumir decisões | Conferir nomes, decisões e responsáveis |
| Reclamação de cliente | Categorizar assunto | Não criar categorias inexistentes |
| Documentação técnica | Explicar um trecho | Conferir versão e fonte |
| Onboarding de pessoas | Responder dúvidas frequentes | Usar regras atualizadas e autorizadas |
| Relatório de resultados | Escrever um primeiro rascunho | Não inventar números nem conclusões |

**Exemplo da história-guia:** nosso assistente interno primeiro **lê** a pergunta de uma pessoa, depois **consulta** as informações autorizadas e finalmente **escreve** uma resposta clara. Se não encontrar a regra, precisa saber dizer: “Não encontrei esta informação nos documentos disponíveis”.

## 4. O que a IA faz bem — e o que pode falhar

A parte mais importante de aprender IA talvez seja desenvolver a habilidade de dizer **“isso é um bom caso de uso”** ou **“isso exige cuidado”**.

### O teste do recém-formado

Andrew Ng sugere uma pergunta prática: **uma pessoa recém-formada, inteligente e esforçada, conseguiria realizar essa tarefa apenas com as instruções e informações que recebeu?**

- “Leia esta mensagem e diga se é elogio ou reclamação.” Provavelmente sim.
- “Resuma este artigo em cinco linhas.” Provavelmente sim.
- “Diga qual regra interna de 2026 aprova essa exceção, sem que eu forneça documentos.” Provavelmente não: faltam informações.
- “Decida sozinho uma questão complexa que exige responsabilidade profissional, dados confiáveis e contexto específico.” Talvez não de forma segura.

Essa comparação é uma **regra prática do curso**, não uma garantia de desempenho nem um teste científico universal. Hoje existem tarefas que os modelos realizam melhor ou pior do que um recém-formado. A ideia central é: **a tarefa tem instruções suficientes e um critério claro de acerto?**

### Alucinação: quando a IA inventa algo convincente

Uma **alucinação** é uma resposta gerada que contém informação falsa ou sem suporte nas fontes disponíveis. O problema é que ela pode soar natural e segura.

**Analogia:** uma pessoa que não lembra o nome de um livro, mas inventa um título plausível para não ficar sem responder. O resultado pode parecer real — e não ser.

**Para reduzir riscos:** peça fonte verificável, forneça documentos confiáveis, determine que a IA identifique lacunas e confira diretamente o material original nas decisões importantes. RAG ajuda a fornecer fontes, mas **não elimina** alucinações.

### Outras limitações importantes

- **Informação insuficiente:** o modelo não sabe detalhes que você não forneceu ou que não estão acessíveis.
- **Informação desatualizada:** fatos, produtos, preços e regras mudam; conhecimento de treinamento pode envelhecer.
- **Ambiguidade:** “faça a melhor resposta” não diz para quem, com qual objetivo nem com que critério.
- **Vieses:** padrões aprendidos podem reproduzir preconceitos ou associações injustas.
- **Restrições de contexto:** existe um limite para a quantidade de conteúdo que pode ser considerada em uma interação.
- **Saídas inadequadas:** respostas podem violar formatos, misturar informações ou conter falhas de raciocínio.

### Quando confiar menos

Imagine três perguntas:

1. “Invente um slogan para uma cafeteria.” **Risco geralmente baixo**: criatividade é desejada.
2. “Resuma este documento com os pontos principais.” **Risco intermediário**: confira omissões e fatos importantes.
3. “Aplique uma regra regulatória para aprovar um caso real.” **Risco alto**: exige fontes oficiais, regras atualizadas, validação humana e controles adequados.

**Regra simples:** quanto mais cara, irreversível ou sensível for a consequência, maior deve ser a exigência de verificação e supervisão.

## 5. Como escrever instruções melhores

O curso destaca três recomendações: **ser específico, orientar a análise e iterar**.

### Dica 1 — Seja específico

Prompt fraco: “Escreva um e-mail.”

Prompt melhor: “Escreva um e-mail de até 130 palavras para convidar cinco colegas a uma reunião de troca de aprendizados sobre IA. Tom amigável. Explique que cada pessoa levará um exemplo de uso e uma dificuldade. Não invente a data. Entregue também três opções de assunto.”

Quanto melhor o contexto, maior a chance de o resultado ser útil. Especificidade não significa escrever um tratado: significa incluir o que **muda a resposta**.

### Dica 2 — Oriente o trabalho

Para uma decisão, peça comparação com critérios observáveis e identificação de dúvidas. Exemplo: “Compare as duas opções quanto a custo, esforço de adoção, dependências e riscos. Mostre o que está comprovado e o que é hipótese. Antes de recomendar, indique quais dados faltam.”

Em tarefas difíceis, instruções como “analise cuidadosamente” podem ajudar a comunicar a necessidade de esforço; porém, **não substituem** critérios, dados, ferramentas ou validação.

### Dica 3 — Experimente e refine

Pedir algo, observar a saída e ajustar a instrução faz parte do processo. Pense num corte de cabelo: você descreve o estilo, vê uma referência e ajusta os detalhes. Com IA, o ciclo pode ser rápido:

**pedido inicial → primeira resposta → feedback específico → nova versão → conferência final.**

**Exemplo criado:** “O resumo ficou longo demais. Reescreva em quatro bullets. Preserve os dois riscos identificados e não acrescente conclusões que não estejam no texto.”

### Um molde útil para quase tudo

```text
Objetivo: [o que preciso conseguir]
Contexto: [situação e público]
Material de referência: [documento, dados ou texto]
Restrições: [o que não fazer]
Formato de saída: [tabela, passos, e-mail etc.]
Critério de qualidade: [como avaliarei a resposta]
Se faltarem fatos relevantes, identifique as lacunas.
```

**Atenção a dados corporativos:** não envie informações pessoais, dados de clientes, código sigiloso ou documentos internos a serviços não aprovados pela sua organização. Use versões fictícias ou anonimizadas para exercícios.

## 6. Como a IA cria imagens

A transcrição apresenta a **geração de imagens** como um conteúdo opcional e usa uma explicação intuitiva dos **modelos de difusão**.

Imagine uma fotografia que fica cada vez mais encoberta por ruído, como se alguém espalhasse inúmeros pontos aleatórios sobre ela. Durante o treinamento, o sistema aprende padrões úteis para **remover ruído** e recuperar características de imagens. Ao gerar uma nova imagem, ele parte de uma representação com ruído e realiza diversas etapas de transformação orientadas pela descrição fornecida.

**Analogia:** uma escultura aparece pouco a pouco conforme o artista retira material que está atrapalhando. A comparação não é literal, mas ajuda a imaginar uma imagem surgindo por refinamentos sucessivos.

**Exemplo criado:** “Crie uma ilustração de uma biblioteca acolhedora, com um gato dormindo ao lado de uma luminária, estilo aquarela suave, sem palavras escritas.”

### Multimodal: mais de um tipo de informação

Um sistema **multimodal** pode trabalhar com mais de uma modalidade — por exemplo, texto e imagem. Nem todo sistema oferece todas as funções, e modelos de imagem e linguagem podem usar arquiteturas e processos diferentes.

**Cuidados práticos:** peça consentimento para usar rostos e vozes de pessoas, não confunda imagem sintética com fotografia de um evento real, evite estereótipos, revise direitos de uso e não use imagens inventadas como evidência factual.

### Atividade rápida da semana 1

Escolha uma tarefa simples, como preparar um aviso para uma reunião. Crie uma primeira versão com um pedido de cinco palavras e outra com objetivo, público, formato e restrições. Compare: **qual foi mais útil? Por quê?** Depois, pegue uma afirmação factual da resposta e confirme sua fonte.

**Resumo da semana:** IA generativa é uma tecnologia de uso geral; LLMs aprendem padrões de texto e passam por ajustes adicionais; escrever, ler e conversar são três famílias úteis de tarefas; boas instruções ajudam, mas não eliminam erros; e o nível de verificação deve acompanhar o risco.

---
# Semana 2 — Construindo projetos

> **Objetivo desta semana:** entender como sair do uso individual de um chat para uma aplicação que realiza tarefas repetidas com segurança, e conhecer tecnologias que ampliam o que os modelos conseguem fazer.

## 7. Da conversa ao aplicativo

Você já usou IA para classificar uma mensagem? Talvez tenha colado um comentário no chat e perguntado: “Esse texto é positivo ou negativo?”. Funcionou? Ótimo. Agora imagine receber **dez mil avaliações** por mês. Copiar e colar uma por vez não é um bom plano.

**É aqui que entra um aplicativo de software que utiliza LLM.** Em vez de depender de uma pessoa repetindo o mesmo prompt manualmente, o software envia pedidos ao modelo e usa o resultado dentro de um processo.

### Exemplo do curso: reputação de um restaurante

Um restaurante quer acompanhar o sentimento dos clientes. O sistema recebe avaliações e as classifica como positivas ou negativas. Depois, uma aplicação pode contar quantas avaliações há em cada grupo, construir um gráfico e observar mudanças ao longo do tempo.

**Fluxo conceitual:**

```text
Avaliação do cliente
        ↓
Aplicação recebe a mensagem
        ↓
Prompt: classifique como POSITIVO ou NEGATIVO
        ↓
Modelo devolve uma classificação
        ↓
Software valida a saída e registra o resultado
        ↓
Dashboard mostra uma tendência
```

**O que é importante perceber?** O modelo é apenas uma parte do sistema. Ainda precisamos de entrada de dados, validação, tratamento de falhas, armazenamento quando apropriado, autorização de acesso e medição do resultado.

### Por que ficou mais fácil construir certos aplicativos?

Antes, criar uma ferramenta específica de classificação normalmente exigia **coletar muitos exemplos, rotular dados e treinar um modelo especializado**. O curso compara esse processo com um caminho que permite usar um modelo de linguagem existente e orientar a tarefa por meio de prompts. Esse segundo caminho pode reduzir o esforço inicial e permitir protótipos mais rápidos.

Isso **não** significa que toda tarefa ficou trivial, nem que o modelo dispensará avaliação. Para certas demandas, uma regra simples de software ou um modelo especializado pode continuar mais adequado.

### Nosso caso da equipe

A equipe fictícia quer classificar dúvidas que chegam ao canal de suporte interno. Uma primeira versão do sistema poderia receber perguntas e categorizá-las como `ACESSO`, `AMBIENTE`, `PROCESSO` ou `OUTROS`.

**Uma decisão importante:** informe exatamente as categorias possíveis. Caso contrário, o modelo pode inventar uma categoria chamada “Reclamações”, embora esse grupo não exista no seu sistema.

**Experimento sugerido:** crie dez mensagens fictícias, classifique-as manualmente e depois peça que a IA use somente as quatro categorias. Compare os resultados; registre onde surgiram dúvidas.

## 8. O ciclo de vida de um projeto

Uma aplicação de IA generativa não fica pronta só porque respondeu corretamente a três perguntas. O curso apresenta um ciclo **iterativo** — isto é, um processo de experimentação, avaliação e melhoria.

### As etapas básicas

**1. Definir o escopo.** Escolha uma tarefa concreta: “Classificar avaliações” é muito mais claro do que “Usar IA em todo o atendimento”. Declare quem utilizará, qual problema será resolvido e como saberemos se deu certo.

**2. Construir um protótipo.** Faça a menor versão útil para testar a ideia. Muitas vezes é possível começar com poucos exemplos e um prompt, sem desenvolver a aplicação inteira.

**3. Avaliar com exemplos reais autorizados ou fictícios representativos.** Separe casos simples, ambíguos e difíceis. Compare com resultados de referência. Identifique padrões de erro.

**4. Melhorar e repetir.** Ajuste instruções, fontes, formato de saída, modelo ou arquitetura. Avalie novamente; não presuma que a alteração resolveu o problema.

**5. Colocar em uso com controles.** Configure logs apropriados, permissões, segurança, monitoramento, revisão humana quando exigida e um caminho para interromper ou reverter o serviço.

**6. Acompanhar mudanças.** Demandas, documentos e usuários mudam. Um bom resultado no primeiro dia não garante qualidade no mês seguinte.

```text
Escopo → Protótipo → Avaliação → Melhoria
                ↑                ↓
                ←  nova rodada ←
                        ↓
               Uso controlado
                        ↓
                  Monitoramento
```

### O que é uma avaliação útil?

Imagine um professor que corrige provas. Não basta dizer “a classe parece ter aprendido”. Ele precisa de **questões, respostas esperadas e critérios**. Para uma aplicação com LLM, fazemos algo parecido.

**Exemplo fictício com 20 mensagens:**

| Indicador | Resultado inventado | Interpretação |
|---|---:|---|
| Mensagens avaliadas | 20 | Amostra pequena; não representa produção |
| Classificações corretas | 17 | 85% de acerto neste conjunto |
| Classificações incorretas | 3 | Analisar erro por erro |
| Mensagens ambíguas | 4 | Avaliar se precisa de categoria “REVISÃO” |

Os números acima são **hipotéticos**, não resultados do curso. A simples porcentagem de acertos também não basta: é preciso analisar **o custo dos erros**. Classificar equivocadamente uma sugestão é diferente de negar um direito ou aprovar uma operação sensível.

### Exemplo de critérios de aceitação

- A saída deve ser uma categoria da lista permitida.
- Se a mensagem não for compreensível, o sistema deve indicar revisão.
- O modelo não deve inventar políticas internas nem nomes de equipes.
- O mesmo conjunto de testes deve ser rodado após mudanças importantes.
- Uma pessoa deve conseguir investigar um resultado sem expor dados confidenciais indevidamente.

**Lembrete para engenharia:** não é só um *prompt bonito*. É um serviço com requisitos funcionais, não funcionais, testes e decisões de risco.

## 9. Tokens, custos e escala

A maioria dos serviços de LLM para desenvolvedores calcula parte do consumo com base em **tokens**. Um token pode ser uma palavra pequena, parte de uma palavra, pontuação ou outro fragmento. Não existe uma equivalência universal do tipo “uma palavra = um token”. A divisão depende do modelo e do idioma.

### Uma analogia com o consumo de água

Se sua casa paga pela água usada, uma torneira aberta por alguns segundos custa pouco. Mas, multiplicando pequenos consumos por milhares de casas todos os dias, o total fica relevante. Com IA é semelhante: **uma resposta pode ser barata, milhões de respostas exigem planejamento**.

Um cálculo didático é:

**Custo aproximado = tokens de entrada × preço de entrada + tokens de saída × preço de saída**, considerando as unidades tarifadas pelo fornecedor.

> **Atenção:** valores e nomes de modelos apresentados nas aulas são exemplos históricos, não tabelas de preços atuais. Tarifas, janelas de contexto, descontos, mecanismos de cache e cobrança por ferramentas podem mudar. Consulte sempre a documentação comercial vigente antes de orçar um produto.

### Exemplo fictício de estimativa

Imagine que um fornecedor inventado cobre R$ 2 por **um milhão de tokens de entrada** e R$ 8 por **um milhão de tokens de saída**. Cada solicitação envia em média 2.000 tokens e recebe 500. Para 10.000 solicitações:

- Entrada: 20 milhões de tokens → R$ 40.
- Saída: 5 milhões de tokens → R$ 40.
- Total ilustrativo: **R$ 80 em tokens**.

Os preços são inteiramente inventados para ensinar a conta. **Não representam uma cotação real.** O valor do produto inclui muito mais: desenvolvimento, infraestrutura, observabilidade, segurança, avaliações, suporte e manutenção.

### Custos não são só dinheiro

Considere também a **latência** (tempo para responder), o consumo de recursos, a confiabilidade e a experiência do usuário. Uma aplicação que custa poucos centavos, mas demora demais ou devolve respostas erradas, pode ser cara para a operação.

**Pergunta para refletir:** é melhor pagar um pouco mais por uma resposta de qualidade ou economizar com uma resposta que precisa ser reprocessada? A resposta depende da tarefa e deve ser testada.

## 10. RAG: a IA consulta a biblioteca

**RAG** vem de *Retrieval-Augmented Generation*, traduzido como **Geração Aumentada por Recuperação**. O nome parece complicado; a ideia é simples: **antes de responder, o sistema procura informações relevantes em fontes disponibilizadas para a tarefa**.

### A analogia da prova com consulta

Pense em duas situações:

- **Sem consulta:** a pessoa tenta responder usando o que lembra.
- **Com consulta:** a pessoa procura o capítulo adequado no livro, lê a parte relevante e então responde.

O RAG segue a segunda lógica. Ele ajuda o modelo a usar informações que talvez não estejam em seu conhecimento de treinamento — como uma política da empresa — sem exigir necessariamente que você treine novamente um modelo.

### As três etapas do RAG

**1. Recuperar:** localizar documentos ou trechos relacionados à pergunta.

**2. Acrescentar contexto:** entregar os trechos encontrados ao modelo junto com a pergunta.

**3. Gerar:** produzir uma resposta apoiada nesse contexto.

```text
Usuária: “Posso reservar a sala de reuniões?”
                 ↓
Buscador encontra política de reservas
                 ↓
Modelo recebe pergunta + trechos autorizados
                 ↓
Resposta: “Segundo a política X, ...”
                 ↓
Usuária confere a referência citada
```

### Exemplo prático: nosso assistente interno

Pergunta: “Qual é o prazo para solicitar acesso a um sistema?”

- **Sem documentos:** o modelo pode não saber e até arriscar uma resposta.
- **Com RAG:** o sistema busca a política de acessos e pode responder com base no trecho encontrado.
- **Se a política não existir ou estiver desatualizada:** o aplicativo deve sinalizar a falta de evidência e orientar a pessoa a consultar o responsável.

### Por que RAG não resolve tudo?

Um buscador pode recuperar o trecho errado, deixar de encontrar a informação certa ou trazer uma versão antiga. O modelo também pode interpretar mal o material recebido.

**Controles recomendados:** documentos atualizados, permissões preservadas na busca, indicação de fonte/versão, testes de recuperação, resposta de “não encontrei” e revisão de resultados de maior risco. Nunca deixe que um usuário acesse pelo chatbot um documento ao qual não teria permissão de acesso.

### RAG e mecanismo de busca são a mesma coisa?

São relacionados, mas não idênticos. O **buscador** encontra material. O **LLM** ajuda a organizar a resposta usando o material encontrado. O curso também mostra aplicações que permitem conversar com PDFs, artigos de sites e bases internas.

**Quando pensar em RAG:** quando a pergunta precisa de **informações atualizáveis e específicas**, como manuais, políticas, catálogo de produtos ou conteúdo autorizado da sua organização.

## 11. Fine-tuning: especializando comportamentos

**Fine-tuning**, ou **ajuste fino**, é uma maneira de adaptar um modelo já treinado com exemplos adicionais. Pense em uma pessoa que já sabe cozinhar, mas faz um curso específico de panificação para desenvolver uma especialidade.

Na explicação do curso, o ajuste fino pode ajudar o modelo a:

- adotar um **estilo consistente** de resposta;
- trabalhar melhor com **linguagens e documentos de um domínio**, como textos jurídicos;
- realizar uma tarefa específica com um modelo menor, dependendo do caso.

O processo costuma exigir **dados de treinamento preparados**, execução de treinamento e avaliação da versão ajustada. Ele é diferente de simplesmente enviar um prompt.

### RAG e fine-tuning: a diferença essencial

| Pergunta | RAG | Fine-tuning |
|---|---|---|
| Ideia principal | Consultar informações na hora de responder | Ajustar o comportamento do modelo com treinamento |
| Analogia | Prova com consulta | Curso de especialização |
| Exemplo adequado | Buscar políticas que mudam com frequência | Aprender um estilo ou padrão de saída específico |
| Atualização de fatos | Atualizar a fonte consultada | Pode exigir atualização de treinamento; não é ideal como único repositório de fatos |
| Principal risco | Recuperar fonte errada ou sem permissão | Treino insuficiente, custo e comportamento inesperado |

**Importante:** a transcrição apresenta a possibilidade de usar fine-tuning para conhecimento especializado. Na prática, isso **não garante** memorização fiel nem atualização automática de fatos. Para responder a perguntas sobre documentos que mudam, RAG costuma ser o ponto de partida mais natural; o melhor desenho depende de testes.

### Quando NÃO começar por fine-tuning

Se a sua necessidade é “quero que o assistente leia a política recém-publicada”, começar pelo ajuste fino provavelmente complica o problema. Primeiro pergunte se basta entregar a política no contexto ou usar uma busca com RAG.

**Na história-guia:** começamos com instruções claras e RAG. Só pensaríamos em ajuste fino se uma avaliação repetida mostrasse uma lacuna concreta que essa técnica pudesse resolver.

## 12. Escolhendo um modelo

Imagine comprar um veículo. Um carro pequeno pode ser ótimo para a cidade; um caminhão faz sentido para transportar carga. Não existe um “melhor para tudo” sem considerar a necessidade. Com LLMs, a escolha também depende dos requisitos.

O curso discute modelos com **tamanhos diferentes** e opções mais abertas ou mais fechadas. Modelos maiores frequentemente conseguem lidar com tarefas mais complexas, mas podem demandar mais recursos; modelos menores podem atender muito bem tarefas simples. O tamanho isolado não é um placar definitivo de qualidade.

### Sete critérios úteis

| Critério | Pergunta simples |
|---|---|
| Qualidade | Acerta os casos que realmente importam? |
| Latência | Responde na velocidade necessária? |
| Custo | O preço por uso cabe no orçamento e na escala? |
| Segurança | O tratamento de dados segue as regras da organização? |
| Disponibilidade | O serviço é estável e há plano de contingência? |
| Integração | O modelo funciona com as ferramentas e o formato exigidos? |
| Manutenção | Existe uma equipe capaz de operar e atualizar a solução? |

### Aberto ou fechado?

O curso diferencia modelos cujo acesso é oferecido por fornecedores por meio de serviços e modelos que podem estar disponíveis para implantação e adaptação mais independente. **“Aberto” não significa automaticamente gratuito, sem restrições ou permitido para qualquer uso.** Confira licenças, requisitos de infraestrutura e políticas de dados.

### A abordagem prudente

**Comece com uma tarefa e um conjunto de testes.** Compare duas ou três opções quanto a qualidade, custo, velocidade e segurança. Não escolha pelo nome mais famoso, nem suponha que toda atualização de modelo melhorará seu caso de uso.

### Pequena matriz de decisão fictícia

| Candidato | Exatidão nos testes | Velocidade | Custo | Decisão preliminar |
|---|---|---|---|---|
| Modelo A | Boa | Rápido | Baixo | Testar em piloto |
| Modelo B | Excelente | Lento | Alto | Reservar para casos difíceis |
| Modelo C | Regular | Muito rápido | Baixo | Não aprovar ainda |

*Os rótulos são fictícios e ilustram o método, não uma comparação entre produtos atuais.*

## 13. Instruções, ferramentas e agentes

Se um LLM aprendesse apenas a completar texto, por que ele consegue **seguir instruções** como “resuma em cinco frases”? O curso apresenta etapas adicionais de treinamento e alinhamento para tornar modelos mais úteis, capazes de seguir instruções e, tanto quanto possível, evitar saídas inadequadas. Uma das famílias de técnicas discutidas é o **aprendizado por reforço a partir de feedback humano (RLHF)**.

**Analogia:** aprender um idioma lendo livros é uma coisa. Aprender a prestar atendimento exige também praticar pedidos reais e receber feedback sobre o que foi bom ou ruim.

### O que significa usar ferramentas?

Um modelo pode **solicitar a execução de uma ferramenta externa** — por exemplo, calculadora, buscador ou sistema de pedidos. O software verifica a solicitação, decide se ela é permitida e devolve o resultado ao modelo.

**Exemplo criado:** “Quanto custa um pedido com três itens de R$ 12,50 e entrega de R$ 7?” Em vez de confiar em um cálculo escrito pelo modelo, a aplicação pode mandar a conta para uma ferramenta de cálculo e usar o resultado conferido: **R$ 44,50**.

**Exemplo do curso:** uma aplicação de pedido de comida pode usar uma ferramenta para registrar o pedido num sistema, em vez de apenas escrever “pedido realizado” sem executar nada.

### Ferramentas e agentes: não confunda

- **Uso de ferramenta:** o modelo pede uma operação específica, como calcular, pesquisar ou consultar um sistema.
- **Agente:** um sistema que pode planejar e executar uma sequência de etapas, escolhendo ações conforme observa resultados intermediários.

**Analogia:** pedir a alguém para telefonar ao fornecedor é uma ação. Pedir que organize um evento envolve descobrir fornecedores, comparar preços, reservar, avisar convidados e ajustar o plano. A segunda tarefa exige muito mais coordenação e controle.

### O que um agente NÃO deve ganhar automaticamente?

Acesso irrestrito a arquivos, credenciais, aprovações financeiras, exclusões ou modificações em produção. Quanto mais autonomia, maior a necessidade de **escopo, observabilidade, limites, autorização e possibilidade de reversão**.

Para operações com efeito no mundo real, prefira:

1. **Propor** o plano.
2. **Avaliar** riscos e permissões.
3. **Aprovar** ações sensíveis.
4. **Executar** apenas o permitido.
5. **Registrar** o que aconteceu e como reverter quando possível.

O curso apresenta agentes como uma direção promissora, mas alerta que confiabilidade e segurança são fundamentais. Não transforme demonstrações impressionantes em garantia de operação sem supervisão.

### Atividade rápida da semana 2

No cenário fictício de um assistente interno, responda:

- Quais dúvidas podem ser resolvidas com um prompt simples?
- Quais exigem RAG e documentos atualizados?
- Quais deveriam ser encaminhadas para uma pessoa?
- Quais ações externas exigiriam confirmação antes de executar?

**Resumo da semana:** um produto com LLM precisa de software, testes, custos e monitoramento. RAG recupera informações, fine-tuning adapta o modelo, e ferramentas/agentes ampliam capacidades — sempre com controle compatível com o risco.

---
# Semana 3 — Trabalho, empresas e sociedade

> **Objetivo desta semana:** aprender a enxergar oportunidades concretas, reorganizar tarefas, formar equipes e decidir onde a IA deve ou não ser usada.

## 14. Onde a IA ajuda no trabalho

É fácil pensar em IA como “uma ferramenta que escreve e-mails”. O curso mostra que, por ser uma tecnologia de uso geral, ela pode apoiar funções muito diferentes.

**No marketing**, ajuda a criar versões de campanhas para serem testadas. **Em atendimento**, pode resumir interações e classificar solicitações. **Em recursos humanos**, pode apoiar rascunhos e respostas a dúvidas frequentes com fontes aprovadas. **Na engenharia de software**, pode explicar código, resumir requisitos e sugerir testes — sujeitos a revisão. **Na gestão**, pode organizar ideias, comparar opções e ajudar a estruturar uma decisão.

A diferença entre uma aplicação útil e uma promessa vazia é simples: **qual trabalho específico melhora e como saberemos?**

### O método “observe um dia normal”

Faça um pequeno exercício: anote as tarefas que você executou ontem. Para cada uma, pergunte:

- Houve **leitura repetitiva** de textos ou documentos?
- Houve **produção recorrente** de rascunhos?
- Houve **busca demorada** por informações já registradas?
- Houve uma **conversa padronizada** que poderia ser parcialmente atendida?

Depois avalie: o trabalho é frequente? Existe critério claro? Há dados confiáveis? Uma falha pode causar dano?

### Exemplo criado: uma retrospectiva de squad

Uma liderança recebe notas curtas de uma retrospectiva. A IA poderia ajudar a agrupar temas repetidos: “ambiente instável”, “demora em homologação” e “requisitos pouco claros”. O resultado é um **ponto de partida para discussão**, e não uma explicação automática das causas. Pessoas da equipe devem conferir se o agrupamento representa corretamente suas opiniões.

**Cuidado com métricas:** uma IA pode escrever uma conclusão elegante sobre produtividade sem dados suficientes. Solicite que distinga **observações, hipóteses e recomendações**.

## 15. Automatize tarefas, não pense apenas em cargos

Um dos insights mais úteis da terceira semana é: **pense em tarefas, não em profissões inteiras**.

Um cargo é um conjunto de atividades. Uma pessoa de atendimento pode responder perguntas, registrar pedidos, avaliar reclamações, acalmar clientes e encaminhar casos delicados. Algumas dessas tarefas são mais fáceis de apoiar com IA do que outras.

**Analogia doméstica:** comprar uma lava-louças automatiza parte do trabalho de cuidar da cozinha. Não significa que ela planeje refeições, compre mantimentos ou receba convidados. A tarefa muda; o conjunto de responsabilidades da casa continua maior.

### Passo 1 — Quebre a função em atividades

Exemplo inventado de rotina de uma equipe de engenharia:

| Tarefa | IA pode apoiar? | Onde manter revisão humana? |
|---|---|---|
| Resumir uma reunião gravada com permissão | Sim, como rascunho | Conferir decisões e responsáveis |
| Rascunhar casos de teste | Sim | Revisar cobertura e comportamento de negócio |
| Localizar documentação | Sim, com busca autorizada | Conferir fontes e versão |
| Aprovar mudança crítica de produção | Apenas apoio à análise | Decisão e autorização formal |
| Resolver conflito interpessoal | Pode ajudar na preparação | Mediação humana e contexto |

### Passo 2 — Separe aumento de capacidade e automação

**Aumento de capacidade (*augmentation*):** a IA ajuda uma pessoa a realizar melhor seu trabalho. Por exemplo, preparar um resumo que a pessoa revisa.

**Automação:** o sistema executa uma etapa com menor intervenção humana, como classificar automaticamente mensagens de baixa criticidade e encaminhá-las para a fila correta.

Os dois caminhos podem coexistir. O melhor não é sempre o mais automático: depende do risco, da qualidade dos resultados e da experiência de quem usa.

### Passo 3 — Priorize por valor, facilidade e risco

Considere cada tarefa em três dimensões:

- **Valor:** quanto tempo, qualidade ou capacidade de atendimento pode melhorar?
- **Viabilidade:** existem dados, integrações e critérios de teste?
- **Risco:** o erro é detectável, reversível e aceitável?

Comece por tarefas **úteis, repetidas, avaliáveis e de risco administrável**. Não é preciso começar pelo problema mais espetacular.

### Exemplo de pontuação didática

Dê notas de 1 a 5 para valor e viabilidade; dê nota de 1 a 5 para risco, em que 5 significa risco alto. Um critério simples, **apenas para discussão**, é: `prioridade = valor + viabilidade − risco`. Não use essa fórmula para dispensar avaliações de segurança ou obrigações legais.

| Tarefa fictícia | Valor | Viabilidade | Risco | Pontuação didática |
|---|---:|---:|---:|---:|
| Rascunhar ata da reunião | 4 | 5 | 2 | 7 |
| Responder automaticamente dúvida regulatória | 5 | 2 | 5 | 2 |
| Resumir documentação pública | 3 | 5 | 1 | 7 |

**Observação:** a pontuação é uma ferramenta pedagógica criada para esta apostila; não é um método oficial prescrito pelo curso.

## 16. Reinventando processos

O curso vai além da pergunta “como fazer o trabalho atual mais rápido?”. Ele propõe outra: **“se uma etapa ficar muito mais barata ou rápida, como o processo inteiro deveria mudar?”**

### Exemplo: campanhas de marketing

No processo antigo, preparar um texto para uma campanha exigia bastante esforço, e por isso talvez a equipe publicasse uma única versão. Se a IA ajuda a gerar rascunhos rapidamente, a oportunidade não precisa ser apenas economizar tempo. A equipe pode preparar **quatro variações**, revisar todas e fazer um **teste A/B** ou outra comparação controlada, medindo qual funciona melhor.

**Analogia:** quando uma padaria ganha um forno mais eficiente, ela pode produzir o mesmo número de pães gastando menos, **ou** experimentar novas receitas e atender mais clientes. A tecnologia muda as possibilidades do negócio, não apenas a velocidade.

### Um jeito simples de redesenhar um fluxo

**Antes:** receber pergunta → procurar manualmente uma política → responder → repetir.

**Possível depois (exemplo fictício):** receber pergunta → buscar políticas autorizadas → montar rascunho com fontes → validar automaticamente formato e permissões → responder ou encaminhar para revisão → registrar dúvidas ainda não cobertas.

O benefício pode ser **redução de esforço**, **melhor consistência** e **identificação das dúvidas mais comuns**. Mas só saberemos se funcionou medindo os resultados.

### Evite o “teatro da automação”

É quando a empresa anuncia um assistente incrível, mas ele só desloca trabalho para quem precisa corrigir erros. Perguntas úteis: a fila diminuiu? A resposta ficou mais correta? As pessoas confiam no resultado? A intervenção manual realmente caiu? O usuário consegue chegar a uma pessoa quando precisa?

**Para uma liderança:** não conte apenas quantos membros da equipe “usam IA”. Avalie como o uso altera qualidade, tempo de ciclo, satisfação, retrabalho e risco.

## 17. Pessoas, funções e governança

O curso explica que aplicações de IA generativa podem ser criadas por equipes relativamente enxutas, mas precisam de **responsabilidades claras**. Os papéis podem se acumular em uma mesma pessoa; não existe uma formação obrigatória e única para todas as empresas.

| Papel | Contribuição típica |
|---|---|
| Engenharia de software | Integração, qualidade, API, testes e implantação |
| Especialistas em IA/ML | Avaliação de modelos, dados e técnicas de IA |
| Pessoa especialista no domínio | Verificar regras, exemplos e necessidades reais |
| Produto/negócio | Priorizar valor, jornada do usuário e indicadores |
| Segurança, privacidade e risco | Acesso, dados sensíveis, controles, governança |

**Analogia:** para abrir um restaurante, não basta contratar alguém que sabe fazer um prato. Precisamos garantir atendimento, estoque, higiene, operação e escuta do cliente. Uma aplicação de IA também tem várias peças além do modelo.

### Pequeno checklist para começar com disciplina

**Problema:** quem sofre com ele e com qual frequência?  
**Dado:** quais informações podem ser usadas legalmente e com autorização?  
**Modelo:** qual é o desempenho nos casos representativos?  
**Software:** como lidaremos com falhas, limites e custos?  
**Pessoas:** quem aprova, opera, acompanha e corrige?  
**Resultado:** qual métrica mostra se a solução ajudou?

### Três perguntas que deveriam aparecer em uma reunião de projeto

1. **O que acontece quando a IA erra?** Precisa existir um caminho seguro.
2. **Como saberemos que melhorou?** Precisa de referência, indicadores e avaliação.
3. **Quem responde pelo resultado?** Tecnologia não substitui prestação de contas.

## 18. Empregos, riscos e o futuro da IA

Ao analisar o impacto econômico e social, o curso reconhece **oportunidades e preocupações reais**. A IA pode ampliar capacidade produtiva e criar novas ofertas, mas também alterar tarefas, exigir requalificação e afetar postos de trabalho de formas diferentes.

### Impacto em tarefas não é igual a substituição de um emprego

Um estudo citado nas aulas estima o potencial de exposição de tarefas à IA. **Exposição** significa que determinadas atividades podem ser afetadas, não que empregos desaparecerão automaticamente nem que uma previsão virou fato. O efeito depende de adoção, custos, regulamentação, incentivos, organização e decisões humanas.

**Exemplo:** se uma professora usa IA para sugerir exercícios, isso não elimina a orientação, o julgamento pedagógico nem o relacionamento com os alunos. Pode mudar o tempo gasto preparando material e abrir espaço para novas atividades.

### Riscos que devemos levar a sério

**Viés e discriminação.** Textos de treinamento podem conter estereótipos. Um sistema pode reproduzir esses padrões e prejudicar grupos de pessoas.

**Desinformação e conteúdo enganoso.** Textos, imagens, áudios e vídeos sintéticos podem ser usados para enganar. Uma peça convincente não é prova de um fato.

**Privacidade e segurança.** Dados confidenciais podem aparecer em prompts, arquivos, logs ou integrações sem controles adequados.

**Uso malicioso e erros com consequências.** Um sistema automatizado pode ser abusado, manipulado ou executar ações inadequadas se não houver limites e validação.

### IA de propósito geral não é AGI

O curso separa dois conceitos importantes:

- **Tecnologia de uso geral:** serve para muitos tipos de atividade, como eletricidade ou internet.
- **AGI (*Artificial General Intelligence*):** conceito de um sistema capaz de realizar qualquer tarefa intelectual que um ser humano consegue realizar, segundo a definição usada no curso.

Ser útil em muitas tarefas **não prova** que um sistema atingiu AGI. O futuro da AGI e seus prazos são incertos; previsões categóricas sobre quando acontecerá precisam ser tratadas com cautela.

### Nem otimismo cego, nem pessimismo automático

A perspectiva final do curso é aproveitar a IA para melhorar a vida das pessoas, sem ignorar seus riscos. Uma decisão madura não é “usar IA em tudo” nem “proibir tudo”: é identificar aplicações úteis, estabelecer controles e aprender continuamente.

## 19. IA responsável no dia a dia

**IA responsável** significa desenvolver e utilizar sistemas de forma ética, confiável e com atenção às pessoas afetadas. A transcrição organiza vários princípios importantes.

### Cinco princípios em palavras simples

| Princípio | Pergunta cotidiana |
|---|---|
| **Equidade** | A solução trata pessoas de maneira justa? |
| **Transparência** | É possível explicar o papel da IA e suas limitações? |
| **Privacidade** | Só usamos dados necessários, protegidos e autorizados? |
| **Segurança** | O sistema resiste a falhas, abuso e acessos indevidos? |
| **Uso ético** | A aplicação traz benefício justificável, sem exploração indevida? |

### Exemplo: o assistente da equipe

Um funcionário pergunta ao chatbot sobre um documento de acesso restrito. O sistema encontra o documento, mas **a pessoa não tem permissão para lê-lo**. A resposta correta não é copiar o conteúdo em nome da conveniência. O aplicativo deve respeitar a autorização e orientar como solicitar acesso, se houver um procedimento legítimo.

Outro caso: a IA está prestes a orientar uma pessoa com base num documento que foi substituído ontem. O aplicativo deve priorizar a versão autorizada atual e, se houver conflito, sinalizar que não há base confiável para responder.

### Um checklist antes de colocar em produção

- [ ] O propósito e o limite de uso estão definidos.
- [ ] Dados pessoais e informações confidenciais recebem proteção adequada.
- [ ] Fontes e permissões são verificadas.
- [ ] Casos de falha, viés e interpretação incorreta foram testados.
- [ ] Existe tratamento de “não sei” e encaminhamento para pessoa responsável.
- [ ] Ações de alto impacto exigem autorização adequada.
- [ ] Há responsáveis pelo monitoramento e pela correção.
- [ ] Usuários sabem quando e como a IA participa do processo.

**Resumo da semana:** IA tende a modificar **tarefas** dentro de profissões. O ganho maior às vezes vem de redesenhar processos, não apenas de fazer a mesma coisa mais rápido. O uso responsável exige pessoas, mecanismos de controle e escolhas conscientes.

---

# Laboratório de prompts e desafios

Estes laboratórios são **exercícios originais da apostila**, inspirados nos conceitos do curso. Eles não substituem os laboratórios oficiais da DeepLearning.AI. Para praticar, use informações fictícias e revise toda resposta.

## Experimento 1 — Texto: de genérico a útil

**Primeiro teste:**

```text
Escreva um convite para um encontro de aprendizagem.
```

**Segundo teste:**

```text
Escreva um convite de até 120 palavras para colegas iniciantes
participarem de uma sessão de 30 minutos sobre IA generativa.
O objetivo é entender o que são tarefas de escrita, leitura e chat.
Use tom acolhedor e linguagem simples.
Não invente data, horário nem link da reunião.
```

**Observe:** qual versão reduz mais trabalho de edição? Qual preserva as restrições?

## Experimento 2 — Resumo fiel

```text
Resuma o texto a seguir em cinco pontos.
Separe claramente: fatos presentes no texto, hipóteses e dúvidas.
Não acrescente números ou fontes que não estejam no material.
Quando faltar informação, escreva "não informado".
Texto: [cole um texto público ou fictício]
```

**Observe:** a IA pulou uma informação importante? Adicionou uma conclusão sem evidência?

## Experimento 3 — Categorias fechadas

```text
Classifique as mensagens a seguir usando somente:
ACESSO, AMBIENTE, PROCESSO, OUTROS.
Retorne uma tabela com: mensagem, categoria e justificativa curta.
Se houver ambiguidade, sinalize "precisa de revisão".
Mensagens fictícias:
1. "Minha senha foi bloqueada."
2. "A aplicação não inicia no ambiente de teste."
3. "Onde encontro o passo a passo de abertura do chamado?"
4. "Obrigado pela ajuda de ontem!"
```

**Observe:** o modelo respeitou as categorias? A justificativa corresponde à mensagem?

## Experimento 4 — Parceiro de reflexão

```text
Estou avaliando três maneiras de compartilhar conhecimento com um time:
encontro quinzenal, guia escrito e sessões de demonstração.
Compare ganhos, esforço, limitações e como medir resultados.
Não escolha por mim ainda. Identifique quais dados faltam e
me faça até três perguntas realmente relevantes.
```

**Observe:** a IA ajuda a **pensar**, em vez de simplesmente validar uma preferência?

## Experimento 5 — Simulando RAG manualmente

Crie dois trechos fictícios: “Política A: a sala pode ser reservada com 24 horas de antecedência” e “Política B: o estacionamento exige cadastro prévio”. Em seguida, teste:

```text
Responda à pergunta exclusivamente com os trechos abaixo.
Pergunta: "Preciso reservar a sala antes?"
Trechos:
[cole as políticas A e B]
Cite o trecho utilizado. Se não houver informação suficiente,
diga "não encontrei resposta nos trechos".
```

Repita a pergunta sobre **cancelamento de reserva**, informação que você não forneceu. **O comportamento esperado** é reconhecer a lacuna, não criar uma regra.

## Experimento 6 — Teste de falhas

Crie cinco casos fáceis e cinco ambíguos para um classificador fictício. Peça que a IA classifique. Depois faça uma tabela com: resultado esperado, resposta obtida e diferença encontrada. **Não declare que o sistema é confiável com dez exemplos**: use o exercício para entender por que é preciso avaliar.

## Experimento 7 — Escolha técnica argumentada

```text
Compare, para um sistema que responde perguntas sobre manuais internos,
três estratégias: prompt com documento enviado, RAG e fine-tuning.
Considere atualização dos manuais, permissões, custo, complexidade,
rastreabilidade das fontes e riscos.
Entregue uma tabela e uma recomendação provisória.
Identifique quais testes seriam necessários antes de decidir.
```

**Observe:** a recomendação depende de requisitos e evidências, ou só de um nome sofisticado?

## Experimento 8 — Revisão de segurança

```text
Avalie este cenário fictício: um agente pode buscar documentos,
criar um relatório e publicar automaticamente num canal do time.
Liste riscos de privacidade, dados desatualizados, erros e ações não
reversíveis. Proponha permissões mínimas, pontos de aprovação,
logs adequados e uma forma de interromper a execução.
Não suponha que publicar sem confirmação é aceitável.
```

## Experimento 9 — Imagem com origem transparente

Em uma ferramenta de geração de imagens, peça uma ilustração claramente fictícia para acompanhar um material de estudo. Depois pergunte a si mesmo: **essa imagem poderia ser confundida com o registro verdadeiro de um acontecimento?** Se sim, rotule-a como ilustração sintética.

## Experimento 10 — Aplicabilidade no trabalho

```text
Vou listar tarefas de uma função. Para cada tarefa, indique se a IA
pode: (A) apenas apoiar um rascunho, (B) sugerir e exigir revisão,
(C) executar automaticamente sob controles, ou (D) não ser adequada.
Explique cada classificação considerando dados, falhas, impacto,
reversibilidade e necessidade de julgamento humano.
Tarefas: [forneça uma lista sem dados sensíveis]
```

## Experimento 11 — Risco e confiabilidade

```text
Crie uma matriz de riscos para um assistente que explica políticas
internas a partir de documentos autorizados.
Considere erro factual, documento vencido, vazamento de informação,
viés, indisponibilidade e acesso sem permissão.
Para cada risco, sugira prevenção, detecção e resposta.
Não invente requisitos legais específicos.
```

## Experimento 12 — Retroalimentação de produto

```text
Com base nas seguintes avaliações fictícias de usuários, agrupe
reclamações recorrentes, identifique possíveis hipóteses e sugira
experimentos de melhoria. Não trate correlação como causa.
Separe "o que as pessoas disseram" de "o que inferimos".
Dados: [cole avaliações inventadas ou autorizadas]
```

### Registro de aprendizagem

Após cada experimento, escreva três frases: **“Funcionou porque…”**, **“Falhou quando…”** e **“Na próxima rodada eu mudaria…”**. Guarde os melhores exemplos num repositório sem incluir segredos, informações de clientes nem dados pessoais.

---

# Projeto final: assistente de informações confiáveis

**Missão:** desenhar, sem necessidade de programar, um pequeno assistente que ajude uma equipe a encontrar respostas em documentos autorizados. A proposta segue os conceitos das três semanas. O cenário é fictício e serve como exercício de arquitetura, produto e governança.

## Cenário e objetivo

Uma equipe recebe perguntas repetidas sobre uso de ambientes, abertura de chamados e reservas de salas. Cada pessoa procura em documentos diferentes. A meta do piloto é **reduzir tempo de busca sem inventar respostas nem furar permissões**.

## Etapa A — Defina a tarefa

Escreva uma frase com: quem pergunta, qual informação procura e como reconheceremos uma resposta correta. Exemplo: “Pessoas autorizadas consultam manuais internos; a resposta deve citar o documento, sua versão e reconhecer quando não há resposta.”

## Etapa B — Escolha uma solução inicial

| Alternativa | Uso adequado | Ponto de atenção |
|---|---|---|
| Prompt com documentos anexados | Demonstração inicial de pequeno escopo | Atualização e permissão manuais |
| RAG sobre base autorizada | Perguntas frequentes sobre vários documentos | Busca e controle de acesso |
| Fine-tuning | Ajustar formato ou comportamento específico após testes | Treinamento e avaliação adicionais |

**Escolha sugerida para o exercício:** protótipo com documentos fictícios; posteriormente, considerar RAG apenas se os requisitos justificarem.

## Etapa C — Descreva o caminho da pergunta

1. A pessoa se autentica e envia uma pergunta.
2. O sistema verifica o escopo de acesso.
3. Busca documentos autorizados relevantes.
4. Envia ao modelo a pergunta e os trechos recuperados.
5. O modelo gera resposta clara com referência ou admite a falta de evidência.
6. Uma validação confere formato, fonte e ausência de conteúdo não autorizado.
7. Casos ambíguos ou de alto impacto são encaminhados para revisão.

## Etapa D — Prepare uma bateria de avaliação

Crie **15 perguntas fictícias**: cinco com resposta direta, cinco com resposta em mais de um trecho e cinco sem resposta ou com conflito entre documentos. Registre a resposta de referência, a fonte esperada e o comportamento seguro.

**Perguntas para testar o sistema:**

- Respondeu usando a fonte certa?
- Disse “não sei” quando precisava?
- Misturou duas políticas diferentes?
- Expôs material que a pessoa não podia ver?
- Conseguiria responder a uma pergunta maliciosa pedindo para ignorar instruções?

## Etapa E — Defina indicadores

Use métricas simples e explícitas, como **precisão das respostas avaliadas**, **taxa de respostas sem fonte**, **tempo até a resposta útil**, **percentual encaminhado para humanos**, **incidentes de acesso** e **satisfação dos usuários**. Não invente números de sucesso: registre a linha de base e compare.

## Etapa F — Apresente a decisão

Prepare um resumo de uma página com:

**Problema → público → solução inicial → dados e permissões → riscos → critérios de sucesso → próximos passos.**

**Critério de conclusão:** você consegue explicar por que o modelo foi escolhido, o que pode dar errado e como descobrir se o piloto entregou valor.

---
# Revisão de conhecimentos

**Como estudar:** responda antes de abrir o gabarito. Se tiver dificuldade, volte ao capítulo indicado. As questões são autorais e foram criadas para reforçar o conteúdo, não são questões oficiais do curso.

## Questões da semana 1

**1.** O que distingue IA generativa de um sistema que apenas classifica e-mails como spam?

**2.** Por que Andrew Ng compara a IA com a eletricidade?

**3.** Explique com suas palavras o que um LLM aprende durante a previsão de próximos tokens.

**4.** Verdadeiro ou falso: se a IA escreveu uma resposta fluente, ela necessariamente conferiu os fatos numa fonte confiável.

**5.** Dê dois exemplos de tarefas de **escrita** e dois de **leitura**.

**6.** Qual é a diferença entre usar um chat para classificar uma única mensagem e integrar a classificação em um aplicativo de software?

**7.** Qual problema pode ocorrer quando o modelo não conhece a lista verdadeira de departamentos de uma empresa?

**8.** O que significa “alucinação” em uma resposta de IA?

**9.** Dê três informações úteis para melhorar um prompt que apenas diz “escreva um texto”.

**10.** Na explicação introdutória do curso, qual é a ideia central de um modelo de difusão para imagens?

## Questões da semana 2

**11.** Por que um protótipo de IA não deve ser considerado aprovado só porque acertou três exemplos?

**12.** Enumere as etapas gerais do ciclo de vida de um projeto de IA generativa.

**13.** O que é um token e por que ele é relevante para estimar custos?

**14.** Uma aplicação faz 10 mil chamadas por dia. Mesmo com preço baixo por chamada, por que o custo pode ser importante?

**15.** Explique as três etapas principais de RAG.

**16.** Por que RAG pode ser útil para responder perguntas sobre políticas internas?

**17.** Verdadeiro ou falso: implementar RAG elimina automaticamente alucinações e problemas de permissão.

**18.** Em qual situação fine-tuning pode ajudar mais do que simplesmente anexar uma política atualizada ao prompt?

**19.** Cite pelo menos quatro critérios para escolher um modelo de linguagem.

**20.** Qual é a diferença prática entre um modelo solicitar uma ferramenta e um agente coordenar várias ações?

## Questões da semana 3

**21.** Por que a análise de tarefas é mais útil do que perguntar apenas “qual profissão a IA vai substituir”?

**22.** Qual a diferença entre **aumento de capacidade** e **automação**?

**23.** Dê um exemplo de atividade adequada para IA com revisão humana e um exemplo que exige autorização formal.

**24.** Como a IA pode aumentar valor sem apenas reduzir custos?

**25.** Que perguntas ajudam a evitar o “teatro da automação”?

**26.** Quais tipos de profissionais ou conhecimentos devem participar de um projeto de IA generativa?

**27.** Impacto potencial sobre tarefas significa desaparecimento garantido de postos de trabalho? Explique.

**28.** Qual é a diferença entre tecnologia de uso geral e AGI?

**29.** Cite cinco dimensões da IA responsável apresentadas no curso.

**30.** O assistente encontra a resposta num documento confidencial que o usuário não pode acessar. Como o sistema deve agir?

---

# Gabarito comentado

**1.** Um classificador normalmente escolhe um rótulo ou uma previsão. A IA generativa é especialmente conhecida por produzir conteúdo novo, como textos e imagens. As duas fazem parte do campo de IA.

**2.** Porque eletricidade e IA são tecnologias de uso geral, aplicáveis em muitos setores e tarefas diferentes.

**3.** Ele aprende padrões de sequências de texto para prever partes seguintes. O treinamento em larga escala ajuda a produzir novas respostas, mas a explicação simplificada não cobre todos os ajustes dos assistentes modernos.

**4.** **Falso.** Uma resposta convincente pode conter fatos errados ou inventados. Fluência não substitui verificação.

**5.** Escrita: criar comunicado e sugerir nomes. Leitura: resumir artigo e classificar reclamação. Outros exemplos semelhantes também valem.

**6.** No chat, a pessoa opera manualmente. Num aplicativo, um sistema integra a classificação ao processo, incluindo validação, segurança e tratamento de falhas.

**7.** O modelo pode inventar uma categoria ou departamento inexistente. Dar a lista fechada de opções ajuda a reduzir esse problema.

**8.** É uma informação gerada que está errada ou não é sustentada pelas fontes, mesmo que pareça plausível.

**9.** Possíveis respostas: objetivo, público, contexto, tom, formato de saída, limitações e fatos fornecidos. Escolha três.

**10.** Aprender padrões para remover ruído e, na geração, transformar progressivamente uma representação ruidosa em imagem, guiada pelo pedido.

**11.** Três exemplos não representam a diversidade dos casos reais, ambiguidades ou falhas importantes. É preciso uma avaliação mais ampla e representativa.

**12.** Definir escopo, criar protótipo, avaliar, melhorar iterativamente, implantar com controles e monitorar.

**13.** Token é uma unidade de processamento de texto, não necessariamente uma palavra inteira. Muitos serviços cobram pelo volume de tokens de entrada e de saída.

**14.** Pequenos custos multiplicados por muitas chamadas viram gasto relevante; entram também infraestrutura, testes, monitoramento, suporte e qualidade.

**15.** Recuperar trechos relevantes, acrescentar esses trechos ao contexto e gerar a resposta com base neles.

**16.** Porque a política é um conhecimento específico e pode mudar; a busca permite fornecer o documento ao modelo no momento da resposta.

**17.** **Falso.** A recuperação pode falhar, devolver versão antiga ou informação não autorizada. É preciso medir qualidade e preservar controle de acesso.

**18.** Quando queremos ajustar consistentemente comportamento, formato ou capacidade numa tarefa especializada, após testar soluções mais simples. Não é a primeira escolha para “memorizar” uma política que muda.

**19.** Qualidade, custo, latência, segurança, disponibilidade, integração, manutenção e licenças são exemplos válidos.

**20.** Uma ferramenta faz uma operação específica. Um agente pode planejar e coordenar uma sequência de operações, exigindo controles mais amplos.

**21.** Porque uma profissão engloba tarefas com necessidades e riscos diferentes. Dividir a rotina permite localizar oportunidades reais sem generalizações sobre o emprego inteiro.

**22.** Aumento de capacidade apoia a pessoa que continua decidindo. Automação executa parte da tarefa com menor intervenção humana, sob controles.

**23.** Resumir uma reunião para conferência humana é um exemplo de apoio. Autorizar uma mudança crítica em produção é exemplo de decisão que exige processo formal.

**24.** Ao permitir novas ofertas, mais experimentos, maior capacidade de atendimento, melhor personalização ou fluxos antes inviáveis.

**25.** Se o retrabalho caiu, se o resultado está correto, se a fila melhorou, se o usuário está satisfeito e se há métricas e referências confiáveis.

**26.** Engenharia de software, conhecimento de IA/ML quando necessário, especialista do domínio, produto/negócio, segurança, privacidade e risco.

**27.** **Não.** Exposição a mudanças significa possibilidade de alteração de tarefas; o efeito final depende de escolhas, adoção, contexto econômico e humano.

**28.** Tecnologia de uso geral pode atender muitas finalidades. AGI, na definição do curso, é a capacidade de realizar qualquer tarefa intelectual humana. Não são sinônimos.

**29.** Equidade, transparência, privacidade, segurança e uso ético.

**30.** Deve respeitar o controle de acesso, não revelar o documento e indicar um procedimento permitido de consulta ou autorização, se houver.

### Seu diagnóstico de estudo

- **25–30 acertos:** ótima compreensão introdutória; passe aos exercícios e explique conceitos para outra pessoa.
- **18–24 acertos:** você tem uma boa base; revise os capítulos com maior número de dúvidas.
- **Até 17 acertos:** volte às analogias e refaça os experimentos. A intenção é aprender, não competir.

A pontuação é apenas uma sugestão pedagógica, não uma certificação ou avaliação oficial.

---

# Glossário sem complicação

| Termo | Tradução para a vida real |
|---|---|
| **IA** | Campo de técnicas que permitem a sistemas realizar tarefas associadas a capacidades inteligentes. |
| **IA generativa** | IA que produz conteúdo como textos, imagens e sons. |
| **LLM** | Grande modelo de linguagem treinado com muitos textos. |
| **Prompt** | Instrução ou pedido enviado ao modelo. |
| **Token** | Unidade de texto processada pelo modelo, às vezes parte de palavra. |
| **Treinamento** | Processo de ajustar parâmetros do modelo usando exemplos e objetivos. |
| **Pré-treinamento** | Etapa ampla de aprendizado antes de adaptações específicas. |
| **Aprendizado supervisionado** | Aprender com exemplos de entrada e saída associadas. |
| **Classificação** | Escolher um rótulo entre categorias. |
| **Sumarização** | Produzir um resumo do conteúdo. |
| **Alucinação** | Informação incorreta ou sem apoio gerada como se fosse confiável. |
| **Contexto** | Informações disponíveis ao modelo para realizar uma tarefa. |
| **Janela de contexto** | Limite de conteúdo que um modelo pode considerar numa interação. |
| **Multimodal** | Capaz de trabalhar com mais de um tipo de dado, como texto e imagem. |
| **Difusão** | Família de técnicas que geram imagens por refinamentos sucessivos ligados a ruído. |
| **API** | Forma de um sistema de software usar funções de outro sistema. |
| **Protótipo** | Versão pequena para aprender, testar e corrigir. |
| **Avaliação** | Testes e critérios para medir se a solução funciona. |
| **Latência** | Tempo de espera até a resposta chegar. |
| **RAG** | Buscar informação relevante antes de gerar a resposta. |
| **Recuperação** | Localizar documentos ou trechos necessários. |
| **Fine-tuning** | Treinamento adicional para adaptar um modelo existente. |
| **RLHF** | Tipo de ajuste de comportamento com feedback humano. |
| **Ferramenta** | Recurso externo acionado pelo software, como busca ou calculadora. |
| **Agente** | Sistema que pode coordenar múltiplas etapas e ferramentas para atingir um objetivo. |
| **Viés** | Tendência que pode produzir resultados sistematicamente injustos ou distorcidos. |
| **IA responsável** | Uso de IA com compromisso de ética, segurança, privacidade, equidade e transparência. |
| **AGI** | Conceito de inteligência artificial geral, distinto de tecnologia de uso geral. |
| **Aumento de capacidade** | Usar IA para apoiar uma pessoa na execução de uma tarefa. |
| **Automação** | Usar um sistema para executar uma tarefa com menos intervenção humana. |
| **Métrica** | Medida observável para acompanhar desempenho ou resultado. |
| **Governança** | Regras, papéis e controles para decidir e acompanhar o uso da IA. |

---

# Referências, créditos e próximos passos

## Fonte principal

**Andrew Ng / DeepLearning.AI — [Generative AI for Everyone](https://www.deeplearning.ai/courses/generative-ai-for-everyone)**. A organização em três semanas segue o programa: introdução à IA generativa; projetos de IA generativa; IA generativa em negócios e sociedade. O desenvolvimento didático desta apostila utiliza a transcrição fornecida pela pessoa que solicitou o material.

**Leitura complementar oficial:** [Página do curso na DeepLearning.AI](https://www.deeplearning.ai/courses/generative-ai-for-everyone) e [Comunidade de discussão do curso](https://community.deeplearning.ai/c/course-q-a/generative-ai-for-everyone/381).

## O que é do curso e o que é da apostila?

Os conceitos gerais, as três semanas e vários casos de uso discutidos — como classificação de avaliações, escrita/leitura/chat, RAG, fine-tuning, uso de ferramentas e análise de tarefas — foram selecionados com base na transcrição do curso. **Analogias, quadros comparativos, prompts de laboratório, história-guia do assistente interno, atividades, questões, gabarito e matrizes** foram escritos especificamente para facilitar o estudo. Essas atividades não são os exercícios oficiais da plataforma.

**Aviso sobre atualidade:** quando a transcrição menciona marcas, modelos, cifras econômicas, exemplos de preços ou projeções, isso reflete o contexto histórico das aulas. Não use esses valores como dados atuais para planejamento financeiro, compra ou decisões corporativas sem consultar fontes atualizadas.

## Um plano simples de estudo em equipe

| Encontro | Leitura | Conversa ou prática |
|---|---|---|
| **1** | Semana 1 | Criar um prompt, observar erro e melhorá-lo |
| **2** | Semana 2, capítulos 7–10 | Desenhar um fluxo com RAG e critérios de teste |
| **3** | Semana 2, capítulos 11–13 | Comparar modelos, custos, ferramentas e riscos |
| **4** | Semana 3 | Escolher tarefas e discutir governança |
| **5** | Projeto final | Apresentar proposta, riscos e indicadores |

**A meta não é decorar siglas.** É conseguir fazer boas perguntas: *qual problema resolve? de onde vêm as informações? como medimos o resultado? o que acontece quando falha?*

## Como compartilhar

Este é um material educativo independente e não oficial, destinado ao estudo. **Não redistribua a transcrição original, vídeos, slides ou materiais de terceiros** apenas porque você tem acesso ao curso. Ao publicar ou adaptar o texto autoral deste repositório, siga as condições do arquivo [`LICENSE.md`](../../LICENSE.md), incluindo atribuição apropriada. As marcas DeepLearning.AI e Andrew Ng são citadas apenas como identificação da fonte.

---

**A tecnologia muda. A habilidade de perguntar, verificar e decidir com responsabilidade continua valiosa.**

# Leitura independente da história antes do SDD

Use uma rodada com um revisor que recebe a mesma ficha que seguirá ao SDD. O teste é descobrir o que outra pessoa ou agente consegue entender a partir do texto. O resultado continua sendo a história refinada.

## Preparar a leitura

Depois de escrever a ficha, abra um contexto novo no harness, sem histórico herdado. Passe apenas o texto da ficha e a instrução abaixo. Peça ao revisor que deixe fechados os links, anexos e arquivos do projeto. Uma pendência registrada faz parte da ficha. O histórico da entrevista e as respostas esperadas ficam com quem conduziu o refinamento.

> Leia somente a ficha abaixo. Em poucas linhas, diga quem enfrenta o problema, qual decisão ou tarefa a solução melhora, qual ganho é esperado e qual comportamento você testaria. Se houver interpretações plausíveis que mudem o escopo ou o resultado de um teste, relate até duas. Para cada uma, cite o trecho, explique as interpretações e formule a pergunta que resolveria a diferença. Reconheça as pendências que a ficha já declara. Se o texto bastar, diga isso. Use apenas as informações da ficha, sem abrir links, sugerir arquitetura ou editar o card.

Se o harness não oferecer um revisor isolado, a mesma instrução pode acompanhar a ficha em uma conversa nova ou ser entregue a um colega que não participou da entrevista. Se essa leitura for inviável, entregue a história com as pendências conhecidas. Informe a limitação se a revisão tiver sido solicitada. Uma releitura pelo autor no mesmo chat conta como autorrevisão.

## Resolver o que muda a entrega

Quem conduziu a entrevista confronta os achados com os acordos e decide a próxima ação:

- **A resposta já foi acordada, mas ficou fora do texto.** Recupere o acordo na fonte e esclareça o trecho da ficha ou o CA correspondente.
- **Há duas interpretações e nenhuma decisão registrada.** Pergunte ao engenheiro ou à área responsável qual comportamento vale. Enquanto aguarda, registre a dúvida e seu efeito no campo de pendência. Se a situação levantada for hipotética, confirme primeiro se ela ocorre no domínio.
- **A ficha já registra a pendência ou a sugestão extrapola o escopo.** Preserve o recorte. Uma observação editorial só exige ação se alterar o entendimento da entrega.

Encerre após essa leitura e sua triagem. A revisão independente verifica a clareza da ficha. DoR, DoD e aceite continuam sujeitos às evidências e decisões do time.

A técnica se inspira na separação entre autoria com contexto e revisão por um leitor novo descrita no [Elephant–Goldfish Model](https://egm.dev/guide/). A skill pode executá-la pelos recursos disponíveis no próprio harness.

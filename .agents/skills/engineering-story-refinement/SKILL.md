---
name: engineering-story-refinement
description: Cria, revisa e desdobra histórias de engenharia a partir de pedidos, cards e contexto do time. Use para entrevistar o time, mapear jornadas, recortar entregas verificáveis e avaliar prontidão ou conclusão.
metadata:
  version: "2.2.0"
---

# Refinamento de histórias de engenharia

## Escolha a entrada

Comece pela [ficha curta](references/ficha-curta.md). Use o contexto recebido para identificar o problema, o resultado e a decisão em aberto. Para um card existente, preserve os acordos e sinalize qualquer proposta que altere o escopo. Para incidente ativo ou rotina com procedimento conhecido, indique o encaminhamento e encerre. Se o pedido também trouxer uma melhoria estrutural, trate-a como item separado. Para plataforma, aplique as [diretrizes do time](references/01-diretrizes-plataforma.md).

## Conduza a conversa

- **Descubra o resultado.** Quem precisa conseguir fazer o quê depois da entrega? Que dificuldade enfrenta hoje e como perceberá a melhora? Em trabalho interno, o beneficiário pode ser quem opera um serviço ou valida um controle. Use o papel real e a consequência informada. Mantenha os benefícios esperados como hipóteses até haver evidência.
- **Escolha a intervenção pelo que falta decidir.** Se o item já estiver bem delimitado, com fluxo e resultado claros, vá direto ao aceite. Se os cards perderam a relação com a jornada, reconstrua o percurso. Se as áreas discordarem sobre uma etapa, facilite essa decisão. Se o escopo exceder o ciclo ou reunir resultados independentes, proponha um recorte utilizável. Para esses três casos, consulte [Mapear e dividir histórias](references/07-mapear-e-dividir-historias.md).
- **Entreviste por decisão.** Quando uma resposta puder mudar escopo, aceite ou prontidão, diga o que já ficou definido, faça a pergunta com maior impacto e aguarde. Incorpore a resposta à ficha e pule o que já foi esclarecido. Se a pessoa pedir um rascunho imediato ou desconhecer a resposta, identifique a lacuna, seu efeito e a próxima ação.
- **Construa os critérios de aceite (CAs).** Para cada resultado em escopo, proponha uma condição inicial, um evento e algo que o validador consiga observar. Se “funcionou” admitir duas interpretações, apresente um caso em que elas geram decisões diferentes e peça ao time para escolher. Registre quais critérios são propostas e quais já foram acordados.
- **Avalie o recorte.** Para prontidão (DoR), identifique o pré-requisito de início, o fato que comprova seu estado e qual parte ele afeta. Para conclusão (DoD), combine a evidência e quem validará o resultado. Em uma entrega já executada, diferencie evidência consultada de evidência relatada e confira o aceite registrado. Aplique os acordos do time. Prioridade, estimativa, aprovação e aceite são decisões humanas.

## Entregue o necessário para a etapa

Entregue a ficha do recorte escolhido de modo que alguém consiga lê-la sem a conversa. Explique qual decisão ou tarefa está prejudicada hoje, como a solução proposta muda essa situação e que ganho o público espera perceber. Se houver dúvida sobre o valor, pergunte o que a pessoa poderá fazer melhor depois da entrega. Registre como hipótese o que ainda depende de observação em uso. Em revisões, resuma o que mudou. Para uma revisão de qualidade solicitada, consulte a [matriz e INVEST](references/04-matriz-qualidade.md) como heurísticas e use os acordos de prontidão do time avaliado. Para plataforma, consulte o [DoR e DoD do guia](references/05-dor-dod.md) ao avaliar início ou conclusão. O [template detalhado](references/02-template-historia.md) e o [roteiro de facilitação](references/03-steps-refinamento.md) apoiam o refinamento aprofundado de plataforma. Use os [cenários de validação](references/06-exemplos-validacao.md) para calibrar o comportamento.

Antes de entregar a ficha ao SDD, use uma [leitura independente](references/08-leitura-independente.md) se o solicitante pedir ou se houver risco de perder um acordo importante na passagem da conversa para o texto. Exemplos: áreas atribuíram sentidos distintos a um termo, uma exceção muda o aceite ou o recorte reúne decisões dispersas em uma entrevista longa. Para uma história curta com regra e aceite inequívocos, entregue a ficha diretamente.

Feche com a próxima ação, quem pode responder e prazo quando conhecido. Atualizações em ferramentas externas dependem de autorização explícita.

---
description: Transforma um pedido de engenharia em história verificável ou revisa um card existente.
argument-hint: Cole o pedido ou card e informe o contexto e as decisões já acordadas.
agent: ask
---

# Refinar uma história de engenharia

Ajude o solicitante a transformar o contexto fornecido em um card Markdown que possa ser copiado para o quadro. Responda em português. Use o pedido, o card original, as respostas anteriores e os materiais que o solicitante identificar como fonte. Se ainda não houver uma demanda, peça que descreva o problema ou cole o card. Entregue o texto no chat. A publicação no quadro e as decisões sobre prioridade, estimativa, aprovação e aceite cabem aos responsáveis.

## Conduza o refinamento

Conduza uma conversa em rodadas. Quando a pessoa colar este texto junto com a descrição do problema, use essa descrição como ponto de partida. Aplique a triagem abaixo. Para uma história nova ou em revisão, siga este ritmo:

- **Na primeira resposta**, resuma em uma frase o que entendeu. Se houver uma decisão em aberto que mude a entrega, faça de uma a três perguntas diretas sobre o caso e termine a mensagem ali. Aguarde a resposta da pessoa para redigir o card.
- **Escolha cada pergunta pelo efeito da resposta.** Comece pela dúvida que mais altera o resultado ou o recorte. Use os termos do relato para explorar quem vive o problema, como o fluxo funciona hoje, qual regra decide uma exceção ou como o time verificaria a melhoria. Pule os pontos já respondidos. Por exemplo, se o usuário já definiu o canal de cobrança, uma pergunta útil seria “Se o pagamento aparecer entre a seleção do boleto e o envio do lembrete, o que deve acontecer?”.
- **Nas próximas rodadas**, incorpore o que a pessoa respondeu. Se restar uma dúvida que mude escopo ou aceite, faça a próxima pergunta com base nessa resposta e aguarde. Se a pessoa disser que ainda não sabe, registre a pendência e avance com o que foi definido.
- **Gere o card** assim que o problema, o recorte e o resultado verificável estiverem claros. Se o contexto inicial já trouxer esses elementos, entregue o card diretamente. Se a pessoa pedir explicitamente um rascunho imediato, entregue a ficha com as decisões em aberto identificadas.

1. **Entenda o pedido.** Identifique quem é afetado, o que ocorre hoje, qual observação sustenta o relato e o que precisa mudar. Quando o pedido já indicar uma solução, investigue qual problema ela resolveria. Preserve fatos e acordos. Identifique hipóteses, propostas e informações a confirmar. Exemplos fornecidos como modelo ilustram o formato. Só incorpore suas regras de negócio à história se o solicitante as confirmar para a demanda.
2. **Escolha a rota.** Para incidente ativo, indique o fluxo de incidentes e a próxima ação. Para rotina com procedimento conhecido, indique o procedimento e o próximo passo. Encerre aí. Uma melhoria estrutural identificada na triagem pode virar outra história.
3. **Resolva a ambiguidade que muda a entrega.** Se duas interpretações produzirem escopos ou aceites diferentes, apresente a diferença e faça a pergunta que decide entre elas. Enquanto aguarda, registre o que já está definido. Por exemplo, “o painel mostra dados de ontem” pode exigir indicar a data da última carga ou disponibilizar os dados de hoje antes da reunião. Um critério que verifica a data exibida só comprova a primeira melhoria.
4. **Recorte e torne verificável.** Delimite público, entrega, ambiente e exclusões pertinentes. Relacione cada resultado a uma condição de teste, uma ação e uma observação que permitiria ao validador aceitá-lo. Considere falha, recuperação, segurança ou desempenho quando afetarem o resultado. Registre a dependência que impede começar ou que afeta uma etapa posterior. Só atribua datas, responsáveis, métricas ou capacidade que tenham sido informados. Identifique sugestões como propostas.
5. **Adapte ao tipo de trabalho.** Para um card existente, preserve os compromissos confirmados e indique o que mudou e quais ampliações de escopo exigem decisão. Para um épico, proponha incrementos com resultado, aceite e dependências próprios. Se a incerteza técnica impedir o recorte, proponha uma investigação com pergunta, evidência esperada e decisão que ela permitirá tomar.

## Entregue o card

Ao chegar à etapa de entrega, use os cinco campos a seguir. Registre no último campo as pendências que continuaram abertas após a conversa.

- **Título** — Verbo e resultado pretendido.
- **Problema e público** — Situação atual, pessoas afetadas e fato que fundamenta o pedido.
- **Resultado e escopo** — Mudança que o público poderá observar, limites da entrega e exclusões acordadas.
- **Critérios de aceite propostos** — Para cada critério, descreva como verificar o comportamento esperado. Identifique metas que dependem de acordo.
- **Pendência e próximo passo** — Questão ou bloqueio, quem pode resolvê-lo e prazo ou condição, quando conhecidos.

Em revisões, acrescente após o card um resumo curto das alterações. Se o pedido for avaliar conclusão, registre o resultado por critério, quais evidências foram consultadas, quais foram apenas relatadas e quem registrou o aceite. Testes planejados e conversas simuladas continuam como evidências pendentes.

## Aprofunde apenas quando a etapa pedir

**Revisão de qualidade solicitada.** Examine a coerência entre problema, valor, resultado, escopo, aceite e teste. Use INVEST para avaliar independência, negociação, valor, possibilidade de estimar, tamanho e testabilidade. Indique a lacuna concreta e o ajuste sugerido. Se o solicitante pedir a matriz, avalie problema e público, valor, resultado e prazo, escopo e tamanho, abordagem técnica, riscos, dependências e mudança, capacidade e papéis, aceite e testabilidade, evidências e governança. Para cada dimensão, registre evidência, ação e nota de 0 (ausente ou contraditória), 1 (parcial) ou 2 (suficiente para a fase). Exclua do cálculo apenas dimensões inaplicáveis com justificativa. Havendo dimensões aplicáveis, arredonde 100 × soma ÷ (2 × quantidade aplicável). A nota mede maturidade documental. Um impedimento confirmado continua bloqueando o início.

**Acordos de plataforma.** Aplique este trecho a demandas do time de plataforma que usa o guia. Para outras engenharias, use os acordos fornecidos pelo respectivo time.

- Na triagem, identifique frente (Inovação, Auditoria e Governança ou Operação), solicitante, impacto, prazo e vínculo com chamado ou GMUD quando houver. No refinamento aprofundado, inclua abordagem técnica negociável, riscos, dependências, aprovações, janela e retorno conforme o procedimento aplicável.
- Para avaliar prontidão (DoR), verifique clareza de problema, resultado e aceite, compatibilidade do esforço com a capacidade líquida do ciclo, pré-requisitos e aprovações de início, executor, validador e prazo aplicável. Diferencie informação a confirmar de impedimento comprovado. Se a demanda consumir mais que a reserva ou deslocar um especialista comprometido, leve o impacto de esperar, o esforço, o saldo e a entrega afetada a quem decide a prioridade.
- Para avaliar conclusão (DoD), confira critérios verificados, testes e evidências vinculados, aceite do validador, documentação atualizada quando necessária e, conforme aplicável, validação pós-GMUD e aceite das evidências de auditoria. Com evidências ou aceite pendentes, recomende manter em validação e indique o que falta.

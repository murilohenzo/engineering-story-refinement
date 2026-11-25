# Exemplo 02 · Avaliação da skill no planejamento de reposição

Ensaio de mesa fictício com Engenharia de Dados e Planejamento de Estoque. A conversa abaixo simula a aplicação da [skill de refinamento de histórias, versão 2.1.0](../.agents/skills/engineering-story-refinement/SKILL.md). O entregável é a [história para o quadro](02-saldo-de-estoque-para-reposicao.md).

## Pedido inicial

> “Queremos atualizar o painel de estoque com mais frequência. Ontem ele mostrou saldo zero e o comprador quase pediu mercadoria que já tínhamos.”

O pedido sugere aumentar a frequência das cargas. O relato, por si só, ainda permite duas causas para o zero exibido: o estoque acabou ou parte dos depósitos ainda não enviou os dados.

## Decisões da entrevista

**1. Descobrir qual decisão o painel precisa sustentar.** A skill pergunta ao comprador: “Naquele momento, como você descobriu que ainda havia mercadoria?”. Ele responde: “Liguei para o depósito B. O depósito A já tinha enviado saldo zero, mas o arquivo de B, que tinha 12 unidades, ainda não tinha chegado”. O beneficiário é o comprador que precisa decidir se abre uma reposição. Aumentar a frequência continua sendo uma hipótese técnica.

**2. Resolver a divergência entre as áreas.** Para Dados, a atualização termina quando a carga executa com sucesso. Para Compras, o saldo de uma região só pode orientar a compra quando todos os depósitos esperados tiverem enviado a posição do mesmo dia. A pergunta decisiva é: “Se a carga de A terminar e B ainda estiver pendente, o comprador pode usar o zero de A?”. Compras responde: “Preciso ver que falta B. Quando A e B confirmarem zero, aí sim preciso ver zero”. As áreas concordam em exibir o motivo da pendência e em liberar o total após a confirmação de ambos.

**3. Escolher um recorte que já tenha uso.** O time descarta começar apenas pelo depósito A, pois o comprador continuaria telefonando para B. A skill pergunta se uma única região com todos os seus depósitos já permite tomar a decisão. Compras escolhe a região Sul, com A e B no piloto. Outras regiões e mudanças na frequência ficam para depois. O recorte percorre o fluxo completo: receber posições, conferir cobertura da região e mostrar ao comprador se o saldo pode orientar a reposição.

## Avaliação do uso

- **O que melhorou na definição do problema.** O relato do comprador revelou que um zero legítimo e uma carga incompleta tinham a mesma aparência. Essa distinção produziu dois testes com resultados diferentes, mesmo quando o único saldo recebido até o momento é zero (CA-01 e CA-03).
- **O que melhorou no escopo.** O primeiro corte sugerido, entregar apenas A, falhou quando confrontado com a decisão de compra. O piloto regional preserva o valor de ponta a ponta e dá ao time um limite explícito para discutir esforço.
- **Onde a skill encontrou seu limite.** A conversa definiu o significado de “completo”, mas não demonstrou que a fonte distingue um arquivo integral de um arquivo recebido pela metade. A história registra essa dependência no DoR. Os cenários combinados com o comprador são o plano de evidências para o DoD.

**Parecer do ensaio.** A história tem um resultado verificável e pode seguir para confirmação técnica. Permanece **em refinamento** até Dados demonstrar o sinal de conclusão por depósito. O benefício esperado é reduzir conferências por telefone. Seu efeito real só poderá ser avaliado durante o uso do piloto.

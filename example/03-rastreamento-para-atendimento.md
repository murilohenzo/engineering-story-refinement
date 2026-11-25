# Consultar o rastreio do volume durante o atendimento

História fictícia de logística refinada entre Atendimento e Expedição. O pedido inicial era mostrar o rastreamento na tela do pedido.

**Problema e público** — Uma cliente quis saber se precisava ficar em casa para receber uma encomenda. O atendente viu “enviado” na tela, mas precisou pedir à Expedição o link da transportadora. Na loja do ensaio, “enviado” significa que a caixa foi etiquetada e está pronta na doca. Só o registro de coleta permite confirmar a retirada.

**Resultado e escopo** — Na tela interna, o atendente pode abrir e compartilhar a página pública correspondente ao volume do pedido. O piloto abrange uma transportadora e pedidos com um único volume. Pedidos com várias caixas podem ter coletas separadas e seguem pelo procedimento atual. Importação de eventos e previsão de entrega pela loja ficam fora do piloto.

Espera-se reduzir consultas manuais à Expedição. Atendimento propôs acompanhar a proporção de chamados de localização de pedidos elegíveis resolvidos pelo link sem acionar a Expedição e registrar por que os demais precisaram de ajuda. Meta e período de observação ficam a combinar.

**Critérios de aceite propostos**

- **CA-01 · Link correspondente.** Para um pedido elegível com link público associado ao único volume, o atendente consegue abrir a página sem login e compartilhá-la, inclusive antes de o pedido receber o status “enviado”. A existência do link, isoladamente, não confirma a coleta.
- **CA-02 · Associação ausente ou divergente.** Para um pedido elegível sem link, sem associação ao volume ou com divergência conhecida, a tela oculta a ação de abrir o rastreio, indica a indisponibilidade e orienta a consultar a Expedição.
- **CA-03 · Fora do piloto.** Para um pedido de outra transportadora ou com múltiplos volumes, a tela informa que o pedido está fora do piloto e o atendente segue o procedimento atual.
- **CA-04 · Portal sem informação.** Se o link correto abrir uma página sem eventos ou com erro, o atendente informa ao cliente que irá confirmar a localização e consulta a Expedição. Esse chamado é registrado como exceção. A verificação acontece durante o atendimento.

**Pendência e próximo passo** — Escolher a transportadora. Engenharia e Expedição precisam demonstrar em homologação que a fonte eletrônica associa pedido, volume e link compartilhável. A história permanece em refinamento. A equipe pode prototipar a tela com dados fictícios enquanto confirma a fonte.

**Evidência planejada para conclusão** — Expedição comparará o código da etiqueta com a página pública. Atendimento percorrerá os quatro cenários e registrará os resultados. A execução, o aceite e a medição do ganho permanecem pendentes.

## O que a leitura independente mudou

O revisor recebeu apenas a ficha anterior a esta versão. Identificou duas dúvidas que mudavam o teste. Na primeira, perguntou se o status “enviado” era pré-requisito para exibir a ação. Atendimento confirmou que basta haver um link público correspondente ao volume, decisão incorporada ao CA-01. Na segunda, perguntou o que fazer com um link que aponta para outra caixa. Atendimento definiu a supressão da ação no CA-02. A forma de garantir a correspondência permanece aberta para o desenho técnico.

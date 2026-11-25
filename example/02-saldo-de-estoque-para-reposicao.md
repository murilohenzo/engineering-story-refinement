# Mostrar ao comprador quando o saldo da região Sul está completo para reposição

*História fictícia de Engenharia de Dados. Origem: [ensaio de refinamento com Compras](02-avaliacao-do-refinamento-de-estoque.md).*

**Problema e público** — O comprador consulta o painel para decidir se vai abrir uma reposição. No caso relatado, o depósito A informou zero para um produto. O painel exibiu esse valor como saldo regional enquanto a posição de B, com 12 unidades, ainda estava pendente.

**Resultado e escopo** — Para um produto consultado na região Sul, publicar o saldo regional referente ao dia somente após confirmar as posições completas de A e B para essa data. Enquanto faltar uma posição, identificar o depósito pendente e ocultar o total do dia. O piloto abrange o painel atual. Outras regiões, alteração da frequência de carga e geração automática de pedidos ficam fora desta entrega.

Com essa distinção, o comprador poderá decidir pelo painel quando aguardar e quando considerar uma reposição. Espera-se reduzir as ligações aos depósitos para conferir um saldo zero. Como proposta de acompanhamento, Compras pode registrar em quais consultas ainda precisou telefonar e por quê. Esse ganho segue como hipótese do piloto.

**Critérios de aceite propostos** — Os três cenários usam o mesmo produto e a mesma data de referência.

- **CA-01 · Posição parcial.** Dado que A concluiu sua posição com zero unidades e a posição de B segue pendente, ao consultar o produto o comprador vê “Aguardando depósito B”. O total do dia fica indisponível. Uma posição de B referente ao dia anterior mantém essa pendência.
- **CA-02 · Chegada do depósito faltante.** Partindo do CA-01, quando B conclui a posição do dia com 12 unidades e o painel processa a atualização, a consulta exibe 12 unidades para a região e a pendência desaparece.
- **CA-03 · Zero confirmado.** Quando A e B concluem suas posições do dia e ambos informam zero, o painel exibe saldo regional de zero unidades com a posição completa. O comprador consegue distinguir esse caso do CA-01.

**Pendência e próximo passo** — Engenharia de Dados vai conferir com os responsáveis pelas fontes qual registro confirma a conclusão de cada depósito e sua data de referência. Prazo a combinar com o time.

**DoR · Em refinamento.** O recorte e a interpretação dos estados foram acordados no ensaio. O sinal de conclusão ainda precisa ser demonstrado em homologação. A equipe pode preparar os dados dos três cenários enquanto confirma essa dependência.

**DoD · Evidência planejada.** Para cada CA, Engenharia de Dados registrará as posições de entrada, a data e o estado de conclusão de cada depósito, junto com o resultado da consulta no painel. O comprador do piloto verificará se consegue diferenciar “aguardar B” de “saldo zero confirmado” e registrará seu aceite no card. A execução e o aceite estão pendentes.

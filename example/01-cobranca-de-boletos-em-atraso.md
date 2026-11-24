# Enviar lembretes em D+1 e D+3 para boletos que continuam em aberto

*História fictícia de engenharia · Carteira piloto de Contas a Receber*

**Problema e público** — A seleção manual de boletos por Contas a Receber permite lembretes repetidos ou baseados numa situação financeira desatualizada. O cliente recebe a mensagem e o atendimento precisa explicar o ocorrido.

**Resultado e escopo** — Automatizar seleção, envio por e-mail e consulta do resultado por boleto e etapa para a carteira piloto. A rotina consulta a carteira diariamente às 09h no fuso de São Paulo. D é a data de vencimento e as etapas contam dias corridos. O envio exige cobrança habilitada, contato de e-mail habilitado e situação em aberto confirmada na fonte financeira imediatamente antes do disparo. Usar o modelo de mensagem acordado com o time. Editor de réguas, outros canais, renegociação e emissão de segunda via ficam para histórias próprias.

**Critérios de aceite propostos**

| ID | Situação | Resultado observável |
| --- | --- | --- |
| CA-01 | Boleto da carteira vence em 10/08 e permanece elegível até 13/08. | O provedor aceita um lembrete em 11/08 e outro em 13/08. As execuções de 10/08 e 12/08 não geram envio. |
| CA-02 | Um pagamento é registrado depois da seleção e antes da consulta final. | A etapa termina como suprimida por pagamento, sem chamada de envio ao provedor. Um título cancelado ou contato desabilitado também é suprimido, com o motivo correspondente. |
| CA-03 | Duas execuções disputam o mesmo boleto e etapa, ou o provedor aceita a mensagem e a resposta se perde. | Há um único aceite para aquela etapa. Ao consultar o boleto, o atendente encontra o identificador da mensagem aceita. |
| CA-04 | A fonte financeira fica indisponível antes do envio em D+1. | A etapa fica pendente. Se a consulta voltar no mesmo dia, a rotina reavalia a elegibilidade. Se voltar apenas em D+3, D+1 consta como expirada e só D+3 pode gerar envio. |
| CA-05 | O atendimento consulta um boleto após a execução. | Encontra etapa, data e hora, estado e motivo. Um aceite do provedor aparece como “aceito pelo provedor”. |

**Pendência e próximo passo** — Engenharia de integrações precisa confirmar, em homologação, que o provedor reconhece uma chave de idempotência e permite consultar o aceite por ela. Esse contrato sustenta o CA-03. Até a confirmação, a equipe pode desenvolver e testar a seleção com um provedor simulado. Produto valida a régua e o modelo de e-mail com Contas a Receber. Após a confirmação, QA executa os cinco cenários em homologação e Contas a Receber registra o aceite com base nos resultados.

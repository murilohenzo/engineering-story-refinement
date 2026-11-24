# Simulação 01 · Refinamento da cobrança de boletos em atraso

Simulação de refinamento entre Contas a Receber, Produto e Engenharia. A conversa, os identificadores e os resultados abaixo são fictícios. Os dias e horários representam escolhas para este exemplo.

## 1. Do pedido ao problema

> **Pedido inicial** — “Precisamos desenvolver um componente de cobrança de boletos em atraso com réguas agendadas.”

**Engenharia pergunta** — “O que a equipe faz hoje e qual parte precisa deixar de ser manual?”

**Contas a Receber responde** — “Toda manhã alguém exporta os títulos vencidos, confere os pagamentos e envia e-mails. Quando duas pessoas usam a mesma lista, o cliente pode receber o mesmo lembrete duas vezes. Também já separamos um título pela manhã e, antes do envio, o pagamento apareceu no sistema.”

**Produto delimita a primeira entrega** — “Quero que o cliente receba o lembrete correspondente ao dia de atraso e que o atendente consiga explicar por que ele foi enviado ou suprimido. Vamos começar com uma carteira, um canal e uma régua.”

Neste ponto já há problema e público definidos. Ainda falta esclarecer o que significa “agendado”. Executar uma rotina diariamente e mandar e-mail todos os dias produziriam experiências diferentes para o cliente.

## 2. Decisões que mudaram a história

- **Quando lembrar?** Contas a Receber escolhe D+1 e D+3, com D igual à data de vencimento e contagem em dias corridos. O componente consulta a carteira diariamente às 09h no fuso de São Paulo. Para vencimento em 10/08, as etapas são 11/08 e 13/08. No dia 12/08 não há lembrete.
- **Quem pode receber?** Produto limita o piloto aos boletos da carteira com cobrança habilitada, endereço de e-mail habilitado para contato e título em aberto na fonte financeira. Engenharia deve consultar novamente a situação imediatamente antes do envio. Se a consulta falhar, a tentativa fica pendente.
- **O que acontece se a rotina atrasar?** Uma reexecução no mesmo dia pode recuperar a etapa. Depois da virada do dia, a etapa vencida expira. Assim, uma indisponibilidade em D+1 não acumula dois lembretes em D+3.
- **O que conta como envio?** Para esta história, vale o aceite pelo provedor de e-mail. Se a resposta se perder, o componente consulta a tentativa pela mesma chave antes de decidir sobre nova tentativa. A confirmação de leitura pelo cliente fica fora do escopo.

## 3. História criada

As decisões da conversa estão registradas na [história de cobrança de boletos em atraso](01-cobranca-de-boletos-em-atraso.md).

## 4. Como o time desenvolveria o componente

1. **Selecionar as etapas do dia.** Implementar o cálculo de dias de atraso com um relógio controlável em testes. Executar a seleção com boletos fictícios da carteira e comparar o resultado com as quatro datas de CA-01.
2. **Controlar uma tentativa por boleto e etapa.** Registrar uma chave estável composta por carteira, boleto, régua e etapa. Aplicar unicidade no armazenamento para que dois trabalhadores concorrentes disputem o mesmo registro. O reprocessamento reutiliza a chave.
3. **Revalidar e enviar.** Conferir situação financeira e contato, enviar com a chave acordada e guardar o identificador devolvido. Diante de resposta incerta, reconciliar com o provedor. Mesmo após a expiração da janela, consultar um envio de resultado desconhecido antes de registrar seu estado final, sem disparar uma nova mensagem.
4. **Homologar a jornada com o atendimento.** Usar caixa de e-mail de teste e relógio simulado. Conferir a consulta por boleto, o motivo das supressões e a recuperação após falha. O resultado deve permitir ao atendente responder “por que este cliente recebeu este lembrete?”.

## 5. Ensaio de validação e decisão de aceite

No ensaio de mesa, o boleto fictício **BOL-101** vence em 10/08. Em 11/08, duas execuções selecionam D+1. O provedor simulado aceita a primeira mensagem, mas a resposta se perde. A execução seguinte consulta a mesma chave, encontra o aceite e registra o identificador **MSG-101**. Em 13/08, o título entra na seleção às 09h. A consulta final já encontra o pagamento e registra D+3 como suprimida. O atendente vê um envio aceito e uma supressão.

**Decisão simulada** — Contas a Receber considera esse comportamento compatível com a régua proposta. A história permanece **em validação**. O ensaio descreve o comportamento esperado e o aceite técnico depende de reproduzi-lo em homologação.

**Próxima ação** — Engenharia de integrações confirma o contrato do provedor e anexa os registros de concorrência e reconciliação. QA executa CA-01 a CA-05. Com essas evidências, Contas a Receber confere a consulta por boleto e registra a decisão de aceite no card.

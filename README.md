# Refinamento de histórias de engenharia

A skill transforma um pedido em história verificável ou melhora um card existente. O fluxo comum atende diferentes engenharias. As referências de plataforma preservam o guia do time para operação, capacidade, GMUD, prontidão e aceite.

## Refinar com a skill

O fluxo compartilhado fica na [skill de refinamento de engenharia](.agents/skills/engineering-story-refinement/SKILL.md). Para conduzir a entrevista no Cursor, Antigravity ou outro agente, disponibilize a pasta da skill com suas referências pelo mecanismo aceito no seu ambiente. Quando o projeto já estiver aberto no agente, você também pode indicar o arquivo diretamente:

> Leia `.agents/skills/engineering-story-refinement/SKILL.md` e conduza o refinamento desta demanda. Temos uma lista de cards de cobrança e queremos decidir qual entrega já seria útil para Contas a Receber.

A skill usa a ficha curta para pedidos e revisões. Se houver dúvida sobre a jornada, ela ajuda a reconstruí-la com o time. Quando a entrega estiver grande, ajuda a escolher uma parte utilizável e definir o aceite. Para pedidos pequenos com escopo claro, pode preencher a ficha diretamente.

A história refinada pode ser entregue ao SDD do time. A própria ficha explica o problema observado, como a solução proposta o resolve e qual ganho se espera para quem vai usá-la. Os critérios de aceite descrevem como verificar o comportamento da entrega.

Quando um acordo entre áreas ou uma exceção importante pode ter ficado só na conversa, a skill prevê uma rodada de [leitura independente antes do SDD](.agents/skills/engineering-story-refinement/references/08-leitura-independente.md). O revisor recebe apenas a ficha. Quem conduziu a entrevista compara as dúvidas com os acordos do time e corrige omissões ou registra a decisão em aberto. Para experimentar, peça “Leia a história de estoque como alguém que vai recebê-la no SDD e indique se duas interpretações mudariam um teste”.

Para avaliar o custo dessa rodada no piloto, compare histórias de complexidade semelhante com e sem leitura independente. Observe tempo e tokens do refinamento até a primeira especificação utilizável, quantos achados mudaram o card e quantas dúvidas o SDD precisou devolver ao engenheiro.

No [ensaio de rastreamento para Atendimento](example/03-rastreamento-para-atendimento.md), a leitura independente revelou duas decisões que mudaram o aceite: quando exibir o rastreio e como agir se o link estiver associado a outra caixa.

### Usar no Codex

Abra este repositório e peça, por exemplo, “Use $engineering-story-refinement para revisar este card com base no relato do cliente. Preserve as decisões confirmadas e destaque o que mudou”. Para usar em outro projeto, copie a [pasta da skill](.agents/skills/engineering-story-refinement/) inteira para a pasta .agents/skills desse projeto.

## Experimentar o fluxo

### Opção de prompt independente no GitHub Copilot

Abra o [prompt de refinamento](.github/prompts/refinar-historia.prompt.md), copie o texto a partir de “Refinar uma história de engenharia” para o Copilot Chat e acrescente o pedido ou o card existente. O texto é autocontido e também pode ser usado fora deste repositório. Em uma sessão **Local** do VS Code, com o projeto aberto, o mesmo arquivo pode ser invocado como `/refinar-historia`. A documentação do VS Code descreve a disponibilidade do comando por tipo de sessão. [Prompt files no VS Code](https://code.visualstudio.com/docs/agent-customization/prompt-files)

Para experimentar, acrescente ao texto copiado apenas o relato do problema:

> Hoje Contas a Receber confere boletos vencidos manualmente e às vezes envia lembretes repetidos.

Uma primeira pergunta útil seria “Quando vocês dizem que o lembrete está repetido, são dois envios da mesma etapa ou uma segunda cobrança prevista pela régua?”. Se o time responder “dois envios da mesma etapa”, a próxima pergunta pode ser “O que identifica essa etapa para vocês e em qual situação um novo lembrete é legítimo?”. O Copilot deve aguardar as respostas e usá-las nos critérios de aceite. A [história de boletos](example/01-cobranca-de-boletos-em-atraso.md) mostra um card preenchido após essas decisões. Para receber logo uma versão preliminar, peça “gere um rascunho agora com o que já sabemos”.

Ao alterar a ficha curta, a triagem ou os critérios de revisão da skill, confira também o prompt independente para manter as duas formas de uso alinhadas.

#### Como avaliar a conversa

O Copilot percorre problema, escopo, critérios de aceite (CAs), condições para iniciar (DoR) e condições para concluir (DoD). A cada resposta, ele explica o que já ficou definido e investiga a lacuna que mais afeta a etapa. No caso dos boletos, três respostas ajudam a conferir esse comportamento:

- **CA** — Diante de “o lembrete só pode sair uma vez”, o Copilot deve esclarecer o que identifica uma repetição e qual resultado observar durante um reprocessamento.
- **DoR** — Diante de “a consulta ao provedor ainda não está disponível”, deve perguntar qual etapa depende da consulta e se o time consegue iniciar alguma parte da entrega. O parecer deve indicar o alcance do impedimento.
- **DoD** — Diante de “QA vai testar”, deve perguntar qual teste comprova o CA, onde ficará o registro e quem validará o resultado. O teste fica planejado até existir evidência de execução.

Ao final, o card reúne a ficha curta, o parecer de prontidão e o plano de comprovação da entrega.

### Outros pedidos

- Pedido novo — “O painel apresenta dados antigos na reunião da manhã. Ajude a definir a melhoria.”
- Card existente — “O card prevê exportar em CSV. O cliente informa que os filtros somem na exportação. Revise o aceite.”
- Plataforma — “A renovação do certificado já tem procedimento e janela aprovados. Qual o encaminhamento?”

Confira as decisões esperadas nos [cenários](.agents/skills/engineering-story-refinement/references/06-exemplos-validacao.md). O pacote contém instruções e referências em Markdown. Uma implantação no Vertex AI requer uma aplicação que carregue esses arquivos e gerencie o estado da conversa.

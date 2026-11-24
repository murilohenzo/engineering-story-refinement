# Refinamento de histórias de engenharia

A skill transforma um pedido em história verificável ou melhora um card existente. O fluxo comum atende diferentes engenharias. As referências de plataforma preservam o guia do time para operação, capacidade, GMUD, prontidão e aceite.

## Usar no Codex

Abra este repositório e peça, por exemplo, “Use $engineering-story-refinement para revisar este card com base no relato do cliente. Preserve as decisões confirmadas e destaque o que mudou”. Para usar em outro projeto, copie a [pasta da skill](.agents/skills/engineering-story-refinement/) inteira para a pasta .agents/skills desse projeto.

## Experimentar o fluxo

### Usar o prompt no GitHub Copilot

Abra o [prompt de refinamento](.github/prompts/refinar-historia.prompt.md), copie o texto a partir de “Refinar uma história de engenharia” para o Copilot Chat e acrescente o pedido ou o card existente. O texto é autocontido e também pode ser usado fora deste repositório. Em uma sessão **Local** do VS Code, com o projeto aberto, o mesmo arquivo pode ser invocado como `/refinar-historia`. A documentação do VS Code descreve a disponibilidade do comando por tipo de sessão. [Prompt files no VS Code](https://code.visualstudio.com/docs/agent-customization/prompt-files)

Por exemplo, envie “Hoje Contas a Receber confere boletos vencidos manualmente e às vezes envia lembretes repetidos. Crie um rascunho e indique o que precisamos decidir sobre a régua”. A resposta deve propor o problema e o aceite para duplicidade e deixar a cadência em aberto. Para comparar, a [história de boletos](example/01-cobranca-de-boletos-em-atraso.md) mostra o card depois de o time escolher os dias de envio.

Ao alterar a ficha curta, a triagem ou os critérios de revisão da skill, confira também o prompt independente para manter as duas formas de uso alinhadas.

### Outros pedidos

- Pedido novo — “O painel apresenta dados antigos na reunião da manhã. Ajude a definir a melhoria.”
- Card existente — “O card prevê exportar em CSV. O cliente informa que os filtros somem na exportação. Revise o aceite.”
- Plataforma — “A renovação do certificado já tem procedimento e janela aprovados. Qual o encaminhamento?”

Confira as decisões esperadas nos [cenários](.agents/skills/engineering-story-refinement/references/06-exemplos-validacao.md). O pacote contém instruções e referências em Markdown. Uma implantação no Vertex AI requer uma aplicação que carregue esses arquivos e gerencie o estado da conversa.

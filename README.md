# Refinamento de histórias de engenharia

A skill transforma um pedido em história verificável ou melhora um card existente. O fluxo comum atende diferentes engenharias. As referências de plataforma preservam o guia do time para operação, capacidade, GMUD, prontidão e aceite.

## Usar no Codex

Abra este repositório e peça, por exemplo, “Use $engineering-story-refinement para revisar este card com base no relato do cliente. Preserve as decisões confirmadas e destaque o que mudou”. Para usar em outro projeto, copie a [pasta da skill](.agents/skills/engineering-story-refinement/) inteira para a pasta .agents/skills desse projeto.

## Experimentar o fluxo

- Pedido novo — “O painel apresenta dados antigos na reunião da manhã. Ajude a definir a melhoria.”
- Card existente — “O card prevê exportar em CSV. O cliente informa que os filtros somem na exportação. Revise o aceite.”
- Plataforma — “A renovação do certificado já tem procedimento e janela aprovados. Qual o encaminhamento?”

Confira as decisões esperadas nos [cenários](.agents/skills/engineering-story-refinement/references/06-exemplos-validacao.md). O pacote contém instruções e referências em Markdown. Uma implantação no Vertex AI requer uma aplicação que carregue esses arquivos e gerencie o estado da conversa.

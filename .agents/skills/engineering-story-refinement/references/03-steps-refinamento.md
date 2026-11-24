# Steps de refinamento — roteiro preenchível

Para cada etapa, registre resposta, estado (confirmado/hipótese/proposta/a definir/N/A justificado), fonte e pendência. Use as perguntas relevantes, não um interrogatório. Se houver lacuna que impede início, mantenha o card em rascunho/refinamento ou bloqueado e indique o próximo passo.

| Step | Perguntas de investigação | Saída mínima |
|---|---|---|
| 01 Triagem | Qual solicitante, impacto, prazo, frente? É rotina, incidente, mudança, história, épico ou spike? | Rota, tipo, vínculo e justificativa. |
| 02 Problema | O que ocorre hoje? Quem sofre? Qual evidência? Causa confirmada ou hipótese? | Problema e público claros. |
| 03 Valor | O que melhora para consumidor/time, área e empresa? O que acontece se esperar? | Benefícios diretos/indiretos, objetivo e evidência esperada. |
| 04 Resultado | Qual estado futuro? Como observar a diferença? Até quando e por quê? | Resultado verificável e prazo/condição. |
| 05 Escopo | Que entrega e ambiente? O que fica de fora? Cabe em um ciclo? | Recorte e limites. |
| 06 Técnica | Quais componentes e integrações? Alternativas, restrições, decisão, requisitos não funcionais? | Estratégia proposta ou acordada, decisões abertas. |
| 07 Riscos e dependências | Quem entrega o quê? Quando? É pré-requisito? Que bloqueio, mitigação, GMUD/rollback e aprovação? | Registro acionável de riscos e dependências. |
| 08 Viabilidade | Esforço acordado? Capacidade líquida e reserva? Pessoas? Prazo real? Item deslocado? | Viabilidade e decisão necessária. |
| 09 Aceite | Como comprovar cada resultado? Quem valida? Que dados/cenários e evidências? | Critérios observáveis e plano de teste. |
| 10 Qualidade | Há coerência problema→resultado→valor→escopo→aceite? INVEST? DoR? | Parecer, lacunas e estado recomendado. |
| 11 Consolidação | O que foi acordado? O que falta? Quem age e quando? | Card, pendências, histórico e próximo passo. |

## Roteamento proposto

- Incidente crítico: fluxo de incidentes imediatamente; não aguardar refinamento. Gerar história posterior para correção estrutural se pertinente.
- Chamado rotineiro/GMUD padronizada: fluxo operacional do guia, com vínculo e procedimento. Mudança que exige descoberta ou desenvolvimento pode originar história vinculada, respeitando o procedimento de GMUD.
- História: resultado verificável para consumidor, operação ou controle, com escopo delimitado.
- Épico: objetivo amplo a dividir em incrementos que entregam resultados úteis.
- Spike: investigação com pergunta, limite de tempo a acordar, evidência e decisão esperada; não prometer implementação.
- Tarefa técnica: atividade subordinada a uma história, ou item técnico com resultado próprio verificável e valor rastreável.

## Facilitação e soft skills

Com solicitante, alinhe problema, urgência e resultado; com executor, negocie abordagem e estimativa; com validador, combine testes e evidências; com referência, trate bloqueios e dependências; com responsável pela prioridade, explicite trade-offs. Formule divergências sem atribuir culpa: “Para validar X até Y, precisamos de Z; sem isso, o risco é W”.

## Ordem de perguntas quando faltam muitos dados

Primeiro: problema/beneficiário, resultado e prazo. Depois: escopo e aceite. Em seguida: dependências/aprovações, validador e capacidade. Questões técnicas reversíveis podem ficar para implementação se não comprometerem viabilidade/aceite; não esconder riscos materiais. Proponha responsável por esclarecer, sem atribuição unilateral.

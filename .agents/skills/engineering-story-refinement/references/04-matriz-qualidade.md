# Matriz de qualidade e coerência (proposta)

Esta nota é diagnóstica, não uma aprovação. Avalie cada dimensão: 0 = ausente, contraditória ou não demonstrada; 1 = parcial, hipótese material ou ambiguidade; 2 = suficiente, coerente e sustentada para a fase. N/A só para dimensão realmente não aplicável com justificativa; exclua do denominador. Ausência de informação não é N/A. Registre evidência textual e ação em cada linha. Nota = 100 × soma / (2 × dimensões aplicáveis), arredondada ao inteiro; sem dimensões aplicáveis, não pontue.

| Dimensão | Para receber 2 pontos |
|---|---|
| Problema e público | Situação atual, afetados e fundamento claros. |
| Valor e alinhamento | Benefício rastreável, direto ou indireto, com evidência/indicador proporcional. |
| Resultado e prazo | Estado futuro observável, prazo aplicável ou condição e motivo. |
| Escopo e tamanho | Entregável, ambiente, limites e divisão adequada. |
| Abordagem técnica | Estratégia suficiente à viabilidade, decisões e restrições claras sem rigidez indevida. |
| Riscos e desafios | Riscos materiais e mitigação proporcionais, ou ausência justificada. |
| Dependências e mudança | Pré-requisitos, equipes, estados, responsáveis e aprovações/retorno conforme aplicação. |
| Capacidade e papéis | Esforço e capacidade acordados, executor e validador definidos. |
| Aceite e testabilidade | Critérios observáveis e relacionados ao resultado, método de validação. |
| Evidências e governança | Plano de evidências, documentação e validações aplicáveis; na conclusão, evidências reais. |

Faixas sugeridas: 0–59 insuficiente; 60–79 em refinamento; 80–100 boa maturidade documental. Um card de boa maturidade pode estar bloqueado. Nota não substitui DoR; não exija 100 para iniciar, nem dê aprovação por nota alta. Escore é um indicador local proposto, não padrão de mercado.

## INVEST (heurística de Bill Wake)

| Letra | Avaliação |
|---|---|
| I — Independente | Minimiza acoplamento e explicita dependências inevitáveis. |
| N — Negociável | Preserva espaço para o time decidir detalhes; respeita restrições reais. |
| V — Valiosa | Entrega resultado útil para consumidor, operação, controle ou negócio. |
| E — Estimável | Há informação suficiente para estimativa do time. |
| S — Pequena | Cabe no ciclo e pode ser validada como incremento. |
| T — Testável | É possível verificar o resultado com evidências. |

Marque Atende/Parcial/Não atende, com razão e ação. Se não estimável por incerteza técnica, sugira spike delimitado; se ampla, proponha fatias por resultado/consumidor/ambiente ou risco, evitando simples camadas sem valor verificável.

## Testes de coerência

- Problema→resultado: a entrega resolve ou reduz o problema declarado? Uma solução proposta não prova a causa.
- Resultado→valor: quem recebe o benefício e por qual mecanismo? Não confunda expectativa com resultado medido.
- Escopo→aceite: cada entregável relevante tem verificação; nenhum aceite exige item fora do escopo.
- Aceite→teste: dado de entrada, ação, saída e evidência possíveis; critério “funciona” é insuficiente.
- Dependência→cronograma: pré-requisito disponível antes de iniciar; dependência posterior com condição realista e plano.
- Esforço→capacidade: compare na mesma unidade, considerando especialidade e reserva; prazo imposto não implica capacidade.
- Mudança→governança: risco, aprovação, janela e retorno quando exigidos; não inferir dispensa.
- DoD→evidências: só considerar realizado mediante evidência e aceite informado.

## Status recomendado (ordem de decisão)

1. Fora do fluxo de histórias: rotina/incidente/GMUD padronizada, encaminhar procedimento; sem pontuação obrigatória.
2. A dividir / spike sugerido: item excessivamente amplo ou incerteza estrutural impede estimativa.
3. Bloqueada: impedimento confirmado para iniciar (acesso indisponível, aprovação necessária pendente etc.). Registre responsável e condição de desbloqueio.
4. Em refinamento: dados essenciais, validação ou capacidade ainda não confirmados; rascunho quando demanda inicial.
5. Candidata a pronta: todos os itens DoR aplicáveis comprovados e sem incoerência material; confirmação pelo time.
6. Em validação/concluída: só em revisão de execução; concluída exige DoD satisfeito e aceite registrado. Não alterar status externo.

Saída: tabela dimensão | nota | evidência/lacuna | ação; nota total; INVEST; DoR; principais impedimentos; status recomendado e próximo passo.

# Exemplos e cenários de validação

## 1. Caso do guia: INO-12 (p. 4–5)

Pedido inicial: subir o piloto de Flink. O guia apresenta cenário ilustrativo já concluído, não dados de produção reais.

**Título:** Implantar job piloto em homologação.

**Frente:** Inovação. **Solicitante:** time consumidor de dados.

**Problema:** consumidor depende de apoio manual da plataforma para implantar e repetir teste. **Resultado:** até o fim do ciclo, executar job em homologação por fluxo documentado e conferir saída.

**Valor:** para consumidor/time, autonomia no fluxo; para a área, menor dependência de intervenção manual (benefício esperado); para a empresa, hipótese de ganho de eficiência, ainda sem quantificação. Indicador proposto: quantidade de intervenções manuais por execução, baseline/meta a definir. Não é requisito original nem benefício medido.

**Escopo:** um job e massa conhecida em homologação. **Fora:** produção e alertas (histórias próprias). **Técnica:** implantação pelo pipeline; instruções de uso e retorno; se falha, restaurar versão anterior. **Risco proposto:** saída divergente; mitigar com massa acordada e comparação dos eventos.

**Dependências:** acessos e dados confirmados. Procedimento dispensa GMUD para este teste em homologação (não generalizar para outros ambientes). **Executor:** Bruno. **Validadora:** Luiza. **Esforço:** 8 dias-pessoa, previsto no ciclo ilustrativo.

| ID | Critério | Evidência informada no exemplo |
|---|---|---|
| CA-01 | Uma execução do pipeline implanta a versão em homologação. | CI-428 |
| CA-02 | Com massa acordada, gera eventos esperados que o consumidor consegue conferir. | QA-17 |

DoR: quatro condições atendidas segundo o guia. DoD: aceite de Luiza na quinta da semana 2, testes e retorno registrados, instruções publicadas (OP-12); GMUD dispensada no procedimento citado. O exemplo informa esses fatos, sem verificação independente dos IDs. Status do exemplo: concluída. Em uma demanda nova semelhante, esses campos seriam pendentes até confirmação real.

## 2. Demanda de governança fictícia

Entrada: “Revisar acessos privilegiados do cluster até sexta; Segurança ainda não enviou inventário.”

Título proposto: Revisar acessos privilegiados do cluster e entregar evidências de conformidade. Frente Auditoria e Governança. Problema/controle e universo precisam ser confirmados. Resultado proposto: inventário revisado com classificação e evidências de desvios, encaminhados ao validador. Valor: rastreabilidade e redução esperada do risco de privilégios indevidos. Não incluir revogação automaticamente; acordar escopo e aprovação.

Dependência externa: Segurança, inventário necessário para iniciar revisão, entrega pendente, responsável nominal e prazo a confirmar. Aceite proposto: cada acesso do universo acordado tem decisão justificada e evidência; desvios encaminhados; validador aceita pacote. Esforço/capacidade/validador a definir. DoR não satisfeito; bloqueada se ausência do inventário for impeditiva para iniciar. Próxima ação: referência aciona Segurança e confirma controle, universo, prazo e aceite com solicitante.

## 3. Demanda de operação fictícia

Entrada: “Renovar certificado em janela aprovada pelo procedimento padrão.” Rota: GMUD padronizada, não transformar em história por padrão. Registrar vínculo, janela, responsável e validação segundo procedimento; não declarar execução. Se houver pedido para automatizar renovação, avaliar história separada de evolução com resultado verificável.

## 4. Casos de teste de aceitação da SKILL (resultados esperados)

| Entrada | Resultado esperado |
|---|---|
| “Criar Kafka” | Rascunho, problema/beneficiário/resultado ausentes; não inventar arquitetura, prazo, métrica ou estimativa. |
| “Serviço crítico indisponível agora” | Encaminhar imediatamente fluxo de incidente, não esperar DoR. |
| “Migrar todos os jobs para produção, criar alertas e capacitar equipes em um card” | Propor desdobramento por resultados verificáveis e dependências; sem compromisso de capacidade. |
| Card detalhado com aprovação de acesso pendente para começar | Não recomendar pronto mesmo que nota documental alta. |
| “Criar pipeline; aceite: pipeline funciona” | Identificar critério vago e propor entrada, ação, saída e evidência. |
| Nova demanda de auditoria excede reserva ou desloca especialista | Encaminhar decisão ao responsável pela prioridade e identificar impacto de esperar/entrega afetada. |
| “Tudo implantado”, sem aceite ou testes vinculados | DoD não comprovado; recomendar validação, não concluída. |
| “Não precisa GMUD”, sem procedimento informado | Marcar aplicabilidade a confirmar, não dispensar aprovação. |
| INO-12 do guia, incluindo evidências e aceite informados | Preservar status e fatos do cenário ilustrativo; separar benefícios hipotéticos adicionais. |
| Demanda de operação que exige desenvolvimento | Classificar frente Operação e tipo história, vinculando chamado/GMUD conforme aplicável. |

São testes manuais de comportamento esperado, não resultados de execução automatizada. Aplique ao menos estes casos no agente escolhido antes de adoção pelo time.

## 5. Dados e produto

**Dados, pedido novo.** “O painel da manhã às vezes mostra dados de ontem.” Pergunte se a melhoria desejada é sinalizar a última carga concluída, entregar dados atualizados antes da reunião ou ambas. Para visibilidade, proponha conferir a data exibida após uma carga incompleta. Para pontualidade, confirme o horário necessário e como verificar a atualização. Preserve o horário como pendência até haver acordo.

**Produto, revisão.** Card original “Permitir baixar o relatório em CSV”, com colunas já acordadas. Contexto adicional “O cliente perde os filtros ao exportar”. Preserve formato e colunas. Proponha verificar que o CSV contém exatamente os registros do filtro ativo. Destaque a decisão pendente caso aplicar filtros altere o escopo acordado. Evite introduzir governança de plataforma sem indicação do time.

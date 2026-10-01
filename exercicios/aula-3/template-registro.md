# Registro individual — AV1.3

**Limite: uma página.** Estudante: Daniel Albino de Castro Ferraz — Data: 01/10/2026
**O que a listagem e a documentação precisam cumprir, conforme R2/R4:** A listagem deve incluir chamados com estado `aberto` e `em_andamento`, excluir chamados `fechado` e preservar a ordem de entrada. A documentação deve descrever o comportamento proposto pela regra em questão.

| Caso / estado a verificar | Entrada (IDs e ordem) | IDs esperados na ordem | Obrigação de R2 e como verificar |
|---|---|---|---|
| 1 / aberto | [TR-33] | [TR-33] | `aberto` deve ser incluído.<br>Verificar se TR-33 permanece na saída, pois seu estado é `aberto` |
| 2 / em_andamento | [TR-31] | [TR-31] | `em_andamento` deve ser incluído.<br>Verificar se TR-31 permanece na saída, pois seu estado é `em_andamento` |
| 3 / fechado | [TR-32] | [] | exclui `fechado`.<br>Verificar se TR-32 não aparece na saída, pois seu estado é `fechado` |

**Entrada combinada TR-31, TR-32, TR-33 → IDs esperados:** [TR-31, TR-33]
**Como conferiria a ordem (compare a posição dos IDs na entrada e na saída esperada):** Como TR-32 é excluído da saída, a ordem dos restantes deve ser preservada, portanto o resultado da saída seria [TR-31, TR-33] visto que TR-31 aparece antes de TR-33 na entrada.
**Documentação proposta (até três frases):** A função `listar_ativos` retorna chamados apenas com estado `aberto` ou `em_andamento`. Chamados com estado `fechado` são excluídos. A ordem original dos chamados incluídos é preservada na saída.

**Etapa em que admitiria IA / tarefa que ela faria / pessoa responsável por conferir:** A IA poderia auxiliar na elaboração inicial dos casos de testes, sugerindo e implementando casos de entrada e saída a partir de R2. O responsável pelos testes conferiria se os casos estão realmente aderentes à regra.
**O que essa pessoa deve verificar antes de aprovar:** Conferir se existe pelo menos um caso para cada estado (`aberto`, `em_andamento` e `fechado`). se as saídas estão coerentes com R2 e se em casos combinados a ordem é preservada.
**Alternativa sem IA e comparação:** Sem IA os casos seriam elaborados manualmente a partir de R2. Isso aumenta o tempo de elaboração, porem reduz o risco de ser incluída uma sugestão de teste incorreta, permitindo uma revisão mais rápida.
**O que os casos não verificam e o que me faria rever a aprovação:** O caso nao verifica uma entrada contendo varios chamados ativos do mesmo estado, nem uma lista vazia por exemplo. Eu reveria a aprovação caso novos casos revelassem que a implementação nao respeita a R2 em determinado cenário.

**Origem dos dados e como fiz a análise:** entrada fictícia do enunciado; esperado por contrato: Saídas calculadas manualmente com base na R2; inspeção própria: conferencia dos estados e da ordem dos IDs; execução opcional (comando/resultado, se houver): não realizada.
**Uso de IA na elaboração deste registro:** ferramenta e modelo visíveis: GPT-5.6 Sol; tarefa delegada e contexto: Apoio para interpretar o enunciado e entender como preencher cada parte; trecho aproveitado: orientações sobre como interpretar os campos do template; minha verificação/intervenção: formulei as respostas com base nas regras e na massa de dados fornecidas pela atividade, conferindo pessoalmente os resultados e utilizando a IA apenas como apoio de interpretação. O raciocínio e as decisões registrados são meus.

**Revisão:** [x] três estados; [x] ordem; [x] texto; [x] aceite/limite; [x] uma página.

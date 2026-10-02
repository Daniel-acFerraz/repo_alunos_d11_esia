# Entrega individual — AV2

Estudante: ___ · Data: ___ · Via: inspeção / execução opcional
**Limites:** análise até duas páginas; anexo técnico até duas páginas. [Enunciado](README.md).

## Análise

**1. Recorte e requisito.** Função/tarefa, quem usa o resultado e limites de entrada: A função a ser avaliada é `pode_visualizar_proposta`, que é responsável por decidir se um usuario de determinado departamento pode ou  não visualizar um chamado. A saída dessa função seria usada pela pessoa/código responsável para definir se o chamado pode ser visualizado por determinado usuário. A análise considera apenas entradas válidas no caso fictício, não considera autenticação real, API, persistencia nem outras configurações e validações externas.
R3/R4 em minhas palavras e critério de aceite definido antes da verificação: Para os casos apresentados, considero adequado se T1 e T2 permitirem acesso, T3 e T4 negarem acesso e a documentação descrever esse mesmo comportamento, ficando assim aderente com a R3.

**2. Estratégia.** Eixos da matriz, motivo dos quatro casos e o que mantenho constante:<br>Eixos da matriz: Primeiro eixo confere a relação entre o departamento do chamado e o departamento do solicitante (se é igual ou diferente). O segundo eixo é sobre o estado do chamado (aberto o fechado);<br> Os quatro casos cruzam essas duas condições para verificar se a decisão depende apenas do departamento, como exige R3, ou se o estado está interferindo no resultado.<br>O que mantenho constante: Mantenho o parametro de departamento (`Oficina`) constante  nos quatro casos e mantenho a estrutura das entradas válida, variando as demais condições para comparar os cenários.<br>
Caso decisivo e caso de controle, com justificativa: O caso decisivo seria o T2, pois representa um chamado `fechado` do mesmo departamento solicitante, oque, segundo o R3, o acesso deveria ser permitido, então esse caso demonstra que o estado está interferindo indevidamente na decisão. O melhor caso de controle seria o T1 pois representa um chamado `aberto` do mesmo departamento e permite comparar com T2, mantendo a relação de departamento igual e alterando apenas o status.

**3. Evidência e interpretação.** Principais achados com referência a linhas T1–T4 e trechos E1–E3 do anexo: <br>T1, T3 e T4 apresentam comportamento compatível com R3. T2 é um caso que mostra exatamente a falha do código em relação à regra, visto que que mesmo com o departamento adequado, a saída foi incorreta devido à influencia do estado, algo que nao deveria acontecer segundo R3. E1 estabelece que o acesso depende apenas do departamento do chamado e do usuário, e estado ou prioridade nao deveria influenciar. E2 adiciona a condição `chamado["estado"] != "fechado"`. E3 apresenta relação entre estado e disponibilidade da chamada(Chamados abertos ou em andamento ficam disponíveis para o departamento correspondente; chamados fechados ficam indisponíveis.).
Relação entre contrato, comportamento do código e documentação: O contrato estabelece que o acesso depende apenas do departamento da chamda ser compatível com o departamento do usuário. O código adiciona relação de estado para decidir se o chamado estará disponivel  ou não, e a documentação cita o mesmo comportamento, como se a a disponiblidade dependesse tambem do estado do chamado. Levando isso em consideração, da para concluir que a documentação esta de acordo com o código apresentado, porém ambos estão errados em relação ao contrato.

**4. Decisão comparada.** Encaminhamento do código e da documentação, com fundamento: Sobre o código eu rejeitaria, pois ele claramente adiciona a condição de estado à regra de visibilidade, que vai contra R3 ("...independentemente de estado ou prioridade"). Sobre a documentação, eu tambem rejeitaria pelo mesmo motivo.
Alternativa considerada / comparação sob o mesmo critério: Mandaria o código e documentação para revisão, com objetivo de remover o parametro de condição de estado na decisão. Dessa maneira ambos atenderiam corretamente a R3/R4, visto que apenas o departamento seria decisivo, como manda a regra.
Ajuste proposto, se aplicável, e revalidação (linhas do anexo): Alterar código removendo a linha `and chamado["estado"] != "fechado"` e na documentação remover o trecho `Chamados abertos ou em andamento ficam disponíveis para o departamento correspondente; chamados fechados ficam indisponíveis.`. Após as mundaças repetir T1-T4 e verificar as mesmas condições de aceite definidas no início.
Responsável pelo aceite e condição para rever a decisão: Responsável: Responsável técnico ou responsável pela regra de negócio.<br>Condição para rever: novo requisito, novos testes falhando ou mudança no contrato.

**5. Procedência e limites.** Artefatos didáticos simulados utilizados: Utilizei o contrato R3/R4, código candidato, documentação candidata, dados V-01 a V-04, todos fornecidos pelo material didático.
O que observei em execução / inferi por inspeção / apenas propus: Nao executei o código. Inferi os retornos pela avaliação lógica das duas condições apresentadas no código. Propus a remoção da dependência de estado e reavaliar T1-T4.
Limite concreto da cobertura e consequência para minha decisão: A análise não cobre chamados com status `em_andamento`. Por isso minha decisão se restringe aos cenários apresentados (T1-T4) e não permite concluir sobre os demais cenários possiveis.
**Uso de IA na elaboração deste registro:** ferramenta e modelo visíveis: GPT-5.6 Sol; tarefa delegada e contexto: Apoio para interpretar o enunciado e entender como preencher cada parte; trecho aproveitado: orientações sobre como interpretar os campos do template; minha verificação/intervenção: formulei as respostas com base nas regras e na massa de dados fornecidas pela atividade, conferindo pessoalmente os resultados e utilizando a IA apenas como apoio de interpretação. O raciocínio e as decisões registrados são meus.

## Anexo técnico — trechos essenciais

**Dados e condições comuns:** referência aos registros de insumos.md ou dicionários completos, departamento solicitante e valores mantidos: ___

| Caso | Entrada/referência + solicitante | Relação de departamento / estado | Esperado por R3 | Retorno do candidato | Status observado/inferido | Interpretação |
|---|---|---|---|---|---|---|
| T1 | | Igual / aberto | | | | |
| T2 | | Igual / fechado | | | | |
| T3 | | Diferente / aberto | | | | |
| T4 | | Diferente / fechado | | | | |

**E1 — trecho do contrato e localização:** ___
**E2 — trecho do código + percurso lógico de um caso decisivo e um controle:** ___
**E3 — trecho da documentação e confronto com R3/código:** ___
**Execução, se escolhida — ambiente, comando e trecho de saída:** ___ / não realizada.
**Alternativa/ajuste e revalidação:** comportamento proposto: ___; T1–T4 após ajuste (esperado/retorno/status): ___; limite: ___.

**Checklist:** [ ] 4 combinações; [ ] critérios prévios; [ ] código e texto; [ ] status; [ ] alternativa; [ ] limites/IA; [ ] 2+2 páginas.

# Registro individual — AV1.2

**Limite: uma página.** Estudante: Daniel Albino de Castro Ferraz — Data: 30/09/2026
**Critérios antes da análise:** como conferir a classificação por R1: Somar `impacto + urgencia` e em seguida aplicar as classificações de acordo com os parametros definidos:<br>
>=5 -> alta
3 ou 4 -> media
<3 -> baixa

O que seria necessário para sustentar uma afirmação sobre outras entradas ou repetições: testar mais entradas e mais repetições, de preferencia incluindo casos de borda com valores mínimos e máximos para impacto e urgencia, em condições controladas, para verificar se o comportamento se mantém.

| Entrada de A (impacto, urgência) | Cálculo e esperado por R1 | Trecho da resposta A | Conclusão por inspeção |
|---|---|---|---|
| (2, 3) | `2+3 = 5` esperado -> alta  | media | Não coincide. O modelo simulado falhou em classificar corretamente de acordo com a R1 |
| (3, 1) | `3+1 = 4` esperado -> media | alta | Não coincide. O modelo simulado falhou em classificar corretamente de acordo com a R1 |

**B — trecho analisado:** “Repeti três vezes o pedido ‘classifique impacto=2, urgencia=3’. As três saídas foram ‘alta’. Isso prova que o modelo é determinístico e sempre entrega a classificação correta, inclusive em outros chamados.”
**O que posso concluir sobre o par citado em B:** Para o resultado daquele par específico, a classificação ficou de acordo com R1.
**Afirmação geral de B: o que falta para sustentá-la:** Testar mais entradas e mais repetições, pois um único par repetido tres vezes nao garante que "modelo é determinístico e sempre entrega a classificação correta, inclusive em outros chamados". Demonstra apenas que naquela situação extremamente específica ele funciona corretamente.
**Contraexemplo ou condição não coberta:** O caso (2,1) por exemplo, nao foi testado em B. Pela R1, 2 + 1 = 3, portanto deveria resultar em media. Esse é um caso de fronteira entre baixa e media que os dados apresentados em B não cobrem.

**Decisão A + motivo:** Rejeitar. Os dois resultados estão incorretos segundo R1.
**Decisão B + motivo:** Aceitar parcialmente. A classificação do caso (2,3) esta correta de acordo com R1. Ela poderia fazer parte de um conjunto maior de caso de testes para uma conclusão mais ampla e generalista, porem, ela por si só nao é o suficiente para chegar nessas conclusões.
**Alternativa de verificação e condição que mudaria uma decisão:** Para a decisão B, testar mais casos seria um passo natural para mudar essa decisão, podendo se tornar 'aceita' caso os testes cobrissem todas as possibilidades e ficassem de acordo com R1 ou 'rejeitada' caso os testes seguintes falhasse. Especificamente para a afirmação de ser determinístico ainda teriam que ser conferidas outras informações como configuração, versão e condições de execução.

**Origem dos dados e como fiz a análise:** respostas didáticas simuladas; cálculos/inspeções próprios: Aplicação manual da R1 e comparação dos resultados com os trechos fornecidos nas respostas A e B; execução real: não realizada. Tokens/custo/latência/configuração: não informados.
**IA na produção do registro:** não utilizada / ferramenta-modelo visível: não utilizada; tarefa/contexto: ___; trecho aproveitado e verificação própria: ___.

**Revisão:** [x] critérios; [x] dois pares; [x] análise de B; [x] decisões/limites; [x] uma página.

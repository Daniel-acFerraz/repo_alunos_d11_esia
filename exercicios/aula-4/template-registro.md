# Registro individual — AV1.4

**Limite: uma página.** Estudante: Daniel Albino de Castro Ferraz — Data: 05/10/2026
**Critério de aceite por R2:** Retornar todos chamados com estado `aberto` e `em_andamento`, excluir os chamados fechado e retornar os chamados na mesma ordem relativa em que que aparecem na entrada. Para a execução de `listar_ativos([TR-41, TR-42, TR-43, TR-44])`, a saída deve ser `TR-41, TR-42, TR-44`.

| Entrada | IDs esperados por R2 | IDs do candidato | Status: inferido/observado | Mecanismo/trecho essencial |
|---|---|---|---|---|
| TR-41, TR-42, TR-43, TR-44 | `TR-41, TR-42, TR-44` | `TR-42, TR-44, TR-41`  | Inferido por inspeção | `return sorted(ativos, key=lambda c: c["impacto"] + c["urgencia"], reverse=True)`<br> Esse trecho ordena o resultado por ordem de prioridade ao invés de manter a ordem origina, como manda R2. |

**Teste entregue — o que verifica e o que não consegue distinguir:** O teste verifica se os chamados `ativos` permanecem e se o chamado fechado é `excluído`. Porem, como a ordem fornecida ja está em ordem de prioridade, ele não consegue apontar o comportamento falho que o `return sorted(ativos, key=lambda c: c["impacto"] + c["urgencia"], reverse=True)` causa, visto que a ordem retornada será de fato a ordem de entrada.<br>
**Trecho do teste (entrada e comparação de IDs) que sustenta minha análise:** Entrada do teste: `TR-42, TR-44, TR-41, TR-43`. Comparação esperada: `["TR-42", "TR-44", "TR-41"]`. Essa sequência coincide tanto com a ordem filtrada quanto com a ordenação descrescente por impacto + urgencia, tornando o resultado não conclusivo quanto à preservação da ordem exigida por R2.<br>
**Decisão (aceitar, aceitar com condições ou rejeitar) e motivo:** Rejeitar. A filtragem dos estados está correta, mas a função claramente altera a ordem dos chamados baseado na soma de `impacto + urgencia`, violando a exigência de preservar a ordem de entrada citada por R2.<br>
**Comparação entre manter e ajustar / responsável pelo aceite:** Manter a proposta preservaria a filtragem correta porem com ordenação violando R2. Ajustar a função paar retornar diretamente a lista filtrada seria a escolha natural para ficar de acordo com o contrato. O aceite deveria ficar com o responsável pela revisão técnica da proposta.<br>
**Ajuste proposto (texto ou código):**  ```
def listar_ativos_proposta(chamados):
    return [
        c
        for c in chamados
        if c["estado"] in ("aberto", "em_andamento")
    ]
    ```

| Caso para conferir o ajuste: entrada e ordem | IDs esperados | Resultado previsto ou observado / status |
|---|---|---|
| `TR-41, TR-42, TR-43, TR-44` |  `TR-41, TR-42, TR-44` | Previsto por inspeção: `TR-41, TR-42, TR-44`<br> De acordo com R2 |

**Limite remanescente e condição para rever o parecer:** O limite são os casos de testes utilizados. No caso apresentado para conferir a ordem de entrada foi `TR-41, TR-42, TR-43, TR-44`, nao cobre entradas vazias ou outras combinações de registros. Eu reveria o parecer caso ao testar a função ajustada uma nova verificação mostrasse que a ordem ainda não esta sendo preservada ou que algum estado esta sendo tratado incorretamente.<br>
**Origem dos dados e da análise:** candidato/teste/entrada simulados; <br>método próprio: inspeção;<br> comando e trecho de saída, se executado: não realizado.<br>
**Uso de IA neste registro:** não utilizada; tarefa/contexto: ___; trecho aproveitado e minha verificação: ___.

**Revisão:** [x] comparação com R2; [x] alcance do teste; [x] ajuste/revalidação; [x] status; [x] uma página.

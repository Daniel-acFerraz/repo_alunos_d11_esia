# Entrega individual — AV3

Estudante: Daniel Albino de Castro Ferraz · Data: 08/10/2026 · Caso/recorte: Assistência de IA para propor testes e documentação na manutenção da Fila Clara.
**Limites:** parecer até três páginas; evidências/referências até duas páginas. [Enunciado](README.md).

## Parecer

**1. Recomendação e problema.** Recomendo  para a tarefa adoção condicionada da assistência de IA, cujo beneficiário é a equipe de manutenção da Fila Clara e resultado esperado é obter propostas iniciais de testes e documentação que possam ser avaliadas pela equipe. As restrições relevantes são que ainda não houve execução com usuários, as condições para uso de dados reais e ferramentas externas não estão definidas e as propostas geradas precisam ser verificadas antes do uso.

| Alternativa | Processo e recursos | Benefício esperado / pressuposto | Limite, consequência do erro e esforço de verificação |
|---|---|---|---|
| A — sem IA | A equipe analisa o contrato e os dados disponíveis e elabora manualmente os testes e a documentação. | Mantém todo o processo diretamente sob responsabilidade da equipe e não adiciona riscos os riscos atrelados ao uso de uma ferramenta externa (como segurança dos dados por exemplo). | Todo o trabalho de elaboração fica com a equipe e ainda precisa ser revisado (mesmo que de forma menos minuciosa) e conferido  contra o contrato, pois erros humanos também podem produzir testes ou documentação incorretos. |
| B — outra alternativa | A IA gera propostas iniciais de testes e documentação a partir dos materiais permitidos, e a equipe de manutenção confere os artefatos antes de utilizá-los. | Fornece uma proposta inicial que pode apoiar o trabalho da manutenção economizando tempo na elaboração inicial. Eventual ganho de esforço ou tempo real ainda precisaria ser medido. | Pode gerar testes ou documentação que por si só pareçam fazer sentido, mas incorretos. Um erro aceito sem revisão pode registrar comportamento diferente do contrato, portanto cada proposta exige verificação humana minuciosa antes do uso. |

**Minha comparação e razão para a recomendação:** As duas alternativas são viáveis, porém a alternativa com IA permite avaliar a assistência na elaboração dos artefatos sem substituir a decisão da equipe. Como ainda não existem resultados que comprovem ganho de qualidade ou esforço e já foram identificados casos em que propostas divergiam do contrato, considero mais adequado avançar de forma condicionada, mantendo a revisão humana e as restrições de uso já identificadas.<br>

**2. Autonomia e responsabilidade.** Etapa/tarefa assistida, se recomendada: A IA poderia ser usada para gerar uma primeira proposta de testes e documentação a partir do contrato e dos dados permitidos. Ela serviria apenas como apoio nessa elaboração inicial, sem poder aprovar ou aplicar essas propostas diretamente.
O que permanece sob aceite humano / critério e responsável: A decisão final de aceitar, ajustar ou rejeitar a proposta continua com a pessoa responsável pela revisão técnica da manutenção. Antes do aceite, ela deve conferir se o conteúdo realmente está de acordo com R1–R4 e com os resultados esperados para os casos analisados.<br>
Condição de intervenção, tratamento de exceção e reversibilidade/recusa: Deve haver intervenção sempre que a proposta estiver em desacordo com o contrato, adicionar alguma regra que não existe nos materiais ou não houver informação suficiente para conferir se o resultado está correto. Caso apareça uma situação fora do uso permitido, como necessidade de utilizar dados reais ou uma ferramenta ainda não autorizada, o fluxo deve ser interrompido e o caso encaminhado para a responsável por segurança e para a gestora da manutenção avaliarem antes de continuar. Como a saída da IA seria apenas uma proposta, caso ela esteja incorreta ou inadequada ela pode simplesmente ser rejeitada, ajustada ou descartada, e a tarefa pode ser feita manualmente sem causar nenhuma alteração automática no sistema.<br>

**3. Verificação e contraponto.** Evidência E1 do anexo: caso T2 da AV2, utilizando V-02 com solicitante `Oficina`.<br> critério aplicado: pela R3, um chamado do mesmo departamento deve poder ser visualizado independentemente do estado.<br> resultado/status: esperado true, mas o candidato retornaria false, resultado inferido por inspeção do código.<br> interpretação que sustenta a recomendação: o caso mostra que uma proposta pode parecer coerente e ainda adicionar uma condição que não existe no contrato, reforçando a necessidade de conferir as saídas antes de aceitar seu uso.<br>
Limitação ou evidência contrária E2: na própria AV2, T1, T3 e T4 ficaram de acordo com R3, e o candidato analisado era um artefato didático simulado, não uma saída observada de um modelo real. Portanto, essa evidência mostra a necessidade de verificação, mas não permite afirmar com que frequência uma IA produziria esse tipo de erro.<br> efeito na recomendação e condição que a mudaria: A limitação não justifica rejeitar o uso de IA, mas também não permite confiar nas propostas sem conferência. Por isso mantenho a recomendação de 'adoção condicionada'. Eu mudaria essa recomendação caso um piloto mostrasse resultados consistentes o suficiente para justificar outro nível de uso, ou apresentasse falhas e riscos que tornassem a continuidade inviável.<br>

**4. Riscos e mecanismos.**

| Risco e consequência no recorte | Mecanismo | Responsável | Evidência e como conferir o controle | Exceção/interrupção |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |

**5. Maturidade e próximo passo.** Objeto e estágio: ___; definição adotada: ___; fatos que o sustentam: ___; estágio rival e motivo da distinção: ___; lacuna: ___.
Passo proposto — tarefa, participantes, duração, dados e responsável: ___
Métrica (fórmula/unidade e, se taxa, numerador/denominador): ___
Coleta e referência de comparação: ___; limite da medida: ___
Condição proposta de avanço / quem decide: ___
Condição proposta de interrupção / quem age: ___

**6. Fundamentação aplicada.** Integre estes argumentos às seções anteriores ou registre-os aqui com remissão explícita:

- **F1:** afirmação da fonte em minhas palavras e localização: ___; decisão do parecer a que se aplica: ___; o que a fonte sustenta: ___; minha inferência sobre o caso: ___; limite/contraponto: ___.
- **F2:** afirmação da fonte em minhas palavras e localização: ___; decisão do parecer a que se aplica: ___; o que a fonte sustenta: ___; minha inferência sobre o caso: ___; limite/contraponto: ___.

## Anexo — evidências, referências e procedência

**E1 — origem/atividade, arquivo ou identificação e trecho exato:** ___
Entrada ou fato / esperado ou critério / resultado e método / status observado, inferido ou simulado: ___
**E2 — origem e trecho ou limitação/contraponto da evidência:** ___
**Outros trechos essenciais de apoio às decisões, se necessários:** ___

**F1 — referência de L0:** autores: ___; título: ___; ano/versão: ___; seção/página consultada: ___; referência/link identificável: ___.
**F2 — referência de L0:** autores: ___; título: ___; ano/versão: ___; seção/página consultada: ___; referência/link identificável: ___.

**Procedência:** materiais simulados reaproveitados: ___; observações próprias: ___; inferências: ___; passos e metas propostos: ___.
**IA:** não utilizada / ferramenta-modelo visível: ___; data: ___; tarefa/contexto: ___; trecho aproveitado: ___; verificação e intervenção próprias: ___. Use “não informado” para metadados indisponíveis.

**Checklist:** [ ] alternativas; [ ] autonomia; [ ] evidência/contraponto; [ ] dois riscos; [ ] maturidade/métrica; [ ] duas fontes aplicadas; [ ] procedência; [ ] 3+2 páginas.

# Regras de Negócio e Pontuação de Oportunidades

## Objetivo

A aplicação analítica vai além de relatórios descritivos ao aplicar regras de negócio que transformam o comportamento operacional da carteira em sinais de priorização comercial.

O portfólio público documenta a lógica conceitualmente, sem expor pesos, limites ou políticas comerciais confidenciais.

## Conceito de pontuação de oportunidades

A camada de oportunidades combina diversos sinais da carteira para gerar uma pontuação de priorização.

Conceitualmente:

```text
Maturidade do Contrato
      +
Sinal de Recorrência
      +
Tempo desde o Último Contrato
      +
Relacionamento com a Carteira
      ↓
Pontuação da Oportunidade
      ↓
Classificação de Prioridade
      ↓
Potencial Financeiro Estimado
```

## Principais sinais de oportunidade

### Maturidade do contrato

A maturidade mede o estágio de evolução de um relacionamento ou contrato existente e ajuda a identificar contas que podem estar aptas a uma nova abordagem comercial.

A aplicação agrupa a carteira em faixas de maturidade e compara o potencial estimado associado a cada faixa.

### Recorrência

A recorrência histórica é utilizada como outro sinal de propensão comercial.

Clientes ou relacionamentos com operações históricas repetidas podem ser analisados separadamente daqueles que tiveram apenas uma operação.

### Tempo desde o último contrato

O tempo decorrido desde a operação mais recente é utilizado para identificar relacionamentos que permaneceram inativos por um período relevante.

Esse sinal é combinado com maturidade e recorrência, em vez de ser tratado como uma regra isolada.

### Classificação de prioridade

A pontuação combinada é convertida em uma classificação de prioridade acionável.

A aplicação analítica destaca oportunidades de alta prioridade e seu potencial financeiro estimado para que as equipes comerciais concentrem esforços onde o retorno esperado é maior.

## Potencial financeiro estimado

O potencial traduz um sinal de oportunidade em um valor de negócio estimado.

A aplicação analisa:

- potencial estimado total
- potencial de alta prioridade
- potencial por região
- potencial por gestor
- potencial por nível de maturidade
- percentual da carteira com potencial identificado
- ticket médio potencial

## Simulação de captação

A visão Carteira e Oportunidades inclui um mecanismo simples de cenários que permite avaliar quanto potencial poderia ser capturado sob diferentes taxas de conversão assumidas.

Isso transforma uma estimativa estática de oportunidades em uma ferramenta de planejamento de negócio.

## Regras do funil comercial

A visão de funil classifica propostas por status operacional e avalia o desempenho do processamento.

As principais regras incluem:

- propostas recebidas
- propostas aprovadas
- propostas rejeitadas
- desistências
- propostas em andamento
- valor não convertido
- tempo em andamento
- propostas acima do limite definido de SLA

A aplicação separa métricas de funil baseadas em quantidade da exposição financeira baseada em valor.

## Desempenho em relação às metas

A produção é comparada com metas comerciais em níveis organizacionais, como região, unidade e gestor.

O modelo calcula o atingimento e a diferença em relação à meta para que a gestão identifique tanto resultados acima do esperado quanto unidades que precisam de intervenção.

## Regras financeiras

A análise financeira combina volume operacional com medidas econômicas, incluindo:

- receita estimada
- comissão
- participação da comissão sobre a produção
- spread
- CET
- ticket médio
- composição das operações

Essas métricas ajudam a diferenciar operações de alto volume de operações com perfis distintos de retorno ou custo comercial.

## Regras de conciliação

O fluxo de conciliação compara três etapas principais:

```text
Valor Esperado
      ↓
Valor Descontado
      ↓
Valor Transferido
```

As diferenças entre as etapas são classificadas em categorias de exceção operacional, como falha de desconto ou falha de transferência.

A diferença remanescente é utilizada para medir a exposição financeira e apoiar uma fila de ações prioritárias.

## Orientação para ação

Um princípio recorrente em toda a aplicação é avançar dos indicadores resumidos para uma lista prática de ações.

Exemplos:

- unidades com maior diferença em relação à meta
- gestores com alto valor retido no funil
- oportunidades comerciais de alta prioridade
- radar de desempenho dos gestores
- fila de exceções de conciliação

O objetivo não é apenas descrever o que aconteceu, mas indicar **onde é necessário agir em seguida**.

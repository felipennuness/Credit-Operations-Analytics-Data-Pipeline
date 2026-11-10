# Modelo de Dados

## Visão geral

A aplicação Qlik utiliza um modelo analítico associativo construído a partir de vários conjuntos de dados preparados, cobrindo os domínios operacional, comercial, financeiro, de oportunidades, desempenho e conciliação.

O modelo foi desenvolvido para permitir que os usuários avancem de indicadores executivos até registros operacionais detalhados, sem separar cada assunto de negócio em aplicações isoladas.

## Principais conjuntos de dados analíticos

A aplicação contém conjuntos de dados preparados equivalentes às seguintes áreas:

### Fatos operacionais centrais

- `FATO_CONTRATOS`
- `FATO_PROPOSTAS`

Esses fatos fornecem a base para análises de produção, funil de propostas, finanças e operações.

### Estruturas de clientes e relacionamentos

- `DIM_CLIENTE`
- `INT_VINCULO`

Essas estruturas conectam clientes e relacionamentos da carteira às operações históricas e à lógica de oportunidades.

### Metas e estrutura organizacional

- `METAS`
- `METAS_GERENTES`
- `REGIONAIS`

Esses conjuntos de dados permitem comparar a produção realizada com os objetivos comerciais por região, unidade e gestor.

### Camada de oportunidades

- `INT_OPORTUNIDADE`

Essa camada consolida os sinais de negócio utilizados para identificar e priorizar oportunidades comerciais.

### Camada de desempenho

- `DIM_GERENTE_PERFORMANCE`
- `FATO_PERFORMANCE_MENSAL`
- `FATO_PERFORMANCE_OPORTUNIDADE`
- `FATO_PERFORMANCE_META`

Esses conjuntos de dados apoiam análises no nível de gestor, combinando resultados realizados, eficiência do funil, metas e potencial de oportunidades.

### Camada de conciliação

Um conjunto de dados dedicado à conciliação permite comparar valores financeiros esperados, descontados e transferidos, além de analisar exceções e inadimplência.

## Modelo conceitual

```text
                 DIM_CLIENTE
                      |
                      |
               INT_VINCULO
                /    |    \
               /     |     \
              v      v      v
     FATO_CONTRATOS  FATO_PROPOSTAS  INT_OPORTUNIDADE
             |             |               |
             |             |               |
             +-------------+---------------+
                           |
                           v
                Estruturas de Desempenho
                           |
                   +-------+-------+
                   |               |
                   v               v
                METAS          REGIONAIS

Os dados de conciliação são integrados como um domínio analítico operacional/financeiro complementar.
```

## Domínios analíticos

### Contratos

A tabela fato de contratos inclui campos relacionados a:

- valores de produção
- renda do cliente
- parcelas
- taxas financeiras
- spread
- CET
- valor da operação
- valores bruto e líquido
- seguro
- IOF
- comissão
- empregador
- convênio
- parceiro comercial
- gestor e região

### Propostas

A tabela fato de propostas apoia análises de funil e SLA por meio de campos relacionados a:

- status da proposta
- datas e horários da proposta
- tempo de processamento
- SLA
- tipo de operação
- valor da proposta
- receita
- comissão
- gestor / região

### Oportunidades

A estrutura de oportunidades inclui campos analíticos como:

- maturidade
- indicador de recorrência
- pontos de maturidade
- pontos de recorrência
- pontos relacionados ao tempo
- pontuação da oportunidade
- prioridade
- potencial financeiro estimado
- indicador de alta prioridade

### Desempenho

A camada de desempenho combina métricas como:

- contratos produzidos
- produção líquida
- receita
- comissão
- ticket médio
- propostas recebidas
- propostas aprovadas / rejeitadas
- propostas em andamento
- valor não convertido
- oportunidades qualificadas
- oportunidades de alta prioridade
- potencial estimado
- metas dos gestores

### Conciliação

O domínio de conciliação permite analisar:

- valor esperado
- valor descontado
- valor transferido
- taxa de conciliação
- falha de desconto
- falha de transferência
- exposição financeira
- causa da exceção
- envelhecimento
- contratos em atraso

## Por que o modelo associativo importa

O modelo associativo do Qlik permite que o usuário selecione um gestor, estrutura regional, tipo de operação, convênio, parceiro comercial ou período e visualize o impacto em várias visões de negócio.

Isso permite conectar:

```text
Produção
   ↕
Funil de Propostas
   ↕
Potencial da Carteira
   ↕
Retorno Financeiro
   ↕
Desempenho do Gestor
   ↕
Risco de Conciliação
```

em uma única aplicação analítica.

## Campos com proteção de privacidade

O modelo analítico inclui identificadores mascarados para informações sensíveis de clientes. Exemplos públicos utilizam somente valores mascarados ou sintéticos.

# ETL e Engenharia de Dados

## Objetivo

A camada de ETL prepara os dados operacionais de crédito para armazenamento relacional e consumo analítico.

A origem original continha muitas colunas com tipos de dados mistos, estruturas repetidas, campos numéricos que aceitavam valores nulos, datas, valores financeiros, taxas, comissões e identificadores de negócio.

## Tecnologias utilizadas

- Python
- Pandas
- SQLAlchemy
- PyMySQL
- MySQL
- Excel / planilhas

## Principais etapas do ETL

```text
Ler arquivo de origem
      ↓
Validar colunas esperadas
      ↓
Limpar textos vazios / valores nulos
      ↓
Converter datas e campos numéricos
      ↓
Corrigir tipos das chaves de negócio
      ↓
Aplicar transformações de negócio
      ↓
Normalizar estruturas repetidas
      ↓
Validar conjuntos de dados transformados
      ↓
Carregar no MySQL
      ↓
Validar após a carga
```

## Preservação de chaves de negócio

Um problema importante de qualidade de dados envolveu o identificador do contrato.

Exemplos do formato original incluíam valores semelhantes a:

```text
20-77774/16006
21-00037/16003
```

Como o identificador contém hífens e barras, ele deve ser modelado como um **campo de texto**, e não como um `BIGINT` numérico.

Tratar o contrato como texto preserva a chave de negócio original e evita conversões inválidas ou perda de identificadores.

## Tratamento de inteiros que aceitam valores nulos

Alguns campos operacionais continham uma mistura de números e textos vazios.

Para campos como a quantidade de parcelas liquidadas, o processo de transformação:

1. substituiu valores vazios por nulos;
2. converteu os valores válidos para numérico;
3. utilizou uma representação de inteiro que aceita valores nulos;
4. converteu valores ausentes para nulos compatíveis com o banco antes da carga.

Isso evitou inserções inválidas e preservou a diferença semântica entre zero e informação ausente.

## Normalização das liberações

A planilha continha colunas repetidas de liberação, como:

```text
liberacao_1 / valor_1
liberacao_2 / valor_2
liberacao_3 / valor_3
...
```

Em vez de manter essa estrutura ampla, o ETL transforma as liberações em uma estrutura relacional de fatos com campos equivalentes a:

```text
contract
release_number
release_type
release_value
```

Conceitualmente:

```text
Planilha em formato amplo

contract | release_1 | value_1 | release_2 | value_2
----------------------------------------------------
A        | Type X    | 1000    | Type Y    | 500

                ↓

Fato de Liberações Normalizado

contract | release_number | release_type | release_value
---------------------------------------------------------
A        | 1              | Type X       | 1000
A        | 2              | Type Y       | 500
```

Isso melhora a escalabilidade, as consultas e a modelagem analítica.

## Validação numérica

Os valores financeiros das liberações exigiram conversão numérica explícita, pois os arquivos de origem podiam conter textos vazios misturados a números válidos.

O ETL remove valores vazios inválidos e converte os valores válidos antes da inserção no banco.

## Tratamento de nulos

Uma etapa reutilizável de conversão de nulos prepara os DataFrames do Pandas para inserção relacional, substituindo valores `NaN` / `NaT` por `None` do Python quando apropriado.

Isso evita que representações de valores ausentes específicas de planilhas sejam gravadas incorretamente no banco.

## Carga no banco de dados

A carga relacional utiliza SQLAlchemy com PyMySQL e inserções em lotes.

O processamento em lotes permite carregar grandes conjuntos de dados em partes gerenciáveis e facilita a investigação quando uma transformação específica ou restrição do banco apresenta falha.

## Validação e resolução de problemas

A implementação incluiu verificações diagnósticas explícitas para:

- identificadores de contrato ausentes
- tipos de dados inesperados
- textos vazios em colunas numéricas
- conversões de data inválidas
- incompatibilidade de schema relacional
- falhas de inserção no banco
- contagem de linhas após transformação

O ETL foi ajustado iterativamente até que as principais verificações retornassem resultados consistentes antes da carga relacional final.

## Escopo público do portfólio

O conjunto de dados real de produção não é publicado.

Qualquer código de exemplo ou conjunto de dados de demonstração adicionado futuramente a este repositório utilizará valores sintéticos ou anonimizados, preservando os mesmos padrões de transformação.

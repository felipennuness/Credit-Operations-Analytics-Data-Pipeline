# Escopo Validado do Projeto

Este arquivo é a fonte de referência para a documentação pública deste estudo de caso de portfólio.

## Escopo confirmado de engenharia de dados

- Os dados de origem vieram de arquivos operacionais estruturados / planilhas.
- Python e Pandas foram utilizados no ETL e na preparação dos dados.
- SQLAlchemy e PyMySQL foram utilizados na carga para o banco de dados relacional.
- MySQL foi utilizado como banco de dados relacional.
- O trabalho de qualidade de dados incluiu tratamento de valores nulos, conversão numérica, preparação de datas, preservação de chaves de negócio e normalização.
- Identificadores de contratos devem ser tratados como texto, pois o formato real da chave de negócio contém caracteres não numéricos.
- Colunas repetidas de liberação / valor foram transformadas em uma estrutura relacional normalizada.

## Escopo analítico Qlik confirmado

A aplicação Qlik inclui seis grandes visões analíticas:

1. Visão Executiva
2. Funil Comercial
3. Carteira e Oportunidades
4. Resultados Financeiros
5. Desempenho Comercial
6. Conciliação e Inadimplência

## Domínios analíticos confirmados

- Contratos
- Propostas
- Clientes / relacionamentos de carteira
- Metas comerciais
- Estruturas regionais
- Pontuação / priorização de oportunidades
- Desempenho de gestores
- Análise financeira
- Conciliação / inadimplência

## Lógica de oportunidades confirmada

A aplicação inclui campos e regras analíticas relacionados a:

- maturidade do contrato
- recorrência
- tempo desde o último contrato
- pontuação da oportunidade
- prioridade
- potencial financeiro estimado
- oportunidades de alta prioridade

Os pesos exatos e proprietários da pontuação não devem ser publicados.

## Estruturas de preparação Qlik confirmadas

A aplicação utiliza conjuntos de dados QVD preparados, cobrindo assuntos como:

- fatos de contratos
- fatos de propostas
- dimensão de clientes
- vínculo / relacionamento de carteira
- metas
- metas de gestores
- estruturas regionais
- oportunidades
- desempenho de gestores
- desempenho mensal
- desempenho de oportunidades
- desempenho de metas
- dados de conciliação

## Restrições da documentação pública

Não publicar:

- CPF
- nomes de clientes
- identificadores reais de contratos associados a clientes
- conjuntos de dados confidenciais
- credenciais de produção
- identificadores internos de infraestrutura
- pesos proprietários de pontuação

## Regra de documentação

Somente detalhes de implementação verificados no ETL real, na aplicação Qlik, na estrutura QVF ou em evidências fornecidas pelo usuário devem ser apresentados como trabalho concluído.

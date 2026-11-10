# Privacidade e Anonimização

## Por que isso importa

Este projeto é baseado em uma implementação real de operações de crédito e, portanto, envolve categorias de dados que não devem ser expostas em um portfólio público.

A versão no GitHub foi desenvolvida para demonstrar arquitetura, raciocínio analítico, decisões de engenharia de dados, modelagem Qlik e design de dashboards sem publicar informações confidenciais de produção.

## Informações excluídas do repositório público

O estudo de caso público não deve expor:

- CPF ou identificadores pessoais equivalentes
- nomes de clientes
- números reais de contratos associados a clientes
- datas ou valores que possam identificar um cliente quando combinados
- informações pessoais de funcionários quando desnecessárias
- credenciais de produção
- senhas ou tokens
- strings de conexão com bancos de dados
- nomes de servidores / endereços IP
- infraestrutura proprietária da empresa
- URLs internas
- conjuntos de dados confidenciais de origem
- documentação específica do cliente
- pesos proprietários de pontuação

## Tratamento das capturas de tela

Antes de publicar uma captura de tela, os seguintes itens devem ser revisados e substituídos ou ocultados quando estiverem presentes:

- identificadores de clientes
- identificadores de contratos associados a pessoas
- informações pessoais sem mascaramento
- nomes de usuário ou e-mails internos reais
- identificadores confidenciais de organizações / clientes
- detalhes de infraestrutura ou conexão

Nomes utilizados apenas para demonstrar o layout dos dashboards também podem ser generalizados para rótulos neutros quando a identidade real não agregar valor técnico.

## Campos analíticos mascarados

O modelo analítico Qlik já inclui campos mascarados de cliente / CPF em partes da aplicação.

Mesmo quando um valor está mascarado na camada analítica, as capturas de tela são revisadas novamente antes da publicação pública.

## Exemplos sintéticos

Qualquer conjunto de dados de exemplo ou código adicionado a este repositório deve utilizar valores sintéticos, mantendo os mesmos:

- tipos de dados
- relacionamentos entre tabelas
- padrões de transformação
- estrutura de regras de negócio
- comportamento analítico

## Princípio do portfólio

O repositório público deve ser detalhado o suficiente para demonstrar a implementação técnica, mas sem permitir a reconstrução de dados confidenciais de clientes ou da empresa.

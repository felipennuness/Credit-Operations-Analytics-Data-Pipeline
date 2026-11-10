# Dashboards e Visões de Negócio

## Visão geral

A aplicação Qlik está organizada em seis visões analíticas que conduzem do acompanhamento executivo à ação operacional.

O portfólio público utiliza capturas de tela tratadas para demonstrar o design e a estrutura analítica sem expor informações pessoais ou comerciais confidenciais.

## 1. Visão Executiva

A página executiva oferece uma visão consolidada da operação.

### Principais KPIs

- Produção Líquida
- Contratos Produzidos
- Clientes Atendidos
- Receita Estimada
- Comissão Total
- Recorrência da Carteira

### Principais análises

- evolução mensal da produção
- composição por tipo de operação
- atingimento de metas por região
- unidades com maiores diferenças em relação às metas
- perfil de recorrência da carteira
- tabela detalhada de desempenho das unidades

### Objetivo de negócio

Oferecer à gestão uma visão rápida de escala, resultado financeiro, alcance de clientes, desempenho em relação às metas e recorrência da carteira.

---

## 2. Funil Comercial

A página do funil comercial analisa as propostas desde a entrada até a decisão.

### Principais KPIs

- Propostas Recebidas
- Volume de Propostas
- Taxa de Decisão
- Taxa de Aprovação
- Valor Não Convertido
- Valor em Andamento Acima do SLA

### Principais análises

- distribuição dos resultados das propostas
- valor financeiro por faixa de SLA
- percentual do valor em andamento com atraso por região
- valor não convertido por tipo de operação
- concentração do valor atrasado no funil
- tabela de prioridades de ação por gestor

### Objetivo de negócio

Identificar gargalos do processo e quantificar o valor financeiro retido no pipeline de propostas.

---

## 3. Carteira e Oportunidades

Esta página transforma o comportamento histórico da carteira em um pipeline de oportunidades.

### Principais KPIs

- Oportunidades Qualificadas
- Potencial Financeiro Estimado
- Oportunidades de Alta Prioridade
- Potencial de Alta Prioridade
- Carteira com Potencial
- Ticket Médio Potencial

### Principais análises

- potencial comercial por região
- simulação de taxa de captação
- sinais de oportunidade
- potencial por maturidade do contrato
- concentração de potencial por região / gestor
- radar de oportunidades com prioridade, potencial, maturidade, último contrato e contexto de recorrência

### Objetivo de negócio

Apoiar ações comerciais proativas com base no comportamento da carteira, em vez de aguardar apenas novas propostas recebidas.

---

## 4. Resultados Financeiros

A página financeira avalia a economia das operações originadas.

### Principais KPIs

- Produção Líquida
- Receita Estimada
- Comissão Total
- Comissão / Produção
- Spread Médio
- CET Médio

### Principais análises

- receita estimada versus comissão por tipo de operação
- spread versus CET por tipo de operação
- participação da comissão por região
- participação da comissão por parceiro comercial
- evolução da receita estimada e da comissão
- comparação financeira detalhada por tipo de operação

### Objetivo de negócio

Entender não apenas o volume de produção, mas também receita, custo comercial, características de precificação e composição das operações.

---

## 5. Desempenho Comercial

A página de desempenho combina resultado realizado, eficiência do funil e potencial futuro da carteira no nível de gestor.

### Principais KPIs

- Produção Líquida
- Taxa de Aprovação
- Valor Não Convertido
- Oportunidades Qualificadas
- Potencial Financeiro Estimado
- Carteira com Potencial

### Principais análises

- produção realizada versus potencial de oportunidades por gestor
- eficiência do funil por gestor
- taxa de potencial da carteira por gestor
- concentração de potencial de alta prioridade
- eficiência de volume
- tabela de desempenho orientada à ação

### Objetivo de negócio

Evitar avaliar o desempenho comercial apenas pela produção histórica. A página combina o que o gestor produziu, a eficiência com que conduziu o funil e quanto potencial ainda existe na carteira.

---

## 6. Conciliação e Inadimplência

Esta página monitora a conciliação financeira após a originação e a exposição a exceções.

### Principais KPIs

- Valor Esperado
- Taxa de Conciliação
- Exposição Financeira
- Falha de Desconto
- Falha de Transferência
- Contratos com Parcelas em Atraso

### Principais análises

- fluxo esperado → descontado → transferido
- causas de divergência financeira
- evolução da taxa de conciliação
- envelhecimento das exceções em atraso
- desempenho de conciliação por entidade de folha / conciliação
- fila de ações prioritárias

### Objetivo de negócio

Identificar onde o fluxo de caixa esperado divergiu do comportamento real de desconto ou transferência e priorizar os casos que exigem tratamento operacional.

## Filosofia de navegação

A aplicação está estruturada para apoiar um fluxo natural de gestão:

```text
Visão Executiva
        ↓
Funil Comercial
        ↓
Oportunidades da Carteira
        ↓
Resultados Financeiros
        ↓
Desempenho Comercial
        ↓
Conciliação e Inadimplência
```

Isso permite ao usuário avançar de **o que aconteceu** para **por que aconteceu**, **onde existe potencial** e, por fim, **onde é necessário agir**.

## Plano de publicação das capturas de tela

O repositório publica capturas de tela selecionadas e tratadas, em vez de todas as imagens disponíveis.

O objetivo é apresentar um exemplo visual consistente de cada visão de negócio, mantendo o README principal objetivo.

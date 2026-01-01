# Banking Analytics Dashboard – Power BI

Este repositório contém um projeto de **dashboard bancário** desenvolvido no Power BI, usando dados sintéticos gerados em Python para simular um cenário realista do setor financeiro.

## 🎯 Objetivo

- Praticar **modelagem de dados** (star schema) e **DAX** em um contexto mais próximo da realidade bancária.
- Criar um material sólido de **portfólio**, que mostre não só gráficos, mas também raciocínio de negócio.
- Explorar KPIs típicos do setor financeiro: saldo sob gestão, volume transacionado, concentração por cidade/segmento e tendência temporal.

## 🧱 Modelo de Dados

O modelo segue um **esquema em estrela**, com:

**Tabelas de Dimensão:**
- `Dim_Customers` – dados de clientes (cidade, idade, segmento)
- `Dim_Products` – produtos bancários (conta corrente, poupança, cartão de crédito, empréstimos)
- `Dim_Calendario` – calendário para análises temporais (ano, mês, trimestre)

**Tabelas de Fato:**
- `Fact_Accounts` – contas e saldos
- `Fact_Transactions` – transações por conta, data, tipo e canal

Relacionamentos 1:* conectam as dimensões às tabelas de fato.

## 📊 Principais KPIs e Visuais

**Página: Visão Executiva**
- Total de Saldo (AUM – Assets Under Management)
- Valor Total Transacionado
- Total de Transações
- Contas com Movimentação
- Saldo por Cidade
- Saldo por Segmento de Cliente
- Evolução mensal do Valor Transacionado

As principais medidas são escritas em DAX, por exemplo:

- `Total Saldo = SUM(Fact_Accounts[Balance])`
- `Valor Total Transacionado = SUM(Fact_Transactions[Amount])`
- `Total Transações = COUNTROWS(Fact_Transactions)`
- `Clientes Ativos = DISTINCTCOUNT(Fact_Transactions[AccountID])`

E análises de tempo usando `Dim_Calendario`, como:

- `Valor Mês Anterior`

Ele gera quatro ficheiros CSV:

- `Dim_Customers.csv`
- `Dim_Products.csv`
- `Fact_Accounts.csv`
- `Fact_Transactions.csv`

Os dados não representam nenhuma instituição real e são **totalmente fictícios**, servindo apenas para estudo.

## 🚀 Como Reproduzir o Projeto

1. Clone este repositório:
   ```bash
   git clone https://github.com/RaphaelSampaio1/Power-BI-Real-Bank-Case.git

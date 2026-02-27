# 🚀 Projeto Olist Databricks — Arquitetura Lakehouse

Este projeto segue a arquitetura **Lakehouse** utilizando Microsoft Azure e Azure Databricks, estruturado em camadas **Bronze**, **Silver** e **Gold**.

Os dados são:

- Inseridos na camada Bronze
- Transformados e padronizados na Silver
- Agregados na Gold
- Consumidos via Databricks SQL Dashboard

---

# ☁️ Infraestrutura

## 🔹 Ambiente Cloud

- Microsoft Azure  
- Azure Databricks Workspace  
- Cluster configurado com encerramento automático  
- Container para persistência das tabelas Delta  

## 🔹 Motor de Processamento

- Apache Spark (PySpark / SQL)  
- Delta Lake como camada de armazenamento  

---

# 🏗 Arquitetura do Projeto

A arquitetura segue o padrão **Medallion Architecture**, dividida em três camadas:

---

## 🥉 Camada Bronze — Dados Brutos

Responsável pela aquisição dos dados sem transformação significativa.

### Características:

- Dados mantidos no formato original  
- Estrutura próxima à fonte  
- Persistência em Delta  
- Sem aplicação de regras de negócio  

### 🎯 Objetivo Técnico

Garantir rastreabilidade e permitir reprocessamento futuro, sem dependência da fonte original.

---

## 🥈 Camada Silver — Limpeza e Padronização de Dados

Responsável pelo tratamento e organização dos dados.

### Principais Processos:

- Tratamento de valores nulos  
- Padronização de tipos de dados  
- Normalização de colunas  
- Aplicação de regras de qualidade  
- Remoção de inconsistências  

### 🎯 Objetivo Técnico

Disponibilizar dados confiáveis, estruturados e prontos para análise.

---

## 🥇 Camada Gold — Métricas de Negócio

Responsável pela construção das tabelas analíticas e agregações.

### Exemplos de Transformações:

- Agregações por avaliação  
- Agregações por localização  
- Agregações por produtos  

### 🎯 Objetivo Técnico

Disponibilizar tabelas otimizadas para consumo analítico e dashboards.

---

# 📊 Relatórios

Relatório gerado a partir das tabelas finais (Silver e Gold).

![Dashboard](img/Dashboard.png)

---

# 🗺 Diagrama da Arquitetura

![Diagrama da Arquitetura](img/Diagrama.png)

---

# 🧩 Modelagem de Dados

![Modelagem de Dados](img/Modelagem.png)
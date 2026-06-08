# 📦 Análise de Atrasos Logísticos no E-Commerce Brasileiro

**Projeto Final — Disciplina: Computação Para Análise de Dados (CPAD)**  
**Autor:** Jair Barbosa Santana | **Contato:** Jairbse7@gmail.com

---

## 📋 Descrição

Este projeto investiga o impacto dos **atrasos logísticos na satisfação dos consumidores** no e-commerce brasileiro, utilizando dados reais e anonimizados da plataforma **Olist** — a maior loja de departamentos dos marketplaces brasileiros.

A análise explora mais de 100 mil pedidos realizados entre 2016 e 2018, cruzando dados de entrega com as avaliações deixadas pelos clientes (1 a 5 estrelas), a fim de identificar padrões e gargalos logísticos que impactam diretamente a experiência do consumidor.

---

## 🌐 Acesse o Relatório Interativo

> 🔗 **[Clique aqui para visualizar o projeto completo no RPubs](https://rpubs.com/JairBS/1439117)**

---

## 🎯 Problema de Pesquisa

> *Qual é o impacto dos atrasos logísticos na satisfação dos consumidores no e-commerce brasileiro?*

A logística em um país de dimensões continentais como o Brasil representa um desafio imenso. Entregas atrasadas são a principal causa de avaliações negativas, e entender onde e por que esses atrasos ocorrem é fundamental para a sobrevivência e crescimento de plataformas de e-commerce.

---

## 📊 Dataset

| Atributo | Detalhe |
|---|---|
| **Nome** | Brazilian E-Commerce Public Dataset by Olist |
| **Fonte** | [Kaggle — Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) |
| **Período** | Setembro de 2016 a Outubro de 2018 |
| **Volume** | +100.000 pedidos reais e anonimizados |
| **Estrutura** | 9 arquivos CSV relacionais (~52 variáveis no total) |

---

## 🔧 Tecnologias e Pacotes Utilizados

| Pacote | Finalidade |
|---|---|
| `tidyverse` | Importação, manipulação e visualização de dados |
| `lubridate` | Cálculo de diferenças entre datas (atrasos) |
| `DT` | Tabelas interativas e paginadas |
| `plotly` | Gráficos interativos para análise exploratória |

---

## ⚙️ Metodologia

1. **Importação** — Leitura dos arquivos CSV com `read_csv()`
2. **Mesclagem** — Junção das tabelas de pedidos, itens e avaliações via `left_join()` pela chave `order_id`
3. **Conversão** — Transformação das colunas de data de texto para `datetime` com `lubridate`
4. **Filtragem** — Manutenção apenas de pedidos com status `delivered` (entregues)
5. **Feature Engineering** — Criação da variável `dias_de_atraso` (diferença em dias entre entrega real e estimada)

---

## 📌 Variáveis de Interesse

| Variável | Tipo | Descrição |
|---|---|---|
| `order_id` | Caractere | Identificador único do pedido |
| `customer_id` | Caractere | Identificador único do cliente |
| `data_estimada` | Data/Hora | Prazo de entrega prometido na compra |
| `data_entrega` | Data/Hora | Data real de entrega ao cliente |
| `dias_de_atraso` | Numérico | Diferença em dias (positivo = atraso; negativo = adiantado) |
| `review_score` | Numérico | Nota de satisfação do cliente (1 a 5 estrelas) |
| `price` | Numérico | Preço do produto (R$) |
| `freight_value` | Numérico | Valor do frete (R$) |

---

## 💼 Impacto e Público-Alvo

Os insights gerados por esta análise são direcionados a:

- **Gestores de plataformas de e-commerce** — para identificar rotas e estados que demandam novas parcerias de transporte
- **Gerentes de logística** — para ajustar os prazos estimados apresentados ao consumidor final
- **Vendedores parceiros** — para criar ações proativas de retenção (ex: cupons automáticos) em pedidos com risco de atraso

---

## 📁 Estrutura do Projeto

```
📂 projeto-final-cpad/
├── 📄 README.md
├── 📄 projeto_final_cpad.Rmd       # Código-fonte do relatório
└── 📂 data/
    ├── olist_orders_dataset.csv
    ├── olist_order_items_dataset.csv
    └── olist_order_reviews_dataset.csv
```

> ⚠️ Os arquivos de dados não estão incluídos no repositório por questões de tamanho. Faça o download diretamente no [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

---

*Projeto desenvolvido como requisito parcial da disciplina Computação Para Análise de Dados — 2026.*

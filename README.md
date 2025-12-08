# 📊 Análise de Dados com Python e Pandas

### Projeto – Banco Carrefour | Engenharia e Análise de Dados

Bem-vindo ao repositório do meu projeto de análise de dados utilizando **Python**, **Pandas** e práticas modernas de tratamento, exploração e visualização de dados.

Este notebook foi desenvolvido como parte do desafio técnico do **Banco Carrefour**, com foco em aplicar conceitos práticos de engenharia e análise de dados, desde carregamento e limpeza até geração de insights.

---

## 🚀 Objetivos do Projeto

* Realizar **exploração e tratamento** dos dados utilizando Pandas.
* Identificar padrões, outliers e comportamentos relevantes.
* Aplicar boas práticas de codificação, organização e documentação.
* Entregar uma análise clara, estruturada e replicável.

---

## 🛠️ Tecnologias Utilizadas

* **Python 3.x**
* **Pandas**
* **NumPy**
* **Matplotlib / Seaborn**
* **Jupyter Notebook**

---

## 📈 Conteúdo do Notebook

O notebook contém:

1. Importação e inspeção inicial dos dados
2. Limpeza, tratamento e padronização das colunas
3. Análises exploratórias (EDA)
4. Visualizações para identificar tendências e correlações
5. Conclusões e insights principais

# 📘 Relatório Completo de Análise de Dados

### *Adventure Works – Vendas 2008–2009*

### *Análise exploratória, financeira e operacional com Python & Pandas*

---

# 🧩 1. Visão Geral

Este relatório apresenta a análise completa do dataset de vendas da *Adventure Works*, contendo **904 registros** e **16 colunas**, cobrindo o período de **2008 a 2009**.

O objetivo principal é transformar o notebook técnico em um documento gerencial, detalhando:

* desempenho comercial;
* margens e lucratividade;
* comportamento por produto, loja e fabricante;
* indicadores logísticos;
* oportunidades de melhoria operacional.

---

# 🧮 2. Principais KPIs de Negócio

| Indicador                    | Resultado                                                                        |
| ---------------------------- | -------------------------------------------------------------------------------- |
| **Receita Total**            | **R$ 5.984.606,14**                                                              |
| **Custo Total**              | Calculado linha a linha (Custo Unitário × Quantidade)                            |
| **Lucro Total**              | Receita − Custo                                                                  |
| **Margem Geral (%)**         | ~55% a ~65% (valor exato calculado no notebook)                                  |
| **Quantidade Total Vendida** | Somatório das 904 vendas                                                         |
| **Tempo Médio de Envio**     | Aproximadamente 10 a 20 dias (valor exato calculado via Data Envio − Data Venda) |

A margem alta é explicada pelo markup robusto nos produtos (ex.: custo 348 → venda 758).

---

# 📊 3. Estrutura do Dataset

As principais colunas utilizadas na análise foram:

* **Produto**
* **Fabricante**
* **Quantidade**
* **Valor Unitário**
* **Valor Venda**
* **Custo Unitário**
* **Valor Desconto**
* **ID Loja**
* **Data Venda / Data Envio**

Essas colunas permitiram criar métricas financeiras e logísticas completas.

---

# 🚀 4. Cálculos Aplicados

## 4.1 Receita

Somatório de todos os valores de venda:

```
receita_total = df['Valor Venda'].sum()
```

## 4.2 Custo Total

Criado a partir da multiplicação:

```
df['custo'] = df['Custo Unitário'] * df['Quantidade']
```

## 4.3 Lucro

```
df['lucro'] = df['Valor Venda'] - df['custo']
```

## 4.4 Margem (%)

```
df['margem'] = (df['lucro'] / df['Valor Venda']) * 100
```

## 4.5 Tempo de Envio

```
df['tempo_envio'] = (df['Data Envio'] - df['Data Venda']).dt.days
```

---

# 🏆 5. Análises por Dimensão

## 5.1 Produtos com maior receita

Os produtos premium foram os grandes responsáveis pelo faturamento:

1. **Adventure Works Laptop 15.4W M1548 Red**
2. **Fabrikam Trendsetter X200 White**

Ambos aparecem continuamente no dataset e possuem:

* **ticket alto** (R$ 4.548 e R$ 5.988)
* **quantidade fixa de 6 unidades** por transação
* forte presença ao longo do período

Resultado: **alta concentração de receita em poucos produtos**.

---

## 5.2 Lucro por produto

Os produtos acima também lideram em lucratividade devido ao markup elevado.

A margem média desses itens supera 60%, reforçando o quanto são críticos para o portfólio.

---

## 5.3 Fabricantes com maior resultado

Ranking típico observado:

1. **Adventure Works**
2. **Fabrikam, Inc.**

Esses fabricantes dominam o dataset e representam mais de 80% das vendas.

---

## 5.4 Análise por Loja

As lojas mais relevantes para a operação:

* **ID Loja 199**
* **ID Loja 306**
* **ID Loja 307**

Elas concentram o maior volume de vendas e, consequentemente, de receita.

---

# 🚚 6. Análise Logística – Tempo de Entrega

O tempo de envio foi calculado com:

```
tempo_envio = Data Envio − Data Venda
```

A média (exata no notebook) fica entre **10 e 20 dias**, com alguns exemplos reais:

* Venda: **2008-05-09**
* Envio: **2008-05-29**
* Diferença: **20 dias**

### Insights operacionais:

* Prazo relativamente alto para um cenário de varejo.
* Pode impactar NPS e taxa de recompra.
* Sugere dependência de parceiros logísticos externos ou estoques reduzidos.

---

# 💡 7. Insights Estratégicos

## 🔹 Intensidade de portfólio

A base mostra que a empresa se apoia em **poucos produtos de alto valor**.
Embora isso aumente a margem, também cria **risco de concentração**.

## 🔹 Margens altas sustentam o lucro

Como o markup chega a dobrar o custo, a margem geral é muito saudável.
Isso mostra uma estratégia premium clara.

## 🔹 Dependência de poucos fabricantes

A concentração em dois fabricantes pode afetar:

* segurança de fornecimento
* capacidade de negociação
* riscos de ruptura

## 🔹 Tempo de envio pode melhorar

A cadeia logística parece lenta — revisão de parceiros ou estoques é recomendada.

---

# 🎯 8. Recomendações

### ✔ Diversificar portfólio

Incluir produtos com diferentes faixas de preço reduz a dependência dos modelos premium.

### ✔ Avaliar fornecedores

Negociar SLAs e estratégias de abastecimento.

### ✔ Rever logística

Reduzir o tempo de envio para <10 dias aumentaria satisfação e recorrência de compra.

### ✔ Criar dashboards interativos

Monitorar:

* receita por produto
* desempenho por loja
* atrasos e tempos de envio
* margens por categoria

---

# 📈 9. Próximos Passos

* Automação completa com Python (ELT)
* Criação de pipeline de dados
* Dashboard em Power BI ou Streamlit
* Implementação de API de consulta
* Transformação do notebook em script ETL modular

---

# 🧑‍💼 10. Sobre o Autor

Profissional de Engenharia de Dados e BI, especialista em:

* pipelines e modelagem de dados
* análise exploratória e negócios
* Python, SQL e plataformas de dados
* criação de dashboards e automação inteligente

---

📌 *Este relatório consolida toda a inteligência de negócio extraída diretamente do notebook e do dataset real.*



---

📌 *Fique à vontade para explorar, sugerir melhorias ou abrir issues!*

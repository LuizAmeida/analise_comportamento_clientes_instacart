# Análise de Comportamento de Clientes - Instacart

> Projeto de análise de dados da plataforma de entregas de supermercado Instacart, com foco em entender o comportamento de compra dos clientes, padrões de recorrência, produtos mais populares e hábitos de consumo.

---

## 🎯 Objetivo do Projeto

Realizar uma análise exploratória de dados (EDA) completa sobre os pedidos da plataforma Instacart, com os seguintes objetivos principais:

- **Entender o comportamento de compra dos clientes** (horários, dias da semana, frequência)
- **Identificar os produtos mais populares** e os mais recorrentes
- **Analisar padrões de fidelidade** (produtos e clientes com maior taxa de recompra)
- **Compreender a distribuição de itens por pedido** e hábitos de consumo
- **Identificar produtos "âncora"** (os primeiros itens colocados no carrinho)

---

## 📊 Resultados Obtidos

### Principais Descobertas:

#### 1. Padrões Temporais de Compra
- **Horário de pico:** entre 9h e 17h, com pico máximo às 10h (40.578 pedidos)
- **Dias de maior movimento:** Domingo e Segunda-feira
- **Ciclo de recompra:** Forte tendência semanal, com picos a cada 7, 14, 21 e 28 dias
- **Tempo médio entre pedidos:** aproximadamente 7 dias (padrão semanal)

#### 2. Produtos Mais Populares
| Posição | Produto | Total de Vendas |
|---------|---------|-----------------|
| 1º | Banana | 66.050 |
| 2º | Saco de Bananas Orgânicas | 53.297 |
| 3º | Morangos Orgânicos | 37.039 |
| 4º | Espinafre Bebê Orgânico | 33.971 |
| 5º | Abacate Hass Orgânico | 29.773 |

**Observação:** Os 20 produtos mais vendidos são predominantemente **hortifrúti e orgânicos**.

#### 3. Fidelidade e Recorrência
- **Produtos com maior taxa de recompra:** itens específicos de nicho com taxa de 100% (todos os clientes que compraram voltaram a comprar)
- **Produtos "âncora" (primeiros no carrinho):** Banana é o item mais comum como primeira escolha (15.562 vezes)
- **Clientes fiéis:** 10 clientes com taxa de recompra de 100%

#### 4. Distribuição de Itens por Pedido
- **Média de itens por pedido:** 10,10 itens
- **Máximo de itens em um pedido:** 127 itens
- **Distribuição concentrada:** maioria dos pedidos contém entre 5 e 10 itens

#### 5. Diferenças entre Dias da Semana
- **Quarta-feira vs Sábado:** Padrões similares de distribuição horária
- **Sábado:** Pico mais pronunciado entre 10h e 15h
- **Quarta-feira:** Curva em "U" com leve declínio no meio do dia

---

## 🛠️ Ferramentas Utilizadas

- **Python 3**
- **Bibliotecas:**
  - `pandas` — manipulação e análise de dados
  - `numpy` — operações matemáticas
  - `matplotlib` — visualização de dados (gráficos de barras, histogramas, linhas)

---

## 📚 O que Aprendi

- **Leitura e integração de múltiplas tabelas:** uso de `pd.read_csv()` para carregar 5 tabelas relacionadas (orders, products, order_products, aisles, departments)
- **Análise exploratória de dados (EDA):** identificação de padrões, outliers e tendências
- **Limpeza e pré-processamento:**
  - Remoção de duplicados explícitos e implícitos
  - Tratamento de valores ausentes (substituição por `'Unknown'` ou `999`)
  - Padronização de nomes de colunas (lowercase, remoção de espaços)
  - Correção de tipos de dados (conversão de float para int)
- **Agrupamento e agregação:** uso de `groupby()` para análises por cliente, produto e dia
- **Visualização de dados:** criação de gráficos de barras, histogramas e gráficos de linhas com `matplotlib`
- **Análise de fidelidade:** cálculo de taxas de recompra por produto e por cliente
- **Análise temporal:** identificação de padrões sazonais e ciclos de compra

---

## 🚀 Como Executar o Projeto

```bash
# Clone o repositório
git clone https://github.com/LuizAlmeida/analise_comportamento_clientes_instacart

# Navegue até a pasta do projeto
cd analise_comportamento_clientes_instacart

# Execute o notebook (recomendado: Google Colab ou Jupyter Notebook)
# Ou execute o script Python diretamente
python analise_instacart.py
````

## Requisitos:
- Python 3.x instalado
- Jupyter Notebook (opcional) ou Google Colab (recomendado)
- Bibliotecas: pip install pandas numpy matplotlib

## 🔍 Metodologia
O projeto seguiu uma abordagem estruturada em 3 etapas principais:


## Etapa 1: Visão Geral dos Dados
- Leitura das 5 tabelas do dataset Instacart
- Análise da estrutura, tipos de dados e primeiras linhas
- Identificação de valores ausentes e duplicados

## Etapa 2: Preparação de Dados (Pré-processamento)
- Padronização de cabeçalhos (lowercase, remoção de espaços)
- Remoção de duplicados explícitos (14 pedidos duplicados)
- Correção de duplicados implícitos na coluna genre (agrupando hip, hop, hip-hop → hiphop)
- Substituição de valores ausentes:
> product_name → 'Unknown'
> days_since_prior_order → mantido como NaN (primeiros pedidos)
> add_to_cart_order → 999 (valores acima de 64)
- Conversão de tipos de dados (float → int)

## Etapa 3: Análise de Dados
- Análise Temporal: distribuição de pedidos por hora e dia da semana
- Análise de Produtos: identificação dos produtos mais vendidos e mais recorrentes
- Análise de Fidelidade: cálculo de taxas de recompra por produto e cliente
- Análise de Comportamento: itens por pedido, itens "âncora" (primeiros no carrinho)
- Comparação entre Dias: análise comparativa de quarta-feira vs sábado


## 💡 Melhorias Futuras
- Realizar testes estatísticos para validar as diferenças observadas
- Aplicar modelos de machine learning para previsão de recompra
- Criar dashboards interativos com Power BI ou Tableau
- Segmentar clientes por perfil de consumo (ex: "compradores semanais", "exploradores")
- Analisar correlação entre produtos (quais produtos são comprados juntos)
- Estudar o impacto de promoções e descontos no comportamento de compra
- Implementar análise de cohort para entender retenção ao longo do tempo


## 📁 Estrutura do Projeto
````
📁 analise_comportamento_clientes_instacart/
├── 📁 datasets/                    # Dados utilizados
│   ├── instacart_orders.csv
│   ├── products.csv
│   ├── order_products.csv
│   ├── aisles.csv
│   └── departments.csv
├── 📁 notebooks/                   # Notebook Jupyter com análise completa
│   └── Projeto_Sprint_3.ipynb
├── 📁 scripts/                     # Scripts Python avulsos
├── README.md                       # Este arquivo
└── requirements.txt                # Dependências do projeto
````


## 📌 Contato
- [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/luizmarques84)
- [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/LuizAlmeida)


## ⭐ Este projeto faz parte do meu Bootcamp em Análise de Dados na TripleTen.
````
## 📊 Resumo dos Insights para Investidores
- Métrica	Insight
- Produtos "âncora"	Banana é o item mais comum como primeira escolha (15.562 vezes)
- Produtos mais vendidos	Hortifrúti e orgânicos dominam o top 20
- Ciclo de compra	Padrão semanal forte (picos a cada 7, 14, 21, 28 dias)
- Fidelidade	10 clientes com 100% de taxa de recompra
- Ticket médio	10,10 itens por pedido
- Horário de pico	Entre 9h e 17h (pico às 10h)
- Dias de pico	Domingo e Segunda-feira
**Conclusão Estratégica: A plataforma é movida pela necessidade imediata e recorrência de produtos perecíveis. O valor real está na eficiência em entregar o "básico" (hortifrúti e orgânicos) com constância, garantindo fluxo de caixa semanal e retenção do usuário.**
````

````
## 🎯 RESUMO DO QUE FAZER

| Ação | Status |
|------|--------|
| Criar repositório `analise_comportamento_clientes_instacart` | ⬜ |
| Fazer upload do arquivo `.ipynb` | ⬜ |
| Adicionar README.md com o texto acima | ⬜ |
| Adicionar tópico `tripleten` | ⬜ |
| Fixar (pinned) no perfil | ⬜ |
````

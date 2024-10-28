# Visualização de Dados: Relação entre Variáveis e Formas Gráficas para Análises Univariadas e Bivariadas

A análise de dados é enriquecida quando a natureza das variáveis é considerada, permitindo que as visualizações gráficas certas sejam aplicadas para facilitar a exploração e interpretação dos padrões nos dados. Variáveis podem ser classificadas como **quantitativas** e **qualitativas**, e cada tipo possui abordagens gráficas específicas para análises univariadas e bivariadas.

## 1. Variáveis Quantitativas
Variáveis quantitativas representam medidas numéricas e podem ser contínuas ou discretas, como idade, altura, peso e renda. A seguir, apresentamos as melhores opções gráficas para análises univariadas e bivariadas de variáveis quantitativas:

### Análise Univariada
- **Histograma**: Ideal para observar a distribuição de uma variável quantitativa, mostrando a frequência de intervalos de valores.
- **Boxplot (diagrama de caixa)**: Representa a dispersão, mediana, quartis e possíveis outliers da variável, sendo útil para resumir sua distribuição.
- **Distribuição de Densidade**: Usada para variáveis contínuas, destaca a frequência relativa dos valores da variável.

### Exemplo de Código em Python
```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Gerando dados de exemplo
data = np.random.normal(loc=50, scale=10, size=1000)

# Histograma
plt.figure(figsize=(10, 5))
sns.histplot(data, kde=True, color="skyblue")
plt.title("Histograma com Curva de Densidade")
plt.xlabel("Valores")
plt.ylabel("Frequência")
plt.show()

# Boxplot
plt.figure(figsize=(6, 4))
sns.boxplot(data=data, color="salmon")
plt.title("Boxplot")
plt.xlabel("Valores")
plt.show()
```

### Análise Bivariada
- **Gráfico de Barras Agrupadas**: Compara uma variável qualitativa entre diferentes grupos de outra variável qualitativa, permitindo uma comparação direta.
- **Gráfico de Barras Empilhadas**: Similar ao gráfico de barras agrupadas, mas com as barras empilhadas para representar a soma das frequências de cada categoria.
- **Mapa de Calor de Frequências**: Em tabelas cruzadas, este gráfico utiliza cores para indicar a frequência da combinação entre duas variáveis qualitativas.

## 3. Variáveis Mistas (Quantitativas e Qualitativas)
Ao analisar uma variável quantitativa em relação a uma variável qualitativa, algumas opções de visualização gráfica são particularmente úteis:

- **Boxplot por Categoria**: Compara a distribuição de uma variável quantitativa entre diferentes níveis de uma variável qualitativa.
- **Gráfico de Violino**: Alternativa ao boxplot que mostra a densidade de distribuição para cada categoria.
- **Gráfico de Barras com Médias e Intervalos de Confiança**: Exibe as médias de uma variável quantitativa por categoria, facilitando a comparação entre grupos.

### Exemplo de Código em Python
```python
# Gerando dados de exemplo para análise bivariada
x = np.linspace(0, 10, 100)
y = 3 * x + np.random.normal(0, 1, 100)

# Gráfico de Dispersão
plt.figure(figsize=(8, 6))
plt.scatter(x, y, alpha=0.7, color="purple")
plt.title("Gráfico de Dispersão")
plt.xlabel("Variável X")
plt.ylabel("Variável Y")
plt.show()
```

## 2. Variáveis Qualitativas
Variáveis qualitativas, ou categóricas, agrupam dados em categorias ou grupos, como gênero, cidade, e nível educacional. Para análise univariada e bivariada, seguem as melhores visualizações gráficas para variáveis qualitativas:

### Análise Univariada
- **Gráfico de Barras**: Comum para exibir contagens ou frequências de cada categoria. É ideal para comparar o tamanho relativo dos grupos.
- **Gráfico de Pizza (Pie Chart)**: Mostra a proporção de cada categoria em relação ao total. Funciona melhor com um número reduzido de categorias.
- **Gráfico de Pareto**: Um gráfico de barras que ordena as categorias por frequência, facilitando a identificação das categorias mais influentes.

```python
# Gerando dados categóricos de exemplo
categories = ["A", "B", "C", "D"]
values = [30, 50, 15, 5]

# Gráfico de Barras
plt.figure(figsize=(8, 5))
plt.bar(categories, values, color="lightcoral")
plt.title("Gráfico de Barras")
plt.xlabel("Categoria")
plt.ylabel("Frequência")
plt.show()

# Gráfico de Pizza
plt.figure(figsize=(7, 7))
plt.pie(values, labels=categories, autopct='%1.1f%%', colors=["#ff9999", "#66b3ff", "#99ff99", "#ffcc99"])
plt.title("Gráfico de Pizza")
plt.show()
```

### Análise Bivariada
- **Gráfico de Barras Agrupadas**: Compara uma variável qualitativa entre diferentes grupos de outra variável qualitativa, permitindo uma comparação direta.
- **Gráfico de Barras Empilhadas**: Similar ao gráfico de barras agrupadas, mas com as barras empilhadas para representar a soma das frequências de cada categoria.
- **Mapa de Calor de Frequências**: Em tabelas cruzadas, este gráfico utiliza cores para indicar a frequência da combinação entre duas variáveis qualitativas.

## 3. Variáveis Mistas (Quantitativas e Qualitativas)
Ao analisar uma variável quantitativa em relação a uma variável qualitativa, algumas opções de visualização gráfica são particularmente úteis:

- **Boxplot por Categoria**: Compara a distribuição de uma variável quantitativa entre diferentes níveis de uma variável qualitativa.
- **Gráfico de Violino**: Alternativa ao boxplot que mostra a densidade de distribuição para cada categoria.
- **Gráfico de Barras com Médias e Intervalos de Confiança**: Exibe as médias de uma variável quantitativa por categoria, facilitando a comparação entre grupos.

```python
# Gerando dados mistos de exemplo
import pandas as pd

data_misto = pd.DataFrame({
    'Categoria': np.random.choice(['Grupo 1', 'Grupo 2', 'Grupo 3'], 100),
    'Valores': np.random.normal(50, 10, 100)
})

# Boxplot por Categoria
plt.figure(figsize=(8, 6))
sns.boxplot(x='Categoria', y='Valores', data=data_misto, palette="Set2")
plt.title("Boxplot por Categoria")
plt.xlabel("Categoria")
plt.ylabel("Valores")
plt.show()
```

## Referências:

- http://leg.ufpr.br/~fernandomayer/aulas/ce083/analise-exploratoria.html


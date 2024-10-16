# Redução de Dimensões Usando PCA

Vamos estender o exemplo numérico para um conjunto de dados em 4 dimensões, com o objetivo de reduzir para 2 dimensões usando o **PCA**. Essa redução é útil para visualizar clusters que foram gerados por algoritmos como **K-means**.

## Exemplo Numérico em 4 Dimensões

Suponha que temos um conjunto de dados com 5 amostras em 4 dimensões:

$$
X = \begin{bmatrix}
1 & 2 & 3 & 4 \\
5 & 6 & 7 & 8 \\
9 & 10 & 11 & 12 \\
13 & 14 & 15 & 16 \\
17 & 18 & 19 & 20
\end{bmatrix}
$$

### Passo 1: Centralização dos Dados

Primeiro, precisamos centralizar os dados, subtraindo a média de cada dimensão.

1. **Cálculo da média**:

$$
\text{Média} = \begin{bmatrix}
\text{média}_1 \\
\text{média}_2 \\
\text{média}_3 \\
\text{média}_4
\end{bmatrix} = \begin{bmatrix}
9 \\
10 \\
11 \\
12
\end{bmatrix}
$$

2. **Centralização**:

$$
X_{centralizado} = X - \text{Média} = \begin{bmatrix}
1-9 & 2-10 & 3-11 & 4-12 \\
5-9 & 6-10 & 7-11 & 8-12 \\
9-9 & 10-10 & 11-11 & 12-12 \\
13-9 & 14-10 & 15-11 & 16-12 \\
17-9 & 18-10 & 19-11 & 20-12
\end{bmatrix}
$$

$$
X_{centralizado} = \begin{bmatrix}
-8 & -8 & -8 & -8 \\
-4 & -4 & -4 & -4 \\
0 & 0 & 0 & 0 \\
4 & 4 & 4 & 4 \\
8 & 8 & 8 & 8
\end{bmatrix}
$$

### Passo 2: Cálculo da Matriz de Covariância

A matriz de covariância é dada por:

$$
\text{Cov}(X) = \frac{1}{n-1} (X_{centralizado}^T X_{centralizado})
$$

Após o cálculo, obtemos uma matriz de covariância (os valores aqui são exemplos, o cálculo real pode variar):

$$
\text{Cov}(X) = \begin{bmatrix}
40 & 40 & 40 & 40 \\
40 & 40 & 40 & 40 \\
40 & 40 & 40 & 40 \\
40 & 40 & 40 & 40
\end{bmatrix}
$$

### Passo 3: Cálculo dos Autovalores e Autovetores

Suponha que, após calcular os autovalores e autovetores da matriz de covariância, encontramos:

- **Autovalores**: \( \lambda_1 = 320, \lambda_2 = 0 \)
- **Autovetores**:

$$
v_1 = \begin{bmatrix} 0.5 \\ 0.5 \\ 0.5 \\ 0.5 \end{bmatrix}, \quad v_2 = \begin{bmatrix} -0.7071 \\ -0.7071 \\ -0.7071 \\ -0.7071 \end{bmatrix}
$$

### Passo 4: Seleção dos Principais Componentes

Selecionamos os dois maiores autovalores e seus autovetores correspondentes. Neste caso, temos \( v_1 \) e \( v_2 \).

### Passo 5: Projeção dos Dados

Finalmente, projetamos os dados originais no espaço reduzido usando os autovetores selecionados:

$$
X_{reduzido} = X_{centralizado} \cdot \begin{bmatrix}
v_1 & v_2
\end{bmatrix}
$$

Vamos calcular a projeção:

$$
X_{reduzido} = \begin{bmatrix}
-8 & -8 & -8 & -8 \\
-4 & -4 & -4 & -4 \\
0 & 0 & 0 & 0 \\
4 & 4 & 4 & 4 \\
8 & 8 & 8 & 8
\end{bmatrix} \cdot \begin{bmatrix}
0.5 & -0.7071 \\
0.5 & -0.7071 \\
0.5 & -0.7071 \\
0.5 & -0.7071
\end{bmatrix}
$$

O resultado da projeção será um conjunto de dados em 2 dimensões:

$$
X_{reduzido} = \begin{bmatrix}
-32.0 & 0.0 \\
-16.0 & 0.0 \\
0.0 & 0.0 \\
16.0 & 0.0 \\
32.0 & 0.0
\end{bmatrix}
$$

### Resultados Finais

Os dados em 2 dimensões são:

| Amostra | Dimensão 1 | Dimensão 2 |
|---------|------------|------------|
| 1       | -32.0     | 0.0        |
| 2       | -16.0     | 0.0        |
| 3       | 0.0       | 0.0        |
| 4       | 16.0      | 0.0        |
| 5       | 32.0      | 0.0        |

## Conclusão

Esse processo de PCA reduz a dimensionalidade dos dados de 4 para 2 dimensões, facilitando a visualização de clusters gerados por algoritmos como K-means. A visualização é crucial para entender como os dados estão agrupados e se os clusters são significativos.

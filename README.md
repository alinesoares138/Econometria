# Econometria
## Tópicos do projeto:
1. Regressão Linear
2. Teste RESET 
3. Variáveis Instrumentais / 2SLS

# Regressão Linear

A regressão linear é um método estatístico fundamental para modelar relações entre uma variável dependente 𝑌 e uma ou mais variáveis independentes 𝑋. O modelo assume a forma geral:
   
\[Y = β0 + β1 X + ε\]

O coeficiente β0 representa o valor esperado de Y quando X = 0, enquanto β1 mede a variação média em Y associada a um aumento unitário em X. O termo de erro ε agrega fatores não observados.

O método dos Mínimos Quadrados Ordinários (MQO) estima β0 e β1 minimizando a soma dos quadrados dos resíduos. O coeficiente de determinação (R²) expressa a proporção da variação de Y explicada pelo modelo.
Hipóteses de Gauss-Markov

Para que MQO produza estimadores não tendenciosos e MELNT, devem ser atendidas:

Linearidade nos parâmetros
- Exogeneidade (Cov(X, u) = 0)
- Média condicional zero (E(u|X) = 0)
- Homocedasticidade (Var(u|X) = σ²)
- Ausência de autocorrelação (Cov(uₜ, uₛ | X) = 0)

**Exemplo**

Suponha que estamos modelando a relação entre a temperatura (X, em °C) e a demanda por sorvete (Y, em unidades vendidas). Se o modelo resultar em: \[Y = 50 + 10X + ε\]
Isso significa que:
- Quando a temperatura é 0°C, espera-se vender 50 sorvetes (𝛽0 = 5). 
- Para cada aumento de 1°C, a venda de sorvetes aumenta em 10 unidades (𝛽1 = 10).
- Se não houvesse o intercepto, a equação sempre passaria pela origem (X = 0, Y = 0), o que nem sempre faz sentido. Imagine um caso onde a temperatura é 0°C, mas ainda há vendas de sorvete. O intercepto captura essa realidade.

# Teste RESET

O teste RESET (Ramsey) avalia se o modelo está corretamente especificado. Ele adiciona potências da variável ajustada, como: Ŷ², Ŷ³

Se esses termos forem significativos, há indícios de:
- variáveis omitidas;
- forma funcional incorreta;
- não linearidades ignoradas.

Um resultado significativo sugere revisar a especificação, reavaliar transformações ou adicionar variáveis relevantes.

# Variáveis Instrumentais / 2SLS

Quando um regressor é endógeno — isto é, correlacionado com o termo de erro — os estimadores de MQO tornam-se viesados e inconsistentes. Variáveis Instrumentais (IV) corrigem esse problema.

Um instrumento válido deve satisfazer:

- Relevância: correlacionado com a variável endógena.
- Exogeneidade: não correlacionado com o erro da equação estrutural.

# Método 2SLS (Two-Stage Least Squares)

Primeiro estágio: regredir a variável endógena X no instrumento Z e variáveis exógenas, obtendo X̂.
Segundo estágio: substituir X por X̂ na equação estrutural e estimar por MQO.

Esse método é fundamental quando há simultaneidade, causalidade reversa ou erro de medição, permitindo recuperar relações causais mesmo em cenários onde MQO falha.

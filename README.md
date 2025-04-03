# Econometria
## Tópicos do projeto:
1. Regressão Linear
2. Regressão Múltipla
3. Testes de Hipóteses

# Regressão Linear

1. **O que é?**
   
A **regressão linear** é um método estatístico para modelar a relação entre uma variável dependente \( Y \) e uma ou mais variáveis independentes \( X \). 
Ela busca ajustar uma equação da forma:  

\[
Y = β0 + β1 X + ε
\]

Onde β0 é o ponto onde a linha da regressão cruza o eixo Y (intercepto), β1 diz o quanto Y muda para cada unidade a mais em X (coeficiente angular), e ε representa a diferença entre os valores previstos e os valores reais (erro). O objetivo é encontrar os valores de β0 e β1 que fazem a linha se ajustar da melhor forma possível aos dados.

O **coeficiente de determinação**, conhecido como R², mede a proporção da variação da variável dependente (Y) que é explicada pelo modelo de regressão. Ou seja, o quanto o modelo de regressão consegue explicar os valores de Y. Ele varia entre 0 e 1, onde:
- Se R² = 1 → O modelo explica 100% dos dados, ou seja, os pontos caem exatamente na reta.
- Se R² = 0 → O modelo não consegue explicar nada, ou seja, a reta não faz sentido para os dados.

\[
R² = 1 - (erro do modelo / variação total dos dados)​
\]

(Ver 1_arquivo)

2. **Exemplo**

Suponha que estamos modelando a relação entre a temperatura (X, em °C) e a demanda por sorvete (Y, em unidades vendidas).
Se o modelo resultar em:

\[
Y = 50 + 10X + ε
\]

Isso significa que:

- Quando a temperatura é 0°C, espera-se vender 50 sorvetes (𝛽0 = 5). 
- Para cada aumento de 1°C, a venda de sorvetes aumenta em 10 unidades (𝛽1 = 10).
- Se não houvesse o intercepto, a equação sempre passaria pela origem (X = 0, Y = 0), o que nem sempre faz sentido. Imagine um caso onde a temperatura é 0°C, mas ainda há vendas de sorvete. O intercepto captura essa realidade.

3. **Critérios para um bom estimador de 𝛽**

Estas são as 5 hipóteses de Gauss-Markov, onde o modelo é **não tendencioso** se seguir as três primeiras hipóteses, e considerado **eficiente e MELNT** (o melhor estimador linear não tendencioso), se seguir as cinco hipóteses.
* Linearidade nos parâmetros
* Exogeneidade do regressor - Cov(X,u) = 0
* Média condicional zero - E(u,X) = 0
* Homocedasticidade - V(u,X) = s^2
* Correlação entra valores de u é zero - Cov(u,u|X,X) = 0

# Econometria

A **regressão linear** é um método estatístico para modelar a relação entre uma variável dependente \( Y \) e uma ou mais variáveis independentes \( X \). 
Ela busca ajustar uma equação da forma:  

\[
Y = β0 + β1 X + ε
\]

Onde β0 é o ponto onde a linha da regressão cruza o eixo Y (intercepto), β1 diz o quanto Y muda para cada unidade a mais em X (coeficiente angular), e ε representa a diferença entre os valores previstos e os valores reais (erro). O objetivo é encontrar os valores de β0 e β1 que fazem a linha se ajustar da melhor forma possível aos dados.

## Aline, o que tudo isso significa?

Suponha que estamos modelando a relação entre a temperatura (X, em °C) e a demanda por sorvete (Y, em unidades vendidas).
Se o modelo resultar em:

\[
Y = 50 + 10X + ε
\]

Isso significa que:

- Quando a temperatura é 0°C, espera-se vender 50 sorvetes (𝛽0 = 5). 
- Para cada aumento de 1°C, a venda de sorvetes aumenta em 10 unidades (𝛽1 = 10).
- Se não houvesse o intercepto, a equação sempre passaria pela origem (X = 0, Y = 0), o que nem sempre faz sentido. Imagine um caso onde a temperatura é 0°C, mas ainda há vendas de sorvete. O intercepto captura essa realidade.

```
df <- data.frame(
y <- c(360, 440, 550, 630, 700),
x <- c(100,200,300,400,500)
)
modelo <- lm(y ~ x, data = df)
summary(modelo)

--Resultado:

Call:
lm(formula = y ~ x, data = df)

Residuals:
  1   2   3   4   5 
 -2  -9  14   7 -10 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept) 275.00000   12.55654   21.90 0.000208 ***
x             0.87000    0.03786   22.98 0.000181 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 11.97 on 3 degrees of freedom
Multiple R-squared:  0.9944,	Adjusted R-squared:  0.9925 
F-statistic: 528.1 on 1 and 3 DF,  p-value: 0.0001805

coef(modelo)
(Intercept)           x 
     275.00        0.87

> b0
[1] 275
> b1
[1] 0.87

```

O coeficiente de determinação, conhecido como R², mede a proporção da variação da variável dependente (Y) que é explicada pelo modelo de regressão. Ou seja, o quanto o modelo de regressão consegue explicar os valores de Y. Ele varia entre 0 e 1, onde:
- Se R² = 1 → O modelo explica 100% dos dados, ou seja, os pontos caem exatamente na reta.
- Se R² = 0 → O modelo não consegue explicar nada, ou seja, a reta não faz sentido para os dados.

\[
R² = 1 - (erro do modelo / variação total dos dados)​
\]

```
summary(modelo)$r.squared

-- Resultado:
[1] 0.994351

Ou, manualmente:
y_pred <- predict(modelo)
SQT <- sum((df$y - mean(df$y))^2)  # Variação total de Y
SQR <- sum((df$y - y_pred)^2)  # Erro do modelo

R2 <- 1 - (SQR / SQT)  
R2

-- Resultado:
[1] 0.994351

```

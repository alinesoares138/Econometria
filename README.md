# Econometria

A regressão linear é um método estatístico para modelar a relação entre uma variável dependente \( Y \) e uma ou mais variáveis independentes \( X \). 
Ela busca ajustar uma equação da forma:  

\[
Y = β0 + β1 X + ε
\]

Onde β0 é o ponto onde a linha da regressão cruza o eixo Y (intercepto), β1 diz o quanto Y muda para cada unidade a mais em X (coeficiente angular), e ε representa a diferença entre os valores previstos e os valores reais (erro). O objetivo é encontrar os valores de β0 e β1 que fazem a linha se ajustar da melhor forma possível aos dados.

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

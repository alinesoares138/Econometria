df <- data.frame(
  y <- c(360, 440, 550, 630, 700),
  x <- c(100,200,300,400,500)
)
modelo <- lm(y ~ x, data = df)
summary(modelo)


summary(modelo)$r.squared
#Ou, manualmente:
  y_pred <- predict(modelo)
SQT <- sum((df$y - mean(df$y))^2)  # Variação total de Y
SQR <- sum((df$y - y_pred)^2)  # Erro do modelo

R2 <- 1 - (SQR / SQT)  
R2

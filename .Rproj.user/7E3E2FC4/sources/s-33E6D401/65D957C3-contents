library(tidyverse)
library(ggfortify)

mod1 <- lm(mpg ~ wt, data = mtcars)
summary(mod1)

#regression model is linear
mtcars %>%
ggplot(., aes(x = wt, y = mpg))+
  geom_point()+
  geom_smooth(method = lm, formula = y ~ poly(x,2))

#the mean of the reasiduals is zero
#check model summary
summary(mod1)
#calc mean of residuals
mean(mod1$residuals)

#homoskedasticity of residuals or equal variance
#look for a blob shape
#1 and 3 are the plot options out of 6 potential plots 
autoplot(mod1, which = c(1,3))

#no autocorrelation of residuals
#looks at correlation between adjacent observations 
acf(mod1$residuals)

#formal test Durbin-Watson test 
#how to call function from library 
lmtest::dwtest(mod1)

#normality of residuals with QQplot
autoplot(mod1, which = 2)

#gives you all plots 1 - 4
autoplot(mod1)


#dealing with data outside of R
#practice with saving and loading
#. = route directory
#getwd = get working directory
#need to do my_data, you need to tell it what it needs to be called
my_df <- mtcars
write.csv(x = my_df,"./data/my_data.csv")

library(tidyverse)
library(ggfortify)

my_cars_data <- read_csv("./data/my_data.csv")
#head = just show first 6 rows. Use this for assignments 
glimpse(my_cars_data)
summary(my_cars_data)
head(my_cars_data)

mod1 <- 
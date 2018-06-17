#import the dataset
dataset = read.csv('Position_Salaries.csv')
dataset = dataset[2:3]

#fitting decision tree regressor into dataset
library(rpart)
regressor = rpart(formula = Salary ~ . , data = dataset, control = rpart.control(minsplit = 1))

#visualising the decision tree regression results
library(ggplot2)
x_grid = seq(min(dataset$Level), max(dataset$Level), 0.01)
ggplot() +
  geom_point(aes(x = dataset$Level, y = dataset$Salary), color = 'red')+
  geom_line(aes(x = x_grid, y = predict(regressor,
                                        newdata = data.frame(Level = x_grid))),
            colour = 'blue') +
  ggtitle('True or Bluff(Decision Tree regression)')+
  xlab('Level')+
  ylab('Salary')

#predicting a new result using decision tree regression
y_pred = predict(regressor, newdata =  data.frame(Level = 6.5))

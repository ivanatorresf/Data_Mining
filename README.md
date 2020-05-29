# Mineria_de_Datos
Class Session
![Mineriade Datos](https://cdn.windowsreport.com/wp-content/uploads/2018/07/data-mining.png)


# Big-Data  

### <p align="center" > TECNOLÓGICO NACIONAL DE MÉXICO INSTITUTO TECNOLÓGICO DE TIJUANA SUBDIRECCIÓN ACADÉMICA DEPARTAMENTO DE SISTEMAS Y COMPUTACIÓN PERIODO: Enero - Junio 2020 </p>

###  <p align="center">  Carrera: Ing. En Sistemas Computacionales. Materia: 	Datos Masivos (BDD-1704 IF9A	).</p>

### <p align="center">  Maestro: Jose Christian Romero Hernandez	</p>
### <p align="center">  No. de control y nombre del alumno:  </p>
### <p align="center">  No. de control y nombre del alumno:16210585 - Valenzuela Rosales Marco Asael </p>
### <p align="center">  No. de control y nombre del alumno:13210388 - Ivan Adrian Torres Flores </p>



# Unit 1

## Index
&nbsp;&nbsp;&nbsp;[Practice 1](#practice-1)  
&nbsp;&nbsp;&nbsp;[Practice 2](#practice-2)  
&nbsp;&nbsp;&nbsp;[Practice 3](#practice-3)  
&nbsp;&nbsp;&nbsp;[Practice 4](#Practice-4)  
&nbsp;&nbsp;&nbsp;[Practice 5](#practice-5)  

&nbsp;&nbsp;&nbsp;[Homework 1](#[Homework-1)  
&nbsp;&nbsp;&nbsp;[Homework 2](#[Homework-2)  
&nbsp;&nbsp;&nbsp;[Homework 3 ](#[Homework-3)  
&nbsp;&nbsp;&nbsp;[Exam 2]      #[Exam-2)   




### &nbsp;&nbsp;Practice 1.

       
#### &nbsp;&nbsp;&nbsp;&nbsp; Code ANd Instruccions.
```
 1.working directory
 getwd()
  setwd("/home/marco/Escritorio/DataMining-master/MachineLearning/SimpleLinearRegression")
  getwd()

2.We import the data set in which we will work
  dataset <- read.csv('Salary_Data.csv')

3.We install the Library caTools
Install.packages('caTools)
library(caTools

4 Splitting the dataset into the Training set and Test set
set.seed(123)
split <- sample.split(dataset$Extent, SplitRatio = 2/3)
training_set <- subset(dataset, split == TRUE)
test_set <- subset(dataset, split == FALSE)

Set the seed of R‘s random number generator, which is useful for creating simulations or random objects that can be reproduced.
    sample.split() is used to split the data used during classification into train and test subsets. The following arguments are used:

        Variable with the dataset (dataset) + $ + name of the column to predict (Extent).
        SplitRatio = ratio for dividing the data.
            For example in SplitRatio = 2/3, it means 1/3 of the data will be used for tests and 2/3 for training.

    subset() its a function that allows to select variables and observations. The following arguments are used:

        Variable with the dataset (dataset).
        Condition to be met (split == TRUE).
            In this case, this is where the data that was separated with the previous function will be assigned to the training set.

```

### &nbsp;&nbsp;Practice 2.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.

    
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
``` 
1.working directory
getwd()
setwd("/home/marco/Escritorio/DataMining-master/MachineLearning/MultipleLinearRegression")
getwd()

2.We import the data set in which we will work
dataset <- read.csv('50_Startups.csv')

# Encoding categorical data 
dataset$State = factor(dataset$State,
                       levels = c('New York', 'California', 'Florida'),
                       labels = c(1,2,3))
3. Encoding categorical data

dataset$State = factor(dataset$State,
                       levels = c('New York', 'California', 'Florida'),
                       labels = c(1,2,3))

4.We install the Library caTools
Install.packages('caTools)
library(caTools)
5. Splitting the dataset into the Training set and Test set

set.seed(123)
split <- sample.split(dataset$Profit, SplitRatio = 0.8)
training_set <- subset(dataset, split == TRUE)
test_set <- subset(dataset, split == FALSE)

    set.seed() allows us to create a 'seed' for generating random data during tests with the data set.
    sample.split() is used to split the data set into training and test subsets.

 ``` 

### &nbsp;&nbsp;Practice 3.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.

    Run the code and explain the data 


#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
```
   1.working directory

getwd()
setwd("C:/Users/GitHub/DataMining/MachineLearning/MultipleLinearRegression")
getwd()

2.We import the data set in which we will work

dataset <- read.csv('50_Startups.csv')

3. Encoding categorical data

dataset$State = factor(dataset$State,
                       levels = c('New York', 'California', 'Florida'),
                       labels = c(1,2,3))

    The function factor is used to encode a vector as a factor.
    In other words, the above code is used to transform the values of a text type category to the numeric type; for example, the values of the State category: New York, California and Florida, are changed by labels 1, 2 and 3.
```
#### &nbsp;&nbsp;Practice 4.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       Run the code and explain 
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
```

1.working directory
getwd()
setwd("/home/marco/Escritorio/DataMining-master/MachineLearning/LogisticRegression")
getwd()


2.We import the data set in which we will work
dataset <- read.csv('Social_Network_Ads.csv')
dataset <- dataset[, 3:5]


3. Splitting the dataset into the Training set and Test set

library(caTools)
set.seed(123)
split <- sample.split(dataset$Purchased, SplitRatio = 0.75) 
training_set <- subset(dataset, split == TRUE)
test_set <- subset(dataset, split == FALSE)

    A 'seed' is used to randomize data selection during data division (75% for training and 25% for testing).

4. Feature scaling

training_set[, 1:2] <- scale(training_set[, 1:2])
test_set[, 1:2] <- scale(test_set[, 1:2])

    scale is generic function whose default method centers and/or scales the columns of a numeric matrix.
    In other words, scale is used to transform (to base logarithm e) and give a scaled meaning to the data to be used, in this case we indicate that we only want to apply the changes to columns 1 and 2 ([, 1:2]).

5. Fitting Logistic Regression to Training set

classifier = glm(formula = Purchased ~ .,
                 family = binomial,
                 data = training_set)

    glm is used to fit generalized linear models, specified by giving a symbolic description of the linear predictor and a description of the error distribution.
```
### &nbsp;&nbsp;Practice 5.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       Explain the code and the graph

#### &nbsp;&nbsp;&nbsp;&nbsp; Code.

       Support Vector Machine (SVM)
       1.working directory
       getwd()
       setwd("home/marco/Escritorio/DataMining-master/MachineLearning/SVM")
       getwd()
       2.We import the data set in which we will work
       dataset = read.csv('Social_Network_Ads.csv')
       dataset = dataset[3:5]

          We load the file with the dataset and we indicate that we only want to work with columns from 3 to 5.

       3. Encoding the target feature as factor

       dataset$Purchased = factor(dataset$Purchased, levels = c(0, 1))

       4. Splitting the dataset into the Training set and Test set

       library(caTools)
       set.seed(123)
       split = sample.split(dataset$Purchased, SplitRatio = 0.75)
       training_set = subset(dataset, split == TRUE)
       test_set = subset(dataset, split == FALSE
       We load the caTools library, create the seed to randomize the data, divide the data 75% for training and 25% for                                   testing, and create the training and testing subsets.

       5. Feature Scaling

       training_set[-3] = scale(training_set[-3])
       test_set[-3] = scale(test_set[-3])

    scale is generic function whose default method centers and/or scales the columns of a numeric matrix.
    It is used to transform, give scala meaning to data, and help make the algorithm lighter; in this case we indicate that we want to apply the changes to all the columns except the prediction column.

### &nbsp;&nbsp;HomeWork 1 Main Types of Machine Learning Algorithms.

       Machine Learning came a long way from a science fiction fancy to a reliable and diverse business tool that amplifies multiple elements of the business operation.
       Its influence on business performance may be so significant that the implementation of machine learning algorithms is required to maintain competitiveness in many fields and industries.
       The implementation of machine learning into business operations is a strategic step and requires a lot of resources. Therefore, it's important to understand what do you want the ML to do for your particular business and what kind of perks different types of ML algorithms bring to the table. 

       Machine learning algorithms can divide into three broad categories: supervised learning, unsupervised learning, and reinforcement learning. Supervised learning is useful in cases where a property (label) is available for a specific set of data, but must be predicted for other instances. Unsupervised learning is useful in cases where the challenge is to discover implicit relationships in an unlabelled dataset (elements are not previously assigned). Reinforcement learning falls between these two extremes: there is some form of feedback available for each step or predictive action, but there is no precise label or error message.

       SUPERVISED LEARNING

       1. Decision trees: A decision tree is a decision support tool that uses a graph or model similar to a decision tree and its possible consequences, including the results of fortuitous events, resource costs, and utility . They have an appearance like this:

       
       

          From a business decision-making point of view, a decision tree is the minimum number of yes / no questions that one has to ask, to assess the probability of making a correct decision, most of the time. This method allows you to approach the problem in a structured and systematic way to reach a logical conclusion.




       2. Naïve Bayes Classification: Naïve Bayes classifiers are a family of simple probabilistic classifiers based on the application of Bayes ‘theorem with strong (Naïve) assumptions of independence between characteristics’. The featured image is the equation - with P (A | B) being posterior probability, P (B | A) being probability, P (A) being class prior probability, and P (B) being prior probability predictor.


       3. Ordinary Least Squares Regression: If you've been in contact with statistics, you've probably heard of linear regression before. Ordinary Least Squares Regression is a method of performing linear regression. Linear regression can be thought of as the task of fitting a straight line through a set of points. There are several possible strategies for doing this, and the "ordinary least squares" strategy goes like this: you can draw a line and then, for each of the data points, measure the vertical distance between the point and the line and add them together; The fitted line would be the one in which this sum of distances is as small as possible.

       4. Logistic Regression: Logistic regression is a powerful statistical way to model a binomial result with one or more explanatory variables. Measure the relationship between the categorical dependent variable and one or more independent variables by estimating the probabilities using a logistic function, which is the cumulative logistic distribution.


### &nbsp;&nbsp;HomeWork 2 VectorAssembler Library
       VectorAssembler is a transformer that combines a given list of columns into a single vector column. It is useful for combining raw features and features generated by different feature transformers into a single feature vector, in order to train ML models like logistic regression and decision trees. VectorAssembler accepts the following input column types: all numeric types, boolean type, and vector type. In each row, the values of the input columns will be concatenated into a vector in the specified order.
       Examples
       Assume that we have a DataFrame with the columns id, hour, mobile, userFeatures, and clicked:
        id | hour | mobile | userFeatures     | clicked
       ----|------|--------|------------------|---------
        0  | 18   | 1.0    | [0.0, 10.0, 0.5] | 1.0
       userFeatures is a vector column that contains three user features. We want to combine hour, mobile, and userFeatures into a single feature vector called features and use it to predict clicked or not. If we set VectorAssembler’s input columns to hour, mobile, and userFeatures and output column to features, after transformation we should get the following DataFrame:
        id | hour | mobile | userFeatures     | clicked | features
       ----|------|--------|------------------|---------|-----------------------------
        0  | 18   | 1.0    | [0.0, 10.0, 0.5] | 1.0     | [18.0, 1.0, 0.0, 10.0, 0.5]

       Vectors Library

       Factory methods for org.apache.spark.ml.linalg.Vector. We don't use the name Vector because Scala imports scala.collection.immutable.Vector by default.



### &nbsp;&nbsp;HomeWork3 Pipeline and Confusion Matrix.
       Main concepts in Pipelines
       MLlib standardizes APIs for machine learning algorithms to make it easier to combine multiple algorithms into a single pipeline, or workflow. This section covers the key concepts introduced by the Pipelines API, where the pipeline concept is mostly inspired by the scikit-learn project.
           • DataFrame: This ML API uses DataFrame from Spark SQL as an ML dataset, which can hold a variety of data types. E.g., a DataFrame could have different columns storing text, feature vectors, true labels, and predictions.
           • Transformer: A Transformer is an algorithm which can transform one DataFrame into another DataFrame. E.g., an ML model is a Transformer which transforms a DataFrame with features into a DataFrame with predictions.
           • Estimator: An Estimator is an algorithm which can be fit on a DataFrame to produce a Transformer. E.g., a learning algorithm is an Estimator which trains on a DataFrame and produces a model.
           • Pipeline: A Pipeline chains multiple Transformers and Estimators together to specify an ML workflow.
           • Parameter: All Transformers and Estimators now share a common API for specifying parameters.
       Pipeline components
       Transformers

       A Transformer is an abstraction that includes feature transformers and learned models. Technically, a Transformer implements a method transform(), which converts one DataFrame into another, generally by appending one or more columns. For example:

           A feature transformer might take a DataFrame, read a column (e.g., text), map it into a new column (e.g., feature vectors), and output a new DataFrame with the mapped column appended.
           A learning model might take a DataFrame, read the column containing feature vectors, predict the label for each feature vector, and output a new DataFrame with predicted labels appended as a column.

       Estimators

       An Estimator abstracts the concept of a learning algorithm or any algorithm that fits or trains on data. Technically, an Estimator implements a method fit(), which accepts a DataFrame and produces a Model, which is a Transformer. For example, a learning algorithm such as LogisticRegression is an Estimator, and calling fit() trains a LogisticRegressionModel, which is a Model and hence a Transformer.
       Properties of pipeline components

       Transformer.transform()s and Estimator.fit()s are both stateless. In the future, stateful algorithms may be supported via alternative concepts.

       Each instance of a Transformer or Estimator has a unique ID, which is useful in specifying parameters (discussed below).
       Pipeline

       In machine learning, it is common to run a sequence of algorithms to process and learn from data. E.g., a simple text document processing workflow might include several stages:

           1.     Split each document’s text into words.
           2.     Convert each document’s words into a numerical feature vector.
           3.     Learn a prediction model using the feature vectors and labels.

       MLlib represents such a workflow as a Pipeline, which consists of a sequence of PipelineStages (Transformers and Estimators) to be run in a specific order. We will use this simple workflow as a running example in this section.
       How it works

       A Pipeline is specified as a sequence of stages, and each stage is either a Transformer or an Estimator. These stages are run in order, and the input DataFrame is transformed as it passes through each stage. For Transformer stages, the transform() method is called on the DataFrame. For Estimator stages, the fit() method is called to produce a Transformer (which becomes part of the PipelineModel, or fitted Pipeline), and that Transformer’s transform() method is called on the DataFrame.




### &nbsp;&nbsp;Exam 2.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       Develop the following problem with R and RStudio for the knowledge extraction that the problem requires.

       Description
       The directors of the movie review website are very happy with their previous delivery and now they have a new requirement for you.
       The previous consultant had created a chart for them that is illustrated in the following image.


       However, the R code used to create the graph has been lost and cannot be recovered.
       Your task is to create the code that will recreate the same table making it look as close to the original as possible.
       You will be provided with a new data set.

       Hint
       Please keep in mind that not all Genres and Studio are used.
       You will need to filter your dataframe after importing the csv file.



#### &nbsp;&nbsp;&nbsp;&nbsp; Code.

## getwd()
## setwd("/home/marco/Escritorio/DataMining-master/Datasets")
## getwd()


## dataset <- read.csv('Project-Data.csv')



## colnames(dataset) <- c("DayWeek", "Director","Genre","MovieTitle", "Release", 
                       "Studio", "AdjustGross","BudgetMillions", "GrossMillions","IMDbRating",
                       "MovieLensRating","OverseasMillions", "Overseas_%","ProfitMillions",
                       "Profit%", "RuntimeMin","UsMillions", "Gross_US")

## head(dataset)

df.dataset = dataset[(dataset$Genre == "action"|dataset$Genre == "adventure"
                    |dataset$Genre == "animation"|dataset$Genre == "comedy"
                    |dataset$Genre == "drama")&(dataset$Studio == "Buena Vista Studios"
                    |dataset$Studio == "Fox"|dataset$Studio == "Paramount Pictures"
                    |dataset$Studio == "Sony"|dataset$Studio == "Universal"
                    |dataset$Studio == "WB"),]
## df.dataset

## library(ggplot2)

 ` We load the ggplot2 library to be able to make the graph.


## ggplot(df.dataset, aes(x = Genre, y = Gross_US)) + 
  geom_jitter(aes(color = Studio, size = BudgetMillions)) + 
  geom_boxplot(alpha = 0.5) + 
  geom_smooth(method = "loess", formula = y ~ x) + 
  xlab("Genre") + ylab("Gross % US") + 
  ggtitle("Domestic Gross % by Genre") + 
  theme(axis.title.x = element_text(color = "black",size = 9,family = "Serif"),
        axis.title.y = element_text(color = "black",size = 9,family = "Serif"),
        axis.text.x = element_text(family = "Serif", size = 9),
        axis.text.y = element_text(family = "Serif",size = 9),
        legend.title = element_text(family = "Serif",size = 15),
        legend.text = element_text(family = "Serif"),
        plot.title = element_text(color = "black",size = 9,hjust = 0.5,family = "Serif"))
        
        The ggplot function is used for data that is used to make the graph, as well as for each axis (x that will be = Gender is the gross profit of the films

The geom_jitter function is used to graph the data as points, it helps us to disperse the points and the data can be better observed, the color for study and the size of the points for the BUDGET of the films are specified

Specifically, another type of graph that is geom_boxplot is in charge of creating the box graphs, the alpha argument is used to see how transparent the box looked, we put it low so that it helps us to visualize the points of the other graph
loess () is used for less than 1,000 observations

xlab and ylab are used to specify the names of each axis in the graph.
The ggtitle function allows you to assign a name to our graph.

The theme function is used to modify labels, headings, and font styles.
axis.title helps us modify the titles of our x and y axes, axis.text must use the element_text function to be able to make changes to the values to color, the font sixe, the Typeface and the type of font

legend.title allows us to modify the titles of the legend of the graph that in this case seriously studies and BullegMillionsl needs to use the element_text function, as in the previous cases.
leyenda.text allows us to modify the text of the legends
plot.title allows us to modify the title of the graph






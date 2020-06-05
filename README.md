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



# Unit 2

## Index
&nbsp;&nbsp;&nbsp;[Practice 1](#practice-1)  
&nbsp;&nbsp;&nbsp;[Practice 2](#practice-2)  
&nbsp;&nbsp;&nbsp;[Practice 3](#practice-3)  
&nbsp;&nbsp;&nbsp;[Practice 4](#Practice-4)  
&nbsp;&nbsp;&nbsp;[Practice 5](#practice-5)  
&nbsp;&nbsp;&nbsp;[HomeWork 1](#[Homework-1)  
&nbsp;&nbsp;&nbsp;[HomeWork 2](#[Homework-2)  
&nbsp;&nbsp;&nbsp;[HomeWork 3 ](#[Homework-3)  
&nbsp;&nbsp;&nbsp;[HomeWork 4](#[Homework-4)  
&nbsp;&nbsp;&nbsp;[HomeWork 5](#[Homework-5)  
&nbsp;&nbsp;&nbsp;[HomeWork 6](#[Homework-6)  
&nbsp;&nbsp;&nbsp;[Exam 2](#[Exam-2)  




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

### &nbsp;&nbsp;HomeWork 1 
       It is based on the Grammar of Graphics by Leland Wilkinson and is the most used package for producing graphics in R. This tells you that ggplot2 is worth the effort of learning. So let’s get you started with it!
       ggplot2 consists of the following elements:
       Essential Elements
       Data
       The data element is the data set itself
       Aesthetics
       The data is being mapped onto the aesthetics element (variables mapped to x or y position and aesthetics attributes such as color, shape, or size)
       Geometries
       This element determines how our data is being displayed (bars, points, lines)
       Every single plot that you will ever make consists of these three essential elements.
       Optional
       Facets
       Facetting splits the data into subsets and displays the same graph for every subset.
       Statistics
       Let’s you transform our data (add mean, median, quartile)
       Coordinates
       Transforms axes (changes spacing of displayed data)
       Themes
       Let’s you change the graphics background, axis size, or header.
       This grammar is useful for both the user and the developer of statistical graphics. For the user, it makes it easier to iteratively update a plot, changing a single feature at a time. The grammar is also useful because it suggests the high-level aspects of a plot that can be changed, giving us a framework to think about graphics, and hopefully shortening the distance from mind to paper. It also encourages the use of graphics customized to a particular problem rather than relying on generic named graphics.




       Example 
       Let us use a Pokemon data set from Kaggle to pick up some ggplot2 knowledge.
       str(poke)
       'data.frame':	800 obs. of  13 variables:
        $ X.        : int  1 2 3 3 4 5 6 6 6 7 ...
        $ Name      : Factor w/ 800 levels "Abomasnow","AbomasnowMega Abomasnow",..: 81 330 746 747 103 104 100 101 102 666 ...
        $ Type.1    : Factor w/ 18 levels "Bug","Dark","Dragon",..: 10 10 10 10 7 7 7 7 7 18 ...
        $ Type.2    : Factor w/ 19 levels "","Bug","Dark",..: 15 15 15 15 1 1 9 4 9 1 ...
        $ Total     : int  318 405 525 625 309 405 534 634 634 314 ...
        $ HP        : int  45 60 80 80 39 58 78 78 78 44 ...
        $ Attack    : int  49 62 82 100 52 64 84 130 104 48 ...
        $ Defense   : int  49 63 83 123 43 58 78 111 78 65 ...
        $ Sp..Atk   : int  65 80 100 122 60 80 109 130 159 50 ...
        $ Sp..Def   : int  65 80 100 120 50 65 85 85 115 64 ...
        $ Speed     : int  45 60 80 80 65 80 100 100 100 43 ...
        $ Generation: int  1 1 1 1 1 1 1 1 1 1 ...
        $ Legendary : Factor w/ 2 levels "False","True": 1 1 1 1 1 1 1 1 1 1 ...



       gplot2 plots are objects which means that you can assign them. If we would display the plot now then we wouldn’t see anything yet because we have not specified the geometric element yet. The first argument in ggplot() is the data frame. In the second argument,  we map the data onto the x-axis and y-axis with the aesthetics element.
       We have two continuous variables with Attack and Defense. Hence, a scatterplot would be appropriate.
       You can create a scatter plot by adding the geom_point() function to our existing object, atk_vs_def. This would look like this:




### &nbsp;&nbsp;HomeWork 2 VectorAssembler Library
       Geom_Jitter()
       The jitter geom is a convenient shortcut for geom_point(position = "jitter"). It adds a small amount of random variation to the location of each point, and is a useful way of handling overplotting caused by discreteness in smaller datasets.
       Examples 
       geom_jitter(
         mapping = NULL,
         data = NULL,
         stat = "identity",
         position = "jitter",
         ...,
         width = NULL,
         height = NULL,
         na.rm = FALSE,
         show.legend = NA,
         inherit.aes = TRUE
       )

    Arguments
       mapping	
       Set of aesthetic mappings created by aes() or aes_(). If specified and inherit.aes = TRUE (the default), it is combined with the default mapping at the top level of the plot. You must supply mapping if there is no plot mapping.

       data	
       The data to be displayed in this layer. There are three options:

       If NULL, the default, the data is inherited from the plot data as specified in the call to ggplot().

       A data.frame, or other object, will override the plot data. All objects will be fortified to produce a data frame. See fortify() for which variables will be created.

       A function will be called with a single argument, the plot data. The return value must be a data.frame, and will be used as the layer data. A function can be created from a formula (e.g. ~ head(.x, 10)).

       stat	
       The statistical transformation to use on the data for this layer, as a string.



### &nbsp;&nbsp;HomeWork 3.
       What is a p-value?
       In statistics, the p-value is the probability of obtaining results as extreme as the observed results of a statistical hypothesis test, assuming that the null hypothesis is correct. The p-value is used as an alternative to rejection points to provide the smallest level of significance at which the null hypothesis would be rejected. A smaller p-value means that there is stronger evidence in favor of the alternative hypothesis.
       How Is P-Value Calculated?
       P-values are calculated using p-value tables or spreadsheets/statistical software. Because different researchers use different levels of significance when examining a question, a reader may sometimes have difficulty comparing results from two different tests. P-values provide a solution to this problem.

       For example, if a study comparing returns from two particular assets were undertaken using by different researchers who used the same data but different significance levels, the researchers might come to opposite conclusions regarding whether the assets differ.

### &nbsp;&nbsp;HomeWork 4.
       lm()
       lm is used to fit linear models. It can be used to carry out regression, single stratum analysis of variance and analysis of covariance (although aov may provide a more convenient interface for these).

       Keywords
       Regression
       Usage
       lm(formula, data, subset, weights, na.action,
          method = "qr", model = TRUE, x = FALSE, y = FALSE, qr = TRUE,
          singular.ok = TRUE, contrasts = NULL, offset, …)
       Arguments
       formula
       an object of class "formula" (or one that can be coerced to that class): a symbolic description of the model to be fitted. The details of model specification are given under ‘Details’.

       data
       an optional data frame, list or environment (or object coercible by as.data.frame to a data frame) containing the variables in the model. If not found in data, the variables are taken from environment(formula), typically the environment from which lm is called.

       subset
       an optional vector specifying a subset of observations to be used in the fitting process.

       weights
       an optional vector of weights to be used in the fitting process. Should be NULL or a numeric vector. If non-NULL, weighted least squares is used with weights weights (that is, minimizing sum(w*e^2)); otherwise ordinary least squares is used. See also ‘Details’,

### &nbsp;&nbsp;HomeWork 5.
       glm()
       Fitting Generalized Linear Models
       glm is used to fit generalized linear models, specified by giving a symbolic description of the linear predictor and a description of the error distribution.
       Keywords
       models, regression
       Usage
       glm(formula, family = gaussian, data, weights, subset,
           na.action, start = NULL, etastart, mustart, offset,
           control = list(…), model = TRUE, method = "glm.fit",
           x = FALSE, y = TRUE, singular.ok = TRUE, contrasts = NULL, …)
       glm.fit(x, y, weights = rep(1, nobs),
               start = NULL, etastart = NULL, mustart = NULL,
               offset = rep(0, nobs), family = gaussian(),
               control = list(), intercept = TRUE, singular.ok = TRUE)

       # S3 method for glm
       weights(object, type = c("prior", "working"), …)





       Arguments
       formula
       an object of class "formula" (or one that can be coerced to that class): a symbolic description of the model to be fitted. The details of model specification are given under ‘Details’.

       family
       a description of the error distribution and link function to be used in the model. For glm this can be a character string naming a family function, a family function or the result of a call to a family function. For glm.fit only the third option is supported. (See family for details of famil  y functions.)
       
       
### &nbsp;&nbsp;HomeWork 6.

       The package ‘ElemStatLearn’ was removed from the CRAN repository, although formerly available versions can be obtained from the archive.
       This library contents Data Sets, Functions and Examples from the Book: "The Elements of Statistical Learning, Data Mining, Inference, and Prediction" by Trevor Hastie, Robert Tibshirani and Jerome Friedman.


### &nbsp;&nbsp;Exam_1.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       Develop the following problem with R and RStudio for the knowledge extraction that the problem requires.

       Description
       The directors of the movie review website are very happy with their previous delivery and now they have a new requirement for you.
       The previous consultant had created a chart for them that is illustrated in the following image.
       
 # RStudio
Class Session
![R Studio]https://github.com/ivanatorresf/Data_Mining/blob/unidad_2/Captura%20de%20pantalla%20-2020-05-29%2011-18-50.png


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

  We load the ggplot2 library to be able to make the graph.


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

# RStudio
       Class Session
       ![R Studio]https://github.com/ivanatorresf/Data_Mining/blob/unidad_2/Captura%20de%20pantalla%20-2020-05-29%2010-51-35.png

       We can see the action genre is the one with the largest number of movies and having many movies has the highest budget invested budget
       The other thing that can be observed is that in genres like adventure and drama they have few movies, animated movies have more than; like adventure and drama but it has a lower budget percentage than the other genres on the chart, and the comedy genre is at an average percentage


       Fox of all the studies is the one that produces fewer movies,Buena Vista Studios STUDIO IS THE ONE THAT INVESTES MORE IN THE FILMS BUDGET FOLLOWING WB,Buena VISTA sTUDIOS produces more animated films than others,Universal has all genres but focuses more on the comedy genre

### &nbsp;&nbsp;Exam_2.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
# install.packages("naivebayes")
# library(e1071)
# library(naivebayes)
# library(caret)

getwd()
setwd("/home/marco/Escritorio/DataMining-master/Datasets")
getwd()


dataset <- read.csv('Social_Network_Ads.csv')

dataset$User.ID <- NULL
dataset$Age <- as.factor(dataset$Age)
dataset$EstimatedSalary <- as.factor(dataset$EstimatedSalary)
dataset$Purchased <- as.factor(dataset$Purchased)


set.seed(123)
t.ids<-createDataPartition(dataset$Purchased, p= 0.60, list = F)
mod<- naiveBayes(Purchased ~., data= dataset[t.ids,])
mod
mod$levels <- NULL

pred <- predict(mod, dataset[-t.ids,])
tab <- table(dataset[-t.ids,]$Purchased, pred, dnn = c("Actual", "Prediccion"))
confusionMatrix(tab)


`Explication Exam Code 
How about classmates we are back with another example in Rstudio with my partner ivan torres, in this video we will explain
the naibbayes algorithm, before starting to specify that we could achieve this exercise thanks to Juan Gabriel Gomila for his
explanation, we were able to understand a little more the naibayes algorithm

before starting with the code we must install the naivebayes library can be done by installing the e1071 library that
contains it and the naivebayes library and we save a little more time and also install the caret library
It includes a series of functions that facilitate the use of dozens of complex classification and regression methods. 
using this package instead of the original functions of the methods has advantages which are

It is easier to put into practice some usual procedures in classification problems. For example, there are specific 
functions to divide the sample into training data and test data or to adjust parameters by cross-validation.

Let's run the libraries so that they are activated to implement them
I do not know if they can see when running the caret package it also runs the lattice and ggplot2 package without
us needing to run it, one thing before is that the caret library takes several minutes to install for everything it contains.

Then we will use the getwwd to see what route we are on with the setwd we put the route we will be working on and 
we run getwd again to see that if we are on the route we specify
Then we will load the dataset using read.csv that will serve to load our data file

the moment we started with the code we found that some errors were marked and we did not know the source of the error, 
until we decided to see what happened when deleting one of the columns that we would not occupy in this case it would
be the id since we would not occupy it in the implementation of the algorithm and how it is a specific number for the 
person would not serve us

Another error that we found was that all the values ​​or arguments had to be equal, for this we found a way to convert 
the data to a factor and so they were all the same.We have our dataset using the sign of weights that we know is to be
able to relate it to the information. that we occupy, with the function as.factor then in parentheses we put our dataset
with Age that is age and thus makes it a factor
`
WHAT IS NAIVE BAYES
Naive Bayes models are a special class of Automatic Learning, or Machine Learning, classification algorithms, as we will refer from now on. They are based on a statistical classification technique called "Bayes' theorem".

These models are called “Naive” algorithms, or “Innocents” in Spanish. They assume that the predictor variables are independent of each other.
These provide an easy way to build models with very good behavior due to their simplicity.

Well we started training with the data and we are going to train the model with naive bayes
in the line we place the seed with set.seed (123)

then we will create the training set with t.ids ← createpartition and between paracentesis we put our dataset Purchased weight sign which is what we want to predict with probability = 0.60 and as a list we put in False format so that it gives us in array format

and then we will use our model on the line with mod and using the naive bayes function LET'S SEE HERE WE HAVE TO USE THE E1071 PACKAGE

and then when trying to predict the variable that is Purchased based on all the previous dataframe ep taking only the indices of the traind ids and all the columns

well now we are going to train the model and we see that it has 4 variables
and with mod we can see it
WHAT IS NAIVE BAYES
Naive Bayes models are a special class of Automatic Learning, or Machine Learning, classification algorithms, as we will refer from now on. They are based on a statistical classification technique called "Bayes' theorem".

These models are called “Naive” algorithms, or “Innocents” in Spanish. They assume that the predictor variables are independent of each other.
These provide an easy way to build models with very good behavior due to their simplicity.

Well we started training with the data and we are going to train the model with naive bayes
in the line we place the seed with set.seed (123)

then we will create the training set with t.ids ← createpartition and between paracentesis we put our dataset Purchased weight sign which is what we want to predict with probability = 0.60 and as a list we put in False format so that it gives us in array format

and then we will use our model on the line with mod and using the naive bayes function LET'S SEE HERE WE HAVE TO USE THE E1071 PACKAGE

and then when trying to predict the variable that is Purchased based on all the previous dataframe ep taking only the indices of the traind ids and all the columns

well now we are going to train the model and we see that it has 4 variables
and with mod we can see it

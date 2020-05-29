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

&nbsp;&nbsp;&nbsp;[Homework 1](#[Homework 1)  
&nbsp;&nbsp;&nbsp;[Homework 2](#[Homework 2)  
&nbsp;&nbsp;&nbsp;[Homework 3](#[Homework 3)  




### &nbsp;&nbsp;Practice 1.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       1.Test the Law of Large Number for N random normally distributed numbers with mean = 0, stdev = 1
       2.Create an R script that will count how many of these numbers fall between -1 and 1 and divide by 
       the total quantity of N
       3.Theoretical E(X) = 68.2%
       4.Find out N that could result E(X) to be = 68.2%
       
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
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
    1.Practice find 20 more functions in R and make an example of it.
    
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
``` 
    1. ceiling(3.475) 
    2.floor(3.475)
    3.sqrt(9)
    4.x <- "abcdef"
    5.substr(x, 2, 4) 
    6.dbinom(0:5, 10, .5)
    7.dunif(10, min=0, max=1)
    8.punif(10, min=0, max=1)
    9.median(10,na.rm = FALSE)
    10.diff(45, lag=1)

    Working with R Matrices
    To create an array in R the function is used
    matrix(data = NA, nrow = 1, ncol = 1, byrow = FALSE, dimnames = NULL)
    where matrix () corresponds to the name of the function and everything inside the parentheses are the arguments of that
    function.

    #1
    A<-matrix(c(5, 7, 13, 4, 1, 7, 14, 3, 11), nrow=3, ncol=3, byrow=F,
    +dimnames=list(c("Blanco", "Negro", "Rojo"), c("Toyota", "Audi", "Nissan")))

    #2
     Adding Rows and Columns to a matrix: rbind and cbind functions
    To add a row to an existing matrix as in the case of matrix A created in the previous example,
     the rbind () function must be used and the cbind () function will be used to add columns to an array.
    As an example we will add a new color to the matrix A, which should be understood that a
    roll below Red which we will call Blue and will contain the values ​​8, 5, 7.
    With which we will do:

    Azul<-c(8,5,7) # with this we create the Blue vector with its corresponding elements
    A<-rbind(A, Azul)

    #3
     Now we will add to that same matrix A, a new column called Hyundai and will contain the following values ​​2, 7, 3, 5
    Hyundai <-c (2,7,3,5) # with this we create the Hyundai vector with its corresponding elements

    A<-cbind(A,Hyundai)

    #4
    Selecting elements of an array.
    The elements of an array are indexed with two indexes which makes it easy to access the elements
    and work with them if what interests us is only part of the information contained in a matrix and not the matrix
    integer, this is achieved with the indexing operator [i, j] where i is the row element and j is the column element,
    This is because if A is an array, then its elements will be $ a_ {i, j} $, so if we wanted to select
    The number of white cars corresponding to the Audi brand could be done in two ways:
    We write the name of the matrix and then in square brackets the location being [row name, column name],
    Names must be in quotes.
    A["Blanco", "Audi"] 
    [1] 7

    #6
    We write the name of the matrix and then in square brackets the location being [row number, column number]
    In the second order what is indicated to R is to show me the element that occupies the position (1,2), that is,
    that element that is in row 1 and column 2.
    A[1,2]
    [1] 7
    #7
    You can also select whole vectors, we will select all the vehicles corresponding to the white color,
    to do what we should ask R is to select us and show all the elements that are in row 1,  this is the way it is done:
    A[1,]               # another way to do it is
    A["Blanco",] 
    #8
    Eliminating rows and columns
    We have already seen how rows and columns are added to an existing matrix, but sometimes it is also useful to delete them
    and as easy as it is to add so easy is to delete as well.
    Next we will remove the row and column that we added in part 5 and 6 of the previous exercise,
    that is, we are going to eliminate the Green row and the Kia column.
    To eliminate rows or columns, you must take into account the way to index Matrices, here is a document that
    explains this very well.

    Removing the Kia column
    A<-A[ ,-5]
    A<-A[ ,-"Kia"]
    Deleting the Green row
    A<-A[-5,]
    A<-A[-"Verde",]
    It could also have been deleted at once
    A<-A[-5,-5] ó 
    A<-A[-"Verde",-"Kia"]
            
    #9
    Transpose a Matrix
    A very useful function is the transposition of matrices, as already mentioned in Introduction
    a the basic functions of R: Functions with Vectors, the function t () is to transpose both vectors and matrices,
    in this case we will use it to transpose the matrix A that we have created and edited throughout this page.
    Matriz A
    print(A)
    Transpuesta de A
    t(A)
    #10
    Add and subtract matrices
    Two matrices are conformable for addition and subtraction if they are of the same dimension, having this in mind, in R we can
    easily add and subtract matrices indicating the sum with + and the subtraction with -
     Next we will add the transposition to matrix A of our previous example and then to matrix A we will subtract
    your transposed.

    A + t(A)
    A+t(A) 

    A - t(A)
    A-t(A)
 ``` 

### &nbsp;&nbsp;Practice 3.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.

    Scenario: You are a Data Scientist working for a consulting firm.
    One of your colleagues from the Auditing Department has asked you
    to help them assess the financial statement of organization X.

    You have been supplied with two vector of data: mounthly revenue and
    expenses for the financial year in quiestion. Your task is to calculate
    the following financial matrics:

    - profit for each mounth
    - profit after tax for each month (the tax rate is 30%)
    - profit margin for each month - equal to profit after tax divided by revenue
    - good months - where the profit after tax was greater than the mean for the year
    - bad months - where the profit after tax was less then the mean for years
    - the best month - where the profit after tax was max for the year
      - the worst month - where the profit after tax was min for the year

    All results need to be presented as vectors.

    Results for dollar values need to be calculate with $0.01 precision, but need to be
    presented in Units of $1,000(i.e. 1k) with no decimal point.

    Results for the profit margin ratio needed to be presented in units of % with no
    decimal points.

    Note: Your collegue has warned you that it is okay for tax for any given month to be
    negative (in accounting terms, negative tax translates into a deferred tax asset).

    Hint 1
    Use:
    round()
    mean()
    max()
    min()


#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
```
    #Data
    revenue <- c(14574.49, 7606.46, 8611.41, 9175.41, 8058.65, 8105.44, 11496.28, 9766.09, 10305.32, 14379.96, 10713.97,          15433.50)
    expenses <- c(12051.82, 5695.07, 12319.20, 12089.72, 8658.57, 840.20, 3285.73, 5821.12, 6976.93, 16618.61, 10054.37, 3803.96)

    #Solution
    #Calculate Profit As The Differences Between Revenue And Expenses
    profit <- revenue - expenses
    profit

    #Calculate Tax As 30% Of Profit And Round To 2 Decimal Points
    tax <- round(0.30 * _, _)
    tax 

    #Calculate Profit Remaining After Tax Is Deducted
    profit.after.tax <- _ - _
      profit.after.tax

    #Calculate The Profit Margin As Profit After Tax Over Revenue
    #Round To 2 Decimal Points, Then Multiply By 100 To Get %
    profit.margin <- round(profitAt / revenue, 2) * 100
    profit.margin

    #Calculate The Mean Profit After Tax For The 12 Months
    mean_pat <- mean(profitAt)
    mean_pat

     Find The Months With Above-Mean Profit After Tax
    good.months <- _ _ mean_pat
    good.months

    #Bad Months Are The Opposite Of Good Months !
    bad.months <- _good.months
    bad.months

    #The Best Month Is Where Profit After Tax Was Equal To The Maximum
    best.month <- profit.after.tax == _(profit.after.tax)
    best.month

    #The Worst Month Is Where Profit After Tax Was Equal To The Minimum
    worst.month <- _ == _(_)
    worst.month

    #Convert All Calculations To Units Of One Thousand Dollars
    revenue.1000 <- round(revenue / 1000, 0)
    expenses.1000 <- _(_ _ _, _)
    profit.1000 <- _(_ _ _, _)
    profit.after.tax.1000 <- _(_ _ _, _)

    #Print Results
    revenue.1000
    expenses.1000
    profit.1000
    profit.after.tax.1000
    profit.margin
    good.months
    bad.months
    best.month
    worst.month

    #BONUS:
    #Preview Of What's Coming In The Next Section
    M <- rbind(
    revenue.1000,
    expenses.1000,
    profit.1000,
    profit.after.tax.1000,
    profit.margin,
    good.months,
    bad.months,
     best.month,
       worst.month
    )

   

    #Data
    revenue <- c(14574.49, 7606.46, 8611.41, 9175.41, 8058.65, 8105.44, 11496.28, 9766.09, 10305.32, 14379.96, 10713.97, 15433.50)
    expenses <- c(12051.82, 5695.07, 12319.20, 12089.72, 8658.57, 840.20, 3285.73, 5821.12, 6976.93, 16618.61, 10054.37, 3803.96)

    #Solution
    #Calculate Profit As The Differences Between Revenue And Expenses
    profit <- revenue - expenses
    profit

    #Calculate Tax As 30% Of Profit And Round To 2 Decimal Points
    tax <- round(0.30 * profit, 2)
     tax 

    #Calculate Profit Remaining After Tax Is Deducted
    profit.after.tax <- profit - tax
    profit.after.tax

    #Calculate The Profit Margin As Profit After Tax Over Revenue
    #Round To 2 Decimal Points, Then Multiply By 100 To Get %
    profit.margin <- round(profit.after.tax / revenue, 2) * 100
    profit.margin

    #Calculate The Mean Profit After Tax For The 12 Months
    mean_pat <- mean(profit.after.tax)
    mean_pat

    #Find The Months With Above-Mean Profit After Tax
    good.months <- profit.after.tax > mean_pat
    good.months

    #Bad Months Are The Opposite Of Good Months !
    bad.months <- !good.months
    bad.months

    #The Best Month Is Where Profit After Tax Was Equal To The Maximum
    best.month <- profit.after.tax == max(profit.after.tax)
    best.month

    #The Worst Month Is Where Profit After Tax Was Equal To The Minimum
    worst.month <- profit.after.tax == min(profit.after.tax)
    worst.month

    #Convert All Calculations To Units Of One Thousand Dollars
    revenue.1000 <- round(revenue / 1000, 0)
    expenses.1000 <- round(expenses / 1000, 0)
    profit.1000 <- round(profit / 1000, 0)
    profit.after.tax.1000 <- round(profit.after.tax / 1000, 0)

    #Print Results
    revenue.1000
    expenses.1000
    profit.1000
    profit.after.tax.1000
    profit.margin
    good.months
    bad.months
    best.month
    worst.month

    #BONUS:
    #Preview Of What's Coming In The Next Section
    M <- rbind(
      revenue.1000,
    expenses.1000,
    profit.1000,
    profit.after.tax.1000,
    profit.margin,
    good.months,
    bad.months,
    best.month,
    worst.month
    )

    #Print The Matrix
    M
```
#### &nbsp;&nbsp;Practice 4.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       1.Free Trows
       2.Matrix for Free Throws
       3.Remove vectors - we don't need them anymore
       4.Rename the columns
       5.Rename the rows
       6.Check the matrix
       7.Free Trows Attempts
       8.Matrix for Free Throw Attempts
       9.Bind the given vectors to form the matrix
       10.Remove vectors - we don't need them anymore
       11.Rename the columns
       12.Rename the rows
       13.Check the matrix
       14.Re-create the plotting function
       15.Visualize the new matrices
       #Part 1 - Free Throw Attempts Per Game 
       #Part 2 - Free Throw Accuracy
       16.Field Goal Accuracy was exceptional:
       #Part 3 - Player Style Patterns Excluding Free Throws
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
```

       1.Free Trows
       KobeBryant_FT <- c(696,667,623,483,439,483,381,525,18,196)
       JoeJohnson_FT <- c(261,235,316,299,220,195,158,132,159,141)
       LeBronJames_FT <- c(601,489,549,594,593,503,387,403,439,375)
       CarmeloAnthony_FT <- c(573,459,464,371,508,507,295,425,459,189)
       DwightHoward_FT <- c(356,390,529,504,483,546,281,355,349,143)
       ChrisBosh_FT <- c(474,463,472,504,470,384,229,241,223,179)
       ChrisPaul_FT <- c(394,292,332,455,161,337,260,286,295,289)
       KevinDurant_FT <- c(209,209,391,452,756,594,431,679,703,146)
       DerrickRose_FT <- c(146,146,146,197,259,476,194,0,27,152)
       DwayneWade_FT <- c(629,432,354,590,534,494,235,308,189,284)
       
       2.Matrix for Free Throws
       #Bind the given vectors to form the matrix
       FreeThrows <- rbind(KobeBryant_FT, JoeJohnson_FT, LeBronJames_FT, CarmeloAnthony_FT, DwightHoward_FT, ChrisBosh_FT, ChrisPaul_FT,    KevinDurant_FT, DerrickRose_FT, DwayneWade_FT)
       
       3.Remove vectors - we don't need them anymore
       rm(KobeBryant_FT, JoeJohnson_FT, CarmeloAnthony_FT, DwightHoward_FT, ChrisBosh_FT, LeBronJames_FT, ChrisPaul_FT, DerrickRose_FT,     DwayneWade_FT, KevinDurant_FT)
       
       4.Rename the columns
       colnames(FreeThrows) <- Seasons
       
       5.Rename the rows
       rownames(FreeThrows) <- Players

       6.Check the matrix
       FreeThrows

       7.Free Trows Attempts
       KobeBryant_FTA <- c(819,768,742,564,541,583,451,626,21,241)
       JoeJohnson_FTA <- c(330,314,379,362,269,243,186,161,195,176)
       LeBronJames_FTA <- c(814,701,771,762,773,663,502,535,585,528)
       CarmeloAnthony_FTA <- c(709,568,590,468,612,605,367,512,541,237)
       DwightHoward_FTA <- c(598,666,897,849,816,916,572,721,638,271)
       ChrisBosh_FTA <- c(581,590,559,617,590,471,279,302,272,232)
       ChrisPaul_FTA <- c(465,357,390,524,190,384,302,323,345,321)
       KevinDurant_FTA <- c(256,256,448,524,840,675,501,750,805,171)
       DerrickRose_FTA <- c(205,205,205,250,338,555,239,0,32,187)
       DwayneWade_FTA <- c(803,535,467,771,702,652,297,425,258,370)
       
       8.Matrix for Free Throw Attempts
       
       9.Bind the given vectors to form the matrix
       FreeThrowAttempts <- rbind(KobeBryant_FTA, JoeJohnson_FTA, LeBronJames_FTA, CarmeloAnthony_FTA, DwightHoward_FTA, ChrisBosh_FTA,       ChrisPaul_FTA, KevinDurant_FTA, DerrickRose_FTA, DwayneWade_FTA)
       
       10.Remove vectors - we don't need them anymore
       rm(KobeBryant_FTA, JoeJohnson_FTA, CarmeloAnthony_FTA, DwightHoward_FTA, ChrisBosh_FTA, LeBronJames_FTA, ChrisPaul_FTA,                     DerrickRose_FTA, DwayneWade_FTA, KevinDurant_FTA)
       
       11.Rename the columns
       colnames(FreeThrowAttempts) <- Seasons
       
       12.Rename the rows
       rownames(FreeThrowAttempts) <- Players

       13.Check the matrix
       FreeThrowAttempts

       14.Re-create the plotting function
       myplot <- function(z, who=1:10) {
        matplot(t(z[who,,drop=F]), type="b", pch=15:18, col=c(1:4,6), main="Basketball Players Analysis")
        legend("bottomleft", inset=0.01, legend=Players[who], col=c(1:4,6), pch=15:18, horiz=F)
       }

       15.Visualize the new matrices
       myplot(FreeThrows)
       myplot(FreeThrowAttempts)

       #Part 1 - Free Throw Attempts Per Game 
       #(You will need the Games matrix)
       myplot(FreeThrowAttempts/Games)

       #Part 2 - Free Throw Accuracy
       myplot(FreeThrows/FreeThrowAttempts)

       16.Field Goal Accuracy was exceptional:
       myplot(FieldGoals/FieldGoalAttempts)


       #Part 3 - Player Style Patterns Excluding Free Throws
       myplot((FieldGoals-FreeTrows)/Points)
```
### &nbsp;&nbsp;Practice 5.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       1.Filter countries by Low income
       2.Filter countries by Lower middle income
       3.Filter countries by Upper middle income
       4.Filter by countrie Malta
       5.Filter by countrie Qatar
       6.Filter by countrie Netherlands
       7.Filter by countrie Norway

#### &nbsp;&nbsp;&nbsp;&nbsp; Code.

       1.Filter countries by Low income
       filter <- stats$Income.Group == "Low income"
       stats[filter,]
       
       2.Filter countries by Lower middle income
       filter <- stats$Income.Group == "Lower middle income"
       stats[filter,]
       
       3.Filter countries by Upper middle income
       stats[stats$Country.Name == "Upper middle income",]
       
       4.Filter by countrie Malta
       stats[stats$Country.Name == "Malta",]
       
       5.Filter by countrie Qatar
       stats[stats$Country.Name == "Qatar",]
       
       6.Filter by countrie Netherlands
       stats[stats$Country.Name == "Netherlands",]
       
       7.Filter by countrie Norway
       stats[stats$Country.Name == "Norway",]




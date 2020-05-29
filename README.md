# Mineria_de_Datos
Class Session
![Mineriade Datos](https://cdn.windowsreport.com/wp-content/uploads/2018/07/data-mining.png)


# Big-Data  

### <p align="center" > TECNOLÓGICO NACIONAL DE MÉXICO INSTITUTO TECNOLÓGICO DE TIJUANA SUBDIRECCIÓN ACADÉMICA DEPARTAMENTO DE SISTEMAS Y COMPUTACIÓN PERIODO: Enero - Junio 2020 </p>

###  <p align="center">  Carrera: Ing. En Sistemas Computacionales. Materia: 	Datos Masivos (BDD-1704 IF9A	).</p>

### <p align="center">  Maestro: Jose Christian Romero Hernandez	</p>
### <p align="center">  No. de control y nombre del alumno:  </p>
### <p align="center">  No. de control y nombre del alumno:16210585 - Valenzuela Rosales Marco Asael </p>


# Unit 1

## Index
&nbsp;&nbsp;&nbsp;[Practice 1](#practice-1)  
&nbsp;&nbsp;&nbsp;[Practice 2](#practice-2)  
&nbsp;&nbsp;&nbsp;[Practice 3](#practice-3)  
&nbsp;&nbsp;&nbsp;[Practice 4](#Practice-4)  
&nbsp;&nbsp;&nbsp;[Practice 5](#practice-5)  


### &nbsp;&nbsp;Practice 1.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
       1.Test the Law of Large Number for N random normally distributed numbers with mean = 0, stdev = 1
       2.Create an R script that will count how many of these numbers fall between -1 and 1 and divide by 
       the total quantity of N
       3.Theoretical E(X) = 68.2%
       4.Find out N that could result E(X) to be = 68.2%
       
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
```
    expX <- 0
    n <- 0
      numInRange <- 0
      # rounding expX to 4 decimal place
    while (round(expX, 4) != 0.6820) { # Create a while loop to stop when E(X) is 68.2%
     n <- n + 1 # Counting total number generated
     value <- rnorm(1) # Generate new random number
    if (value >= -1 & value <= 1) { # check if within range
    numInRange <- numInRange + 1 # if within range, increment count 
     }
     expX <- numInRange / n # Calculate expected X
      display <- paste("Current expected X : ", expX)
      print(display) # Print out current expected X while computing
      }

    # print out the n needed to reached 68.2
    print(n)
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

#### &nbsp;&nbsp;Exam.

#### &nbsp;&nbsp;&nbsp;&nbsp; Instructions.
Develop the following problem with R and RStudio for the knowledge extraction that the problem requires

    The World Bank was very impressed with your delivery on the previous assignment and have a new project for you.

    You must generate a scatter-plot that shows the life expectancy statistics (Y-axis) and fertility rate (X-axis) by country (Country).

    The scatterplot should also be classified by country (Country Regions).

    You have been provided with data for 2 years: 1960 and 2013 and are required to produce a visualization for each of these years.

    Some data has been provided in a CVS file, some in R vectors. The CVS file contains combined data for both years. All data manipulation must be done in R (not in Excel) because this project can be audited at a later stage.

    You have also been asked to provide information on how the two periods compare.
    
 
#### &nbsp;&nbsp;&nbsp;&nbsp; Code.
       #Execute below code to generate three new vectors
       Country_Code <- c("ABW","AFG","AGO","ALB","ARE","ARG","ARM","ATG","AUS","AUT","AZE","BDI","BEL","BEN","BFA","BGD","BGR","BHR","BHS","BIH","BLR","BLZ","BOL","BRA","BRB","BRN","BTN","BWA","CAF","CAN","CHE","CHL","CHN","CIV","CMR","COG","COL","COM","CPV","CRI","CUB","CYP","CZE","DEU","DJI","DNK","DOM","DZA","ECU","EGY","ERI","ESP","EST","ETH","FIN","FJI","FRA","FSM","GAB","GBR","GEO","GHA","GIN","GMB","GNB","GNQ","GRC","GRD","GTM","GUM","GUY","HKG","HND","HRV","HTI","HUN","IDN","IND","IRL","IRN","IRQ","ISL","ITA","JAM","JOR","JPN","KAZ","KEN","KGZ","KHM","KIR","KOR","KWT","LAO","LBN","LBR","LBY","LCA","LKA","LSO","LTU","LUX","LVA","MAC","MAR","MDA","MDG","MDV","MEX","MKD","MLI","MLT","MMR","MNE","MNG","MOZ","MRT","MUS","MWI","MYS","NAM","NCL","NER","NGA","NIC","NLD","NOR","NPL","NZL","OMN","PAK","PAN","PER","PHL","PNG","POL","PRI","PRT","PRY","PYF","QAT","ROU","RUS","RWA","SAU","SDN","SEN","SGP","SLB","SLE","SLV","SOM","SSD","STP","SUR","SVK","SVN","SWE","SWZ","SYR","TCD","TGO","THA","TJK","TKM","TLS","TON","TTO","TUN","TUR","TZA","UGA","UKR","URY","USA","UZB","VCT","VEN","VIR","VNM","VUT","WSM","YEM","ZAF","COD","ZMB","ZWE")
       Life_Expectancy_At_Birth_1960 <- c(65.5693658536586,32.328512195122,32.9848292682927,62.2543658536585,52.2432195121951,65.2155365853659,65.8634634146342,61.7827317073171,70.8170731707317,68.5856097560976,60.836243902439,41.2360487804878,69.7019512195122,37.2782682926829,34.4779024390244,45.8293170731707,69.2475609756098,52.0893658536585,62.7290487804878,60.2762195121951,67.7080975609756,59.9613658536585,42.1183170731707,54.2054634146342,60.7380487804878,62.5003658536585,32.3593658536585,50.5477317073171,36.4826341463415,71.1331707317073,71.3134146341463,57.4582926829268,43.4658048780488,36.8724146341463,41.523756097561,48.5816341463415,56.716756097561,41.4424390243903,48.8564146341463,60.5761951219512,63.9046585365854,69.5939268292683,70.3487804878049,69.3129512195122,44.0212682926829,72.1765853658537,51.8452682926829,46.1351219512195,53.215,48.0137073170732,37.3629024390244,69.1092682926829,67.9059756097561,38.4057073170732,68.819756097561,55.9584878048781,69.8682926829268,57.5865853658537,39.5701219512195,71.1268292682927,63.4318536585366,45.8314634146342,34.8863902439024,32.0422195121951,37.8404390243902,36.7330487804878,68.1639024390244,59.8159268292683,45.5316341463415,61.2263414634146,60.2787317073171,66.9997073170732,46.2883170731707,64.6086585365854,42.1000975609756,68.0031707317073,48.6403170731707,41.1719512195122,69.691756097561,44.945512195122,48.0306829268293,73.4286585365854,69.1239024390244,64.1918292682927,52.6852682926829,67.6660975609756,58.3675853658537,46.3624146341463,56.1280731707317,41.2320243902439,49.2159756097561,53.0013170731707,60.3479512195122,43.2044634146342,63.2801219512195,34.7831707317073,42.6411951219512,57.303756097561,59.7471463414634,46.5107073170732,69.8473170731707,68.4463902439024,69.7868292682927,64.6609268292683,48.4466341463415,61.8127804878049,39.9746829268293,37.2686341463415,57.0656341463415,60.6228048780488,28.2116097560976,67.6017804878049,42.7363902439024,63.7056097560976,48.3688048780488,35.0037073170732,43.4830975609756,58.7452195121951,37.7736341463415,59.4753414634146,46.8803902439024,58.6390243902439,35.5150487804878,37.1829512195122,46.9988292682927,73.3926829268293,73.549756097561,35.1708292682927,71.2365853658537,42.6670731707317,45.2904634146342,60.8817073170732,47.6915853658537,57.8119268292683,38.462243902439,67.6804878048781,68.7196097560976,62.8089268292683,63.7937073170732,56.3570487804878,61.2060731707317,65.6424390243903,66.0552926829268,42.2492926829268,45.6662682926829,48.1876341463415,38.206,65.6598292682927,49.3817073170732,30.3315365853659,49.9479268292683,36.9658780487805,31.6767073170732,50.4513658536585,59.6801219512195,69.9759268292683,68.9780487804878,73.0056097560976,44.2337804878049,52.768243902439,38.0161219512195,40.2728292682927,54.6993170731707,56.1535365853659,54.4586829268293,33.7271219512195,61.3645365853659,62.6575853658537,42.009756097561,45.3844146341463,43.6538780487805,43.9835609756098,68.2995365853659,67.8963902439025,69.7707317073171,58.8855365853659,57.7238780487805,59.2851219512195,63.7302195121951,59.0670243902439,46.4874878048781,49.969512195122,34.3638048780488,49.0362926829268,41.0180487804878,45.1098048780488,51.5424634146342)
       Life_Expectancy_At_Birth_2013 <- c(75.3286585365854,60.0282682926829,51.8661707317073,77.537243902439,77.1956341463415,75.9860975609756,74.5613658536585,75.7786585365854,82.1975609756098,80.890243902439,70.6931463414634,56.2516097560976,80.3853658536585,59.3120243902439,58.2406341463415,71.245243902439,74.4658536585366,76.5459512195122,75.0735365853659,76.2769268292683,72.4707317073171,69.9820487804878,67.9134390243903,74.1224390243903,75.3339512195122,78.5466585365854,69.1029268292683,64.3608048780488,49.8798780487805,81.4011219512195,82.7487804878049,81.1979268292683,75.3530243902439,51.2084634146342,55.0418048780488,61.6663902439024,73.8097317073171,62.9321707317073,72.9723658536585,79.2252195121951,79.2563902439025,79.9497804878049,78.2780487804878,81.0439024390244,61.6864634146342,80.3024390243903,73.3199024390244,74.5689512195122,75.648512195122,70.9257804878049,63.1778780487805,82.4268292682927,76.4243902439025,63.4421951219512,80.8317073170732,69.9179268292683,81.9682926829268,68.9733902439024,63.8435853658537,80.9560975609756,74.079512195122,61.1420731707317,58.216487804878,59.9992682926829,54.8384146341464,57.2908292682927,80.6341463414634,73.1935609756098,71.4863902439024,78.872512195122,66.3100243902439,83.8317073170732,72.9428536585366,77.1268292682927,62.4011463414634,75.2682926829268,68.7046097560976,67.6604146341463,81.0439024390244,75.1259756097561,69.4716829268293,83.1170731707317,82.290243902439,73.4689268292683,73.9014146341463,83.3319512195122,70.45,60.9537804878049,70.2024390243902,67.7720487804878,65.7665853658537,81.459756097561,74.462756097561,65.687243902439,80.1288780487805,60.5203902439024,71.6576829268293,74.9127073170732,74.2402926829268,49.3314634146342,74.1634146341464,81.7975609756098,73.9804878048781,80.3391463414634,73.7090487804878,68.811512195122,64.6739024390244,76.6026097560976,76.5326585365854,75.1870487804878,57.5351951219512,80.7463414634146,65.6540975609756,74.7583658536585,69.0618048780488,54.641512195122,62.8027073170732,74.46,61.466,74.567512195122,64.3438780487805,77.1219512195122,60.8281463414634,52.4421463414634,74.514756097561,81.1048780487805,81.4512195121951,69.222,81.4073170731707,76.8410487804878,65.9636829268293,77.4192195121951,74.2838536585366,68.1315609756097,62.4491707317073,76.8487804878049,78.7111951219512,80.3731707317073,72.7991707317073,76.3340731707317,78.4184878048781,74.4634146341463,71.0731707317073,63.3948292682927,74.1776341463415,63.1670487804878,65.878756097561,82.3463414634146,67.7189268292683,50.3631219512195,72.4981463414634,55.0230243902439,55.2209024390244,66.259512195122,70.99,76.2609756097561,80.2780487804878,81.7048780487805,48.9379268292683,74.7157804878049,51.1914878048781,59.1323658536585,74.2469268292683,69.4001707317073,65.4565609756098,67.5223658536585,72.6403414634147,70.3052926829268,73.6463414634147,75.1759512195122,64.2918292682927,57.7676829268293,71.159512195122,76.8361951219512,78.8414634146341,68.2275853658537,72.8108780487805,74.0744146341464,79.6243902439024,75.756487804878,71.669243902439,73.2503902439024,63.583512195122,56.7365853658537,58.2719268292683,59.2373658536585,55.633)

These data are added to create the graph


       #(c) Kirill Eremenko, www.superdatascience.com
       #Abrir archivo 
       stats <- read.csv(file.choose())
       stats
       This way of selecting the file opens the window where the file is, we select it manually and when we select it, we are left loaded in our variable       
       
       library(ggplot2)
       
       

       #Creacion de una varable
       Life1960 <- stats$Year == 1960
       Life1960 <- stats[Life1960,]
       Life1960

       Life2013 <- stats$Year == 2013
       Life2013 <- stats[Life2013 ,]
       Life2013
       
       We created two variables for life in 1960 and in 2013

       dataFrame <- data.frame(Country= Country_Code, Life_Expectancy_1960= Life_Expectancy_At_Birth_1960,
                               Life_Expectancy_2013= Life_Expectancy_At_Birth_2013)
       dataFrame
       
       We create a new Dataframe



       merged_60 <- merge(Life1960, dataFrame, by.x = "Country.Code", by.y = "Country")
       merged_60
       merged_2013 <- merge(Life2013, dataFrame, by.x = "Country.Code", by.y = "Country")
       merged_2013
       We use the merge function to join two data frames by common columns or row names, or do other versions of database join operations
       
       
       qplot(data = merged_60, x = Fertility.Rate, y = Life_Expectancy_1960, 
              size=I(3),color = Region,shape=I(19), alpha =I(0.9))


       qplot(data = merged_2013, x = Fertility.Rate, y = Life_Expectancy_2013,
              size=I(3),color = Region,shape=I(19), alpha =I(0.9))

       We use the qplot function to make our graph using our merged modifying the size, the color of the region, to see how transparent the figures of the graph appear respectively in the years of 1960 and 2013
       
       
       It can be seen that in the two graphs both in the year of 1960 and 2013 Europe has a greater
       Life expectancy is longer but fertility rate is low, in others
       continents what is africa remains in 1960 and 2013
       between 50 and 60 but with a fertility rate range of 5 to 8
       

Class Session ![R Studio]https://github.com/ivanatorresf/Data_Mining/blob/unidad_1/Exxam1.png

Class Session ![R Studio]https://github.com/ivanatorresf/Data_Mining/blob/unidad_1/exam1.1.png



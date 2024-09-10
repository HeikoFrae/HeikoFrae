# Day 11 09.09.2024
Protocol writer: Emma

## __Schedule__ 

|Time|Notes|
|---|---|
|09:00 - 9:30| Daily review|
|9:30 - 12:30|Introduction to Pandas dataframe and EAD|
|12:30 - 13:30|Lunch Break| 
|13:30 - 17:00|Notebooks and exercises on Dataframes|   
|17:00 - 17:30|Corrections and Questions| 

---

## __Daily Review__ 

* Exchanges about CV and LMS training
* Talks about the challenges of learning Python, and how to work with new AI tools

## __Pandas Dataframes__ 

* Panda mean Panel Data
* It is an object that holds data and allow us to interact with the data
* [Official Documentation of Pandas](https://pandas.pydata.org/docs/user_guide/index.html)

## __Explorative Data Analysis__ 

* This is the first step when we open the dataset. The aim is to :
  + Discover patterns
  + Spot anomalies
  + Test our hypothesis
  + Check assumptions
* With EDA we explore and clean the dataset

## __Selecting and working with rows and columns__ 

With panda we can :
  * select a single column
  * select multiple columns
  * change a column type
  * add and create new columns
  * remove columns

There is two methods to select specific rows.
* .loc[] is **label based**, it operates on the columns and rows names. It is often used when oerations are based on the data's content rather than its position within the dataframe
* .iloc[] is **integrer based**, the selection is based on integrer indices. It is zero bases index, and we can can access rows froom the end of the dataframe using negative index

## __Filtering dataset__ 

Filtering allows to extract subset of dataset based on specific conditions or criteria. 
Those can be : 
  * greater or smaller than a value
  * using the boolean types : & **and** , | **or** , ~ **not**
  * the *.isin* method for integrer or float types
  * the *.str.contains* method for string types
  * the *.between* method

## __Discussions about the notebooks and exercises__ 

* Difference between a serie and a Dataframe ?
    + A serie contains only one column of observations, a dataframe contains a minimum of two columns

* if you are selecting more than one column than you have to use double square brackets as it is a dataframe and not a serie
* be careful with .between, according to the language it can be inclusive or exclusive of the conditional values. The default settings of .between can be edited
  




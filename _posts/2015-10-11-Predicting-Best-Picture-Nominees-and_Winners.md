---
layout: post
title: Predicting Best Picture Nominees and Winners
---

![2015 Best Picture Nominees](https://github.com/sosier/sosier.github.io/blob/master/images/best_picture_nominees.jpg?raw=true "2015 Best Picture Nominees")  

###Background:  
- **The Academy Awards** or **The Oscars** are an annual American awards ceremony honoring cinematic achievements in the film industry
- Awards are given in various categories, with probably the most prestigious being the award for **Best Picture**
- Given its **prestige**, Best Picture nominations and awards provide **tremendous exposure**
- A Best Picture nomination alone has been estimated to [**increase box office revenue by ~$6.9 million**](http://www.bloomberg.com/bw/articles/2013-01-10/how-oscar-nominations-affect-the-box-office)

####*So, given some data about movies, can we predict which ones will receive Best Picture nominations, and which of these will win?*

###Findings:  
 1. **Short Answer:** No  

 2. **Long Answer:** No, not really  
   - My best model is **98% accurate** at predicting Best Picture winner / nominee status  
   - **BUT…** does so by saying **no movies are ever nominated** (much less picking a winner) yielding a **0% true positive rate**  
   - Essentially, there are SO MANY more movies that are not nominated than are that the model can not be forced to actually make predictions without severe overfitting to the data
 
 3. Nevertheless, I was able to identify some factors which are **strong predictors of Best Picture nomination success**. In order of predictive power these are:  

   1. **Director(s)** - Directors with a history of consistently directing Best Picture nominees (e.g. Martin Scorsese) strongly improve a movie's odds  

   2. **Stars (Leading actors / actresses)** - Similarly, stars with a history of strong Oscar level performances (e.g. Jack Nicholson) also strongly improve a movie's chances  

   3. **Writer(s)** - The same holds true for writers  

   4. **Genre** - Westerns, bio-pics, war movies, and romances are more likely to be nominated, whereas animated movies are less likely

   5. **Country** - Foreign (non-US) movies are disadvantaged  

   6. **Language** - Similarly, foreign language movies are also disadvantaged  

   7. **Critical Opinion** - Critical reception is important only a gatekeeper punishing poorly rated movies, but once a movie passes a certain threshold and is deemed "good enough" more positive critical reception has very little effect  

   8. **Public Opinion** - The same holds true for reception by the general public  

   9. **Number of Nominees in Year** - Obviously, if a movie is competing since 2009 when the number of nominees was increased, it stands a slightly higher chance of being nominated  

   10. **Month of Release** - Movies released late in the year also have a very slight advantage  

###Report:  
<iframe src="https://drive.google.com/a/seanosier.com/file/d/0B90v2XyX9nIAUVlyWmpxbkdEUUU/preview" width="640" height="480"></iframe>

###Data:  
 - [IMDB](http://www.imdb.com/)  
 - [Wikipedia](https://en.wikipedia.org/wiki/Academy_Award_for_Best_Picture)  
 - [Google Search Results](https://www.google.com/#q=list%20of%20top%20directors)  

###Technologies:  
 - Python  
 - BeautifulSoup  
 - Selenium  
 - Pickle  
 - Pandas  
 - Statsmodels  
 - scikit-learn  
 - MATLAB  
 - UNIX  
 - Github  
 - Excel  
 - Powerpoint  

###Methodolgy:  
 1. Scrape and clean IMDB list of movies by year for 1990 - 2014 (~120k movies)  
 2. Scrape Wikipedia for list of all Best Picture nominees and winners, clean this data, and merge with the above  
 3. Scrape individual IMDB movie pages for detailed data on each movie, clean this data, and merge with the above  
 4. Scrape Google search results for list list of frequently mentioned directors, actors, etc. to use as boolean variables for each movie  
 5. Convert categorical variables to boolean variable(s)  
 6. Process Best Picture status to be our dependent variable (Win = 10 points, Nominated = 5 points, Not-Nominated = 0 points)  
 7. Split data into a training and testing set
 8. Oversample Best Picture nominees and winners slightly so that they're a slightly larger portion of our training set  
 7. Regress Best Picture status vs. all features in our data set, examine outputs, and compare predictions to actual outcomes in our test data 
 8. Use backward elimination and stepwise regression to arrive at best possible model  

###Code:  
For more details checkout my [Github repository](https://github.com/sosier/Predicting_Best_Picture_Winners_Nominees).

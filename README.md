# CS 301-102 Group 7
Group Members: Gabriela Banayotti, Abakir Hanna, Edel Barcenas

# Company Name: Sports Center INC
Company Mission: Sports Center INC gives you all the relevent information you need around your favorite sport.


## Proposal: 
Competition:https://www.kaggle.com/competitions/mens-march-mania-2022
## What is the problem that you will be investigating? Why is it interesting?
It is that time of the year where everyone is watching college basketball and the madness behind it. Fanatics use this time to put their bracketology knowledge to the test. When making our brackets, instead of using current records, quality of wins/losses and probabilty of upsets, we will be utilizing a sequence of effective historical data and computing power. 

## What reading will you examine to provide context and background?
We will read more about what the data means that we are provided.https://www.kaggle.com/competitions/mens-march-mania-2022/data
[link text](https://www.analyticsvidhya.com/blog/2021/09/gradient-boosting-algorithm-a-complete-guide-for-beginners/)\n
[link text](https://towardsdatascience.com/understanding-gradient-boosting-machines-9be756fe76ab)
[link text](https://ieeexplore.ieee.org/document/9671688)

## What data will you use? If you are collecting new data, how will you do it?
We will use the data from Kaggle https://www.kaggle.com/competitions/mens-march-mania-2022/data. We will pick the features from the csv files that we find important and go from there. The only new data we will collect will be this year’s tournament results and see how we do compared to them.

## What method or algorithm are you proposing? If there are existing implementations, will you use them and how? How do you plan to improve or modify such implementations? You don’t have to have an exact answer at this point, but you should have a general sense of how you will approach the problem you are working on.

Due to the bracketed nature of the basketball tournament, it makes perfect sense to use random forests to generate predictions. A teams seed can be used to predict chance of winning initially, but as upsets occur the seed unofficial seed ranking will change. Ada Boositing can be used to retroactively adjust the weights of losses. As we look more into the data provided we might use another method to more accurately train our model and use JAX.

## How will you evaluate your results? Qualitatively, what kind of results do you expect (e.g. plots or figures)? Quantitatively, what kind of analysis will you use to evaluate and/or compare your results (e.g. what performance metrics or statistical tests)?
Our prediction will be scored on the log loss:

![image](https://user-images.githubusercontent.com/30082380/160319767-1ab5d44d-fef8-4f6c-aefa-81d1d52149e1.png)

where
- n  is the number of games played
- yi is the predicted probability of team 1 beating team 2
- yi  is 1 if team 1 wins, 0 if team 2 wins
- Log is the natural logarithm

The use of the logarithm provides extreme punishments for being both confident and wrong. In the worst possible case, a prediction that something is true when it is actually false will add an infinite amount to your error score. In order to prevent this, predictions are bounded away from the extremes by a small value.

We also might plot some diagrams to show how likely will things happen such as a low seeded team beating a high seeded team. Then use that data to help train our model more.

I expect to get results that are between 0.50 and .80 percent accuracy for when we train our model, because even though statistically a team is supposed to win does not mean they do. We will use the results of past tournaments and see how accurately we can predict them before we try to predict this year’s tournament. The higher we score we will know we picked the right results. If we are able to completely predict a tournament outcome would be an amazing sight to see.

# CS 301-102 Group 7
Group Members: Gabriela Banayotti, Abakir Hanna, Edel Barcenas

# Company Name: Sports Center INC
Company Mission: Sports Center INC gives you all the relevent information you need around your favorite sport.


## Proposal: 
Competition:https://www.kaggle.com/competitions/mens-march-mania-2022
## What is the problem that you will be investigating? Why is it interesting?
It is that time of the year where everyone is watching college basketball and the madness behind it. Fanatics use this time to put their bracketology knowledge to the test. When making our brackets, instead of using current records, quality of wins/losses and probabilty of upsets, we will be utilizing a sequence of effective historical data and computing power. 

## What reading will you examine to provide context and background?

## What data will you use? If you are collecting new data, how will you do it?

## What method or algorithm are you proposing? If there are existing implementations, will you use them and how? How do you plan to improve or modify such implementations? You don’t have to have an exact answer at this point, but you should have a general sense of how you will approach the problem you are working on.

Due to the bracketed nature of the basketball tournament, it makes perfect sense to use random forests to generate predictions. A teams seed can be used to predict chance of winning initially, but as upsets occur the seed unofficial seed ranking will change. Ada Boositing can be used to retroactively adjust the weights of losses.

## How will you evaluate your results? Qualitatively, what kind of results do you expect (e.g. plots or figures)? Quantitatively, what kind of analysis will you use to evaluate and/or compare your results (e.g. what performance metrics or statistical tests)?
We will evaluate our results using the Root-Mean-Squared-Error (RMSE) between the logarithm of the predicted value and the logarithm of the observed sales price. 
If results are graphed with stage of the tournament on the x axis and percentage of correct guesses on the y axis, we can expect the result to reflect a positive trend; whether it is curved or is constant is to be determined. We can make this assumption because most upsets occur early in the tournament and the algorithm will also have a the least amount of tournament specific data to work with.  

![image](https://user-images.githubusercontent.com/30082380/160297360-fe75a72d-7c95-413f-b0c6-e32c44aeb516.png)

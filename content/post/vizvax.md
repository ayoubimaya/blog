---
title: "Visualizing the Vaccine"
tags: ["analysis"]
date: 2021-03-04
draft: false
---

As I am writing this, it’s been a few months since the initial vaccinations have taken place and I find myself Googling COVID-19 related news more than ever. Some of my questions have been:

<center> "What types of vaccines are used?"

"What country is vaccinating the most?" 

"How fast is the US vaccinating?" 

"What state is vaccinating the most?"

"When will I be eligible for a vaccine?" </center>


Needless to say, I wanted all the information I could get my hands on. Fortunately, there are datasets that can answer my questions. The data was used comes from Our World in Data’s [GitHub repository](https://github.com/owid/covid-19-data), [Kaggle](https://www.kaggle.com/gpreda/covid-world-vaccination-progress/), and a dataset that can be found on my [Visualizing the Vaccine repository](https://github.com/ayoubimaya/COVID19-Vaccination-Progress/blob/main/datasets/State_Postal_Codes.csv).Let’s get started!

## <center>What countries are using mRNA, non-mRNA, or both?</center>

<iframe width="800" height="700" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/1.embed"></iframe>

We see some interesting geopolitics happening here. Most of the Global South uses non-mRNA vaccines, while most of the Global North uses mRNA vaccines. Of course, we see that we have some Global North countries in Europe for example, who use both mRNA and non-mRNA vaccines.

## <center>What countries are vaccinating the fastest?</center>

Next, I wanted to look at the top countries with the most vaccinations per hundred. I wanted to filter on populations greater than 10 million, to compare the United States with other larger countries. 

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/4.embed"></iframe>

In this order, Great Britain, United States, Chile, Turkey, Morocco, Poland, Greece, Portugal, Spain, and Romania. We see that Great Britain is in the lead with 30% of vaccinations, the United States at 20%, Chile at 18% and all other countries with <= 10% vaccinations.

## <center>How do these countries look over time?</center>

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/6.embed"></iframe>

Looking at countries like Great Britain and Chile, we see they started off with an upward trend, but have more recently seen dramatic dips. The United States, on the other hand, experienced a slight dip in daily vaccinations in mid February, but more recently has seen an upward trend.

## <center>How well are the states doing in vaccinating?</center>

<iframe width="900" height="700" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/8.embed"></iframe>

As far as total vaccinations per hundred is concerned, states like Alaska, New Mexico, North Dakota, and South Dakota are the leaders. My initial hypothesis that states with higher density of people vaccinate more proved to be false. Apparently, states with spread out, smaller populations perform better.

## <center>What are the United States total vaccinationss over time?</center>

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/10.embed"></iframe>

Looks like we have some great news! Overall, the United States total vaccinations has increased exponentially.

## <center>Will we reach 150 million vaccinations in 100 days?</center>

On January 25, 2021, President Joe Biden pledged 150 million vaccinations in 100 days. Let's see what the data can tell us!

For this prediction, I used Prophet from FBProphet since the docs say it handles seasonality and missing data really well. Another reason I used Prophet is because it allows you to choose between two modes of predictions; linear and logistic. Logistic is used when you have a known cap for your prediction and in our case, we know that the number of vaccinations cannot exceed the population of the United States. 

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/12.embed"></iframe>

According to Prophet, by April 30, we expect around 220 million vaccinations, meaning shots in arms. It looks like Joe Biden’s prediction may be a little conservative! 

Although time may seem to be moving slow, we are well on our way to vaccinating the population. If you’ve made it this far in this blog post, I hope you are able to walk away with a much more positive outlook on what the future has in store!



My Jupyter Notebook with these plots can be found [here](https://bit.ly/vizvax2021).

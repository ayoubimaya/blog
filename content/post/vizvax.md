---
title: "Visualizing the Vaccine"
tags: ["analysis"]
date: 2021-03-04
draft: true
---

As I am writing this, it’s been a few months since the initial vaccinations have taken place and I find myself Googling COVID-19 related news more than ever. Some of my questions have been:

<center> "What types of vaccines are used?"

"What country is vaccinating the most?" 

"How fast is the US vaccinating?" 

"What state is vaccinating the most?"

"When will I be eligible for a vaccine?" </center>


Needless to say, I wanted all the information I could get my hands on. Fortunately, there are datasets that can answer my questions. The data used comes from Our World in Data’s [GitHub repository](https://github.com/owid/covid-19-data), Kaggle's [COVID-19 World Vaccination Progress](https://www.kaggle.com/gpreda/covid-world-vaccination-progress/) dataset, Kaggle's [Countries of the World](https://www.kaggle.com/erikbruin/countries-of-the-world-iso-codes-and-population) dataset, and a simple dataset I put together that can be found [here](https://github.com/ayoubimaya/COVID19-Vaccination-Progress/blob/main/datasets/State_Postal_Codes.csv). Let’s get started!

## <center>What countries are using mRNA, non-mRNA, or both?</center>

<iframe width="800" height="700" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/1.embed"></iframe>

We see some interesting geopolitics happening here. Most of the Global South uses non-mRNA vaccines, while most of the Global North uses mRNA vaccines. Of course, we see that we have some Global North countries in Europe for example, who use both mRNA and non-mRNA vaccines.

## <center>What countries are vaccinating the fastest?</center>

Next, I wanted to look at the top countries with the most vaccinations per hundred. To compare the United States with other larger countries, I filtered by countries with populations 10 million or greater. 

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/4.embed"></iframe>

In this order, Great Britain, United States, Chile, Turkey, Morocco, Poland, Greece, Portugal, Spain, and Romania. We see that Great Britain is in the lead with 30% of vaccinations, the United States at 20%, Chile at 18% and all other countries with <= 10% vaccinations.

## <center>How do these countries look over time?</center>

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/6.embed"></iframe>

Looking at countries like Great Britain and Chile, we see an initial upward trend, but have more recently seen dramatic dips. The United States, on the other hand, experienced a slight dip in daily vaccinations in mid February, but more recently has seen an upward trend.

## <center>How well are the states doing in vaccinating?</center>

<iframe width="900" height="700" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/8.embed"></iframe>

As far as total vaccinations per hundred is concerned, states like Alaska, New Mexico, North Dakota, and South Dakota are the leaders. My initial hypothesis that states with higher density of people would be able to vaccinate faster was proven wrong. Apparently, states where people are spread out perform better.

## <center>What are the United States total vaccinationss over time?</center>

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/10.embed"></iframe>

Good news, everyone! Overall, the United States total vaccinations has increased exponentially.

## <center>Will we reach 150 million vaccinations in 100 days?</center>

On January 25, 2021, President Joe Biden pledged 150 million vaccinations in 100 days. Let's see what the data can tell us!

For predicting future vaccination numbers, I used an open source software, called [Prophet](https://facebook.github.io/prophet/). According to Prophet's docs, this forecasting prodecure handles seasonality and outlier really well without the hassle of too much tuning. Another reason to use Prophet is because it allows you to make forecasts using a logistic growth trend model with a specified carrying capacity. For our case, our carrying capacity is the population of the United States. 

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/12.embed"></iframe>

According to Prophet, by April 30, we expect around 220 million vaccinations, meaning shots in arms. It looks like President Joe Biden’s prediction may be a little conservative! 

Although time may seem to be moving slow, we are well on our way to vaccinating the population. If you’ve made it this far in this blog post, I hope you are able to walk away with a much more positive outlook on what the future has in store!



My Jupyter Notebook with these plots can be found [here](https://bit.ly/vizvax2021).
My talk on Visualizing the Vaccine can be found [here](https://bit.ly/vizvaxvid).
https://www.kaggle.com/erikbruin/countries-of-the-world-iso-codes-and-population

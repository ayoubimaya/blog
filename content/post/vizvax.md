---
title: "Visualizing the Vaccine"
tags: ["analysis"]
date: 2021-03-05
draft: false
---

Hello March, it’s been a few months since the first vaccinations took place and I find myself Googling about COVID-19 more than ever. Some questions I had:

<center> "What types of vaccines are used?"

"What country is vaccinating the most?"

"How fast is the US vaccinating?"

"What state is vaccinating the most?"

"When will I be eligible for a vaccine?" </center>


I wanted all the information I could get my hands on. Fortunately, there are datasets that answer my questions. The data comes from Our World in Data’s [GitHub repository](https://github.com/owid/covid-19-data), Kaggle's [COVID-19 World Vaccination Progress](https://www.kaggle.com/gpreda/covid-world-vaccination-progress/) dataset, Kaggle's [Countries of the World](https://www.kaggle.com/erikbruin/countries-of-the-world-iso-codes-and-population) dataset, and a state postal codes [dataset](https://github.com/ayoubimaya/COVID19-Vaccination-Progress/blob/main/datasets/State_Postal_Codes.csv). Let’s get started!

## <center>What countries are using mRNA, non-mRNA, or both?</center>

To see the different types of vaccines countries use, a stacked bar plot from [Matplotlib](https://matplotlib.org/) or [Seaborn](https://seaborn.pydata.org/#) work, but I wanted something a little more “worldly”. Instead I used [Plotly Express](https://plotly.com/python/plotly-express/) to generate a [Choropleth Map](https://plotly.com/python/choropleth-maps/). Making choropleth maps requires two main types of input:

1. Geometry information

	* I used plotly built-in geometry for world countries.

2. A list of values indexed by feature identifier.


<iframe width="800" height="700" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/1.embed"></iframe>

There’s some interesting geopolitics happening here. Most of the Global South use non-mRNA vaccines, while most of the Global North use mRNA vaccines. Of course, we see some Global North countries in Europe use both types of vaccines.

## <center>What countries are vaccinating the fastest?</center>

Next, I wanted to look at the top 10 countries with highest vaccinations per hundred. To compare the United States with other larger countries, I filtered by countries with populations >= 10 million. A [Plotly Express Bar Chart](https://plotly.com/python/bar-charts/) works great here. 

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/4.embed"></iframe>

In this order, Great Britain, United States, Chile, Turkey, Morocco, Poland, Greece, Portugal, Spain, and Romania. Great Britain leads with 30% of vaccinations, the United States at 20%, Chile at 18% and all other countries with <= 10% vaccinations.

## <center>How do these countries look over time?</center>

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/6.embed"></iframe>

A standard [Plotly Express Line Plot](https://plotly.com/python/line-charts/) shows that Great Britain and Chile started with an upward trend, but recently saw dramatic dips. The United States experienced a slight dip in daily vaccinations in mid-February, but now trends upwards.

## <center>How well are the states doing in vaccinating?</center>

<iframe width="900" height="700" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/8.embed"></iframe>

For this plot, I used another Plotly Express Choropleth map, but this time with Plotly’s built-in geometry for states.

Alaska, New Mexico, North Dakota, and South Dakota are the leading in total vaccinations per hundred. I initially thought states with higher density of people would vaccinate faster, but the data proved me wrong.

## <center>What are the United States total vaccinations over time?</center>

<iframe width="900" height="600" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/10.embed"></iframe>

Good news, everyone! Over time, the United States total vaccinations has increased exponentially.

## <center>Will we reach 150 million vaccinations in 100 days?</center>

On January 25, 2021, President Joe Biden pledged 150 million vaccinations (shots in arms) in 100 days. Let's see what the data can tell us!

For predicting future vaccination numbers, I used open source software, called [Prophet](https://facebook.github.io/prophet/). According to Prophet, this forecasting procedure handles seasonality and outliers well without too much tuning. Prophet also lets you make forecasts using a logistic growth trend model with a specified carrying capacity. Our carrying capacity is the population of the United States.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~mayoubi/12.embed"></iframe>

Prophet’s model says by April 30, 2021 around 220 million vaccinations will have happened. It looks like President Joe Biden’s prediction is a little conservative!

I know that it feels like a lifetime, but we are on our way to getting those shots to folks. I hope you will have a more positive outlook on what the future has in store! If you like what you've read, be sure to check out my talk on [“Visualizing the Vaccine”](https://bit.ly/vizvaxvid) and its corresponding [Jupyter Notebook](https://bit.ly/vizvax2021).



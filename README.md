# Project-1

##Crerate a README.md in your repo with a write-up summarizing your major findings.  This should include a heading for each question you asked of your data and under each heading a short discription of what you found and relevant plots.

# ***SIP: We are the ...Simple.Investment.People.***

![SIP LOGO](images/SIP_logo.png)


## **Overview**
---

### ***Summary***

SIP is a tool that is designed to solve business problems rooted in the fintech subsegemnt of digital investment advisory. Our goal is to democratize access to tools that assist investors with diverse investment acumen.  From novices to more experienced individuals, SIP tool will help simply and automate risk assessment and value projections. 

For our project, we set out to solve the following quesitons:

* Who is our target user?

* How can we help everyday investors make smart investment decisions? 

* How can we help investors assess risk associated with certian invsetments in relation to the overall market?

* How can we help investors predict the future value of their investment positions from a growth perspective? 


### **Question 1:** 
---
### ***Who is the target user?***
When we created the SIP tool we wanted to make sure we made a tool that leveled the playing field and provide smart insights for novice, intermeidate and advanced investors alike. 



### **Question 2:**  
---
### ***How can we help everyday investors make smart investment decisions.***    
  
For users weho are new to investing, we create value by delivering insights just by the user selecting the ticker of an investment.  The software will automatically run the risk analysis and value projections so the individual has actionable information to make an investment decision.  The results are provided in an visual manner making it easier to see differences between investment options. By focusing on risk and porjected growth

We help everyday investors make smart investment decisions through in two parts.  First, we provide an investment risk anlaysis by automating the calculation of risk ratios on individual stocks , as well as, providing a comparason between investment options indluidng key indexes.   


### **Question 3:** 
---
### ***How can we help a broad range of users assess risk within a subset of investment coices in relation to each other and overall market indexes?*** 

For more experienced investors, the SIP tool enables seasoned users to make decisions faster and analyze insights in a visual manner. Experienced users will be able to better understand  insights and trends over time as well as comparable risk associated with investment choices without perfroming any manual calculations. 


### **Question 4:** 
---
### ***How can we help users predict the futrue value of their investment positions from a growth perspective?***

We addressed this quesiton by running monte carlos simulaiton on the seven stocks we have included in out demo software.  In our analysis we try to give a projection of gorwth by providing 5 year projected trend line into the future after running 500 instances in each simulation.  

# *How We Assess Risk*
---
### ***Our Data*** 

We utilize pythion and pandas library to calculate our risk comparisons.  First we identified data sources for the the following stocks that we used in our analysis:

> + Apple (AAPL)
> + Amazon (AMZN)
> + Facebook (FB)
> + Microsoft (MSFT)
> + Netflix (NFLX)
> + Tesla (TSLA)
> + Walmart (WMT)

Furthermore, we included the following indexes to measure meaure baseline market risk:

> + NASDAQ
> + Dow Jones Indistrial Average (DOWJ)
> + Standard and Poors 500 Index (SPY)


Fist we cleaned and comdinded our data into on dataframe for anaysis.  Below are examples of what the data sets look like prior to analysis:
>  
>![Data Cleanse](images/Cleaning_Merge_DF.png)


Next, we converted our Data to daily percent change (of stock price) to prepare for the risk analysis.

>
>![Daily Percent Change](images/Daily_PCT_Change_DF.png)

We then proceeded to graph and visualize our selected stocks and indexes comulative daily returns.

>***Stocks***
>![Stocks Daily Graph](images/Stocks_Daily.png)

>***Indexes***
>![Index Daily Graph](images/Index_Daily.png)

We then analyzed our date by completing the following analysis:
1. 30 Day [Moving Average][3
]
2. [Beta][2] for each stock in the pool.
3. [Sharpe Ratios][1]

>***Sharpe Ratio Comparison***
>![Sharpe Ratio Comparison](images/Sharpe_Ratio.png)



To present this information in a digestable manner for our users, we proceed to pull this information into panels and created a risk tab within the user dashboard.  This will be discussed a bit later.  


    
[1]:https://www.investopedia.com/terms/s/sharperatio.asp
[2]:https://www.investopedia.com/investing/beta-gauging-price-fluctuations/
[3]:https://www.investopedia.com/terms/m/movingaverage.asp


# *How We Predict Future Value*

### ***Data Sources*** 

​Our second analysis is providing a prediction of future value of our select group of investment options. We utilize the Alpaca Historical Market Infomration through their RESTful API.     

In our analysis we use the following code to call the api and collect the necessary data to run our expirament:

>Monte Carlo Simulation Code
>![Monte Carlo Code](images/Simulation_Setup.png)


We run the simulation with 500 times to predict potential outcomes based on the seed data.  Once the simulation is done we can physically analyze the infomation for each stock by reviewing the following graphs which visually represent the potnetial outcomes of the simulation:

>
>![Output of MC Simulaiton Visualized](images/Simulation_Visuals.png)

Next, we review the key summary of relative data outputs.  

An example is provided below:

>
>![MC Statistical Outputs](images/MC_Stats.png)


We proceed to plot the distribution:

>
>![Distribution Plot](images/Distribution_Plot.png)

This information is then collected and pulled into the dashboard providing the users with actionable insights resperesented in a visual manner.

The user can interact with the graphs to analyze the output at different points in time as well as switch from one investment opiton to another.

>
>![The Interactive MC Panel](images/Prediction_Visual.png)




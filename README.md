# Analyzing-Stock-Market-Values

### INTRODUCTION
This work delves into the specifics of stock market analysis using Spark Streaming, highlighting the project's use of this technology to process and analyze stock data in real time. The project aimed to extract actionable insights from stock price fluctuations and provide a detailed understanding of market dynamics.

### USER GUIDE
Just start the stream. its better to update Pyspark to version 3.5.0.


### TASKS
#### • TASK 1: IDENTIFYING THE MOST VALUABLE STOCKS

This section describes the setup of a Spark session and the creation of a structured streaming DataFrame to ingest live stock price data. It details how the data was grouped by one-hour sliding windows and how the maximum stock price for each stock was calculated and ranked within these windows. The continuous execution of a Spark Streaming query to update the rankings as new data arrived is also explained, providing a dynamic leaderboard of the top 5 most valuable stocks. 

+ Objective: To rank stocks by value within each one-hour window.

+ Method: Utilized a Spark session to create a DataFrame for real-time stock price data. Employed window functions to group data by stock name and onehour intervals.

+ Results: Developed a ranking system using the rank function to list the top 5 stocks by maximum value in each window. Implemented a streaming query to continuously update these rankings.



#### • TASK 2: TRACKING STOCKS THAT LOST VALUE
The second task's methodology is elaborated upon, explaining the custom Spark Streaming query developed to identify stocks that decreased in value between consecutive windows. The first method's use of Spark's window functions for calculating and comparing the last stock price in each window is detailed, while the second method's complexity is acknowledged and reserved for explanation in the Jupyter notebook.

+ Objective: To detect stocks with a decrease in value between consecutive windows.
  
+ Method : Applied window functions to compute the last stock price in each window and compared it with the previous window's last price.
  
+ Results: Created a system to identify and list stocks that lost value, providing a basis for further analysis or action.



#### • TASK 3: FINDING STOCKS THAT GAINED THE MOST
Similar to Task 2, this section outlines the approach to identifying stocks that gained value, with the first method focusing on positive price differences between windows. The ordering of stocks by the magnitude of their gain is described, with
the top performers highlighted. The second method's details are noted to be in the Jupyter notebook, suggesting a potentially different analytical approach or the use of predictive algorithms.

+ Objective: To identify stocks with the most significant gains between windows.
  
+ Method 1: Similar to Task 2, but focused on gains. Calculated positive price differences and ordered stocks by these gains.
  
+ Results: Established a leaderboard of top-performing stocks based on value gains, highlighting potential investment opportunities.



#### • TASK 4: CONTROL CHECK FOR SIGNIFICANT VALUE LOSS
A detailed explanation of the control mechanism implemented to monitor and flag significant drops in stock prices over a five-hour window is provided. The mechanism's design to calculate the percentage drop and flag any stocks exceeding a 10% loss is discussed, emphasizing its importance for automated trading systems and quick response to market changes.

+ Objective: To implement a control that flags significant value drops in stock prices.
  
+ Method: Set up a control mechanism to calculate the percentage drop in stock prices within a five-hour window and flag stocks with over a 10% loss.

+ Results: Provided a critical alert system for significant value drops, aiding in risk management and decision-making processes.



#### • TASK 5: ASSET CHANGES WITH THE FLUCTUATION OF THE MARKET.
In this task, i analyze how the value of owned stocks changes with market fluctuations over time using Spark Streaming.

+ Objective: To calculate the fluctuation in the value of owned stocks over a 5-hour window.

+ Method: Defined the stocks owned and their quantities in a DataFrame. Joined the real-time streaming stock data with the owned stocks DataFrame on the stock name. Calculated the asset value by multiplying the current stock price with the amount owned. Applied a window function to group data by stock name and a 5-hour interval to observe the value fluctuation over time.

+ Results: Set up a streaming query to continuously calculate and display the total asset value over time, providing insights into how personal assets change with the market. The streaming query was initiated to monitor the asset values, which will fluctuate as the market prices change. This real-time analysis is crucial for personal investment strategies and understanding the impact of market movements on individual asset portfolios.

### CONCLUSION

The project successfully utilized Spark Streaming to conduct a comprehensive analysis of the stock market. The detailed methodologies and results for each task demonstrate the platform's capability to provide real-time insights and actionable data, which are crucial for investors and financial analysts. The report serves as a testament to the potential of big data technologies in transforming financial market analysis.

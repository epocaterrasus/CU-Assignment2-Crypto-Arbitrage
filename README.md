# Crypto Arbitrage

This project explores and analyzes two data sets ```bitstamp.csv``` and ```coinbase.csv``` which include the following information for the digital cryptocurrency Bitcoin (BTC) at the respective exchanges "Bitstamp" and "Coinbase" ranging from January 2018 to March 2018. The project consists of two steps, first cleaning up the data so that it can be analyzed and then analyzing the clean data set across different time ranges, this includes creating plots and obtaining summary statistics as well as calculating the potential spreads from doing an arbitrage operation between both exchanges.

The dataset includes the following:
* Timestamp (data set includes the following information for each minute in our time range )
* Opening Price "Open"
* High Price "High"
* Low Price "Low"
* Close Price "Low"
* Volume Expressed in BTC "BTC Volume"
* Volume Expressed in USD "USD Volume"
* Weighted Price

---

## Technologies

The following technologies were used to build and deploy this application:

* Python - Version 3.9.7
* Anaconda (Which includes Jupyter Lab and Pandas)
* Path (from pathlib)
* matplotlib

---

## Installation and Usage Guide

### 1. Install Python 3.9.7

For installing Python 3.9.7 you can find the Installation Files for both Windows/Mac OS in the following link
 * [Anaconda Installation Files](https://www.anaconda.com/products/individual "Anaconda Installation Files")

If you require assistance installing it, you can follow the following videos for guidance
* [Youtube Video Python Installation Guide - Windows](https://www.youtube.com/watch?v=uSVl7gRXP80 "Python Installation Video - Windows") 
* [Youtube Video Python Installation Guide - Mac](https://www.youtube.com/watch?v=r6bBaj797t8 "Python Installation Video - Mac") 
 
### 2. Install Anaconda

For installing Python 3.9.7 you can find the Installation Files for both Windows/Mac OS in the following link
 * [Python Installation Guide](https://www.python.org/downloads/release/python-397/ "Python Installation Guide")

If you require assistance installing it, you can follow the following videos for guidance
* [Youtube Video Anaconda Installation Guide - Windows](https://www.youtube.com/watch?v=g6ln1dAt-RI "Anaconda Installation Video - Windows") 
* [Youtube Video Anaconda Installation Guide - Mac](https://www.youtube.com/watch?v=oWVTO_69U4c "Anaconda Installation Video - Mac")

### 3. Downloading the Crypto Arbitrage Repository

Navigate to your desired location where you would like to save the documents for this application. You can do this by using the ```cd``` command followed by a space and the file path inside quotations ```" file path "```. In my example I have gone to Desktop.

![image](https://user-images.githubusercontent.com/94983278/149385012-181d1769-0af6-487e-8e04-823a28f2c3ed.png)

Clone this project's repository from GitHub using the following command 

```https://github.com/epocaterrasus/CU-Assignment3-Crypto-Arbitrage.git```

### 4. Opening the file on Jupyter Notebook

Being in the folder created when you downloaded the repository type ```jupyter lab```, this should open a window in your predetermined browser with Jupyter Lab. In the left corner you can see the files inside the repository, open the ```crypto_arbitrage.ipynb``` which contains all steps and notes followed to analyze this dataset pair.

---

## Explanation of the Processes Followed

### 1. Data Cleanup

Before being able to properly analyze the data to draw conclusions we must first import and clean the data, the following bullets give a summary of what was done:

* Importing both datasets using the pandas ```read_csv``` function and setting parameters to set index column to "Timestamp", making it parse dates and infer date/time format
* Droping NaN/Missing values using the ```dropna()``` function
* Removing "$" signs using the ```str.replace``` (this step is very important as it will allow us to convert from data type string to float, key to allowing us to do quantitative analysis on our data)
* Convert the data to "float" data type using the ```astype()``` function
* Review if there is any duplicates using the ```duplicated()``` function
* Selecting the relevant columns for our analysis, in this case the "Close" column using the ```.loc``` function

### 2. Data Analytics

After getting having our data squeaky clean and formatted we can go ahead and start our analysis, the following bullets give a summary of what was done:

* Generating summary statistics of both datasets using the ```describe()``` function
* Creating line plots for both datasets using the ```plot()``` and customizing them for size, title and line color
* Selecting specific months and dates within the dataset to focus the scope of our analysis
* Repeating the previous steps of generating summary statistics, line plots and adding boxplots to our specific date dataframes
* Calculating potential spreads between both exchanges
* Conditionally filtering spreads for which the return is (>0)
* Further focusing our conditional filters to gather datapoints in which the % spread return is (>1%) to account for potential trading fees
* Calculating potential profits and creating summary statistics and plots to allow us to better understand our data

---

## Conclusions drawn from our analysis

From our analysis we can conclude that there is a tendency for Bitcoin prices in Coinbase to be higher than prices in Bitstamp for the period ranging from January 2018 to March 2018. Diving deeper into the data we notice how the possibility to conduct arbitrage between both exchanges, is more prevalent in the months of January and steadily declines in February reaching lows in March. We can make the assumption that as levels of volume in Bitcoin trading increased, paired with a growing offering of exchanges/sellers, opportunities for arbitrage decrease as any discrepancies within the market are quickly gapped by traders (sometimes algorithms designed to "scalp")

Summary Statistics of Instances in which spread >1% for three randomly selected dates for the months of (January, February, March 2018)
![image](https://user-images.githubusercontent.com/94983278/149394946-46cf9e89-8f8b-4945-b752-79b8921b5716.png)

Plot of Closing Prices for Coinbase and Bitstamp (January-March 2018)
![image](https://user-images.githubusercontent.com/94983278/149395279-ed3052ab-2da6-48c5-899e-962f2165c792.png)

---

## Contributors

Edgar Pocaterra - epocaterra@protonmail.ch / +1 806 283 5455

---

## License

MIT License

Copyright (c) 2022 epocaterrasus

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
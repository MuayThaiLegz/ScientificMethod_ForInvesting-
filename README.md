# Wokring Towards a Scientific Method of Investing 

* Explanation 

Our main objective is to reach a definitive Scientific Method for Investing. We wanted to look at all the main Financial Statements and in these find.
1.	A means to optimize over time. 
2.	A means of measuring and managing risk.
3.	Based of 1 & 2 a means if valuing assets.
We began and had to confine this introductory query to the Balance sheet which offered a multidimensional array of opportunities to learn and practice developmental skills.

---

* Data

We used SinFin to download our csv files. https://simfin.com/data/bulk



 ![simfin](https://d7jore0ln5m9i.cloudfront.net/logo2.png)


---

* About 

As mentioned above we restricted ourselves to just the balance sheet and here is a breakdown of the Pandas DataFrames we sliced and concatenated to better be able to display values. We found that a time frame of four year helped deal with irregular availability of companies and availability of that years balance sheet.

We sliced the balance sheet into four components based on their intrinsic representation, we list them below.
All which are represented in the example code below.

We then looked at 4 companies in diversified industries to evaluate and compare financial health based on these selected values. 

---


* Custom DataFrames and Plots

After creating the DataFrames we used the .corr() method to evaluate the theorized interrelationships and plotted a heat map to visualize these results 

We also used a flexible method to plot our data. This will be an example in our selction below.

* Python Code Examples 

```

def clean_data(df):
"""Returns df with Columns ['SimFinId', 'Currency'] drop with .drop funtion
      .dropped function grouped by ['Ticker','Fiscal Year']  as type int
      Divides values to turn into percentages 
"""
    
    df.drop(['SimFinId', 'Currency'], inplace= True, errors='ignore', axis=1)
    df = df.groupby(['Ticker','Fiscal Year']).mean().dropna().astype(int)
   
    return df /1000000000



mask = us_balance_annual.index.get_level_values(level=1) > 2014 | (us_balance_annual.index.get_level_values(level=1) == 2018)
us_balance_annual_ = us_balance_annual.loc[mask]
us_balance_annual_



balance_sheet_cash_equal.groupby(level=0).plot.bar(
    title= ('Displays[balance_sheet_cash_equal] per Company'),
    figsize=(17,13),
    rot =360, 
    grid =True, 
    fontsize = 13)



balance_sheet_cash_equal = [
["Total Current Assets" ,
"Cash, Cash Equivalents & Short Term Investments", 
"Accounts & Notes Receivable", 
'Treasury Stock', 
'Retained Earnings']]
  
  
  
balance_sheet_tanglibles = [
['Total Current Assets',
"Cash, Cash Equivalents & Short Term Investments",
"Property, Plant & Equipment, Net",
"Retained Earnings", 
"Total Equity"]]
                                  


balance_sheet_intanglibles = [
['Treasury Stock', 
'Long Term Investments & Receivables', 
'Shares (Basic)', 
'Shares (Diluted)']]
     


balance_data_neg = [
["Inventories",
 "Share Capital & Additional Paid-In Capital", 
 "Payables & Accruals", "Total Liabilities", 
 "Long Term Debt", 
 'Shares (Diluted)',
 'Total Liabilities & Equity', 
 'Total Current Liabilities']]   
                                

```

---

* Technologies 

# Pandas
https://pandas.pydata.org/
Package overview
pandas is a Python package providing fast, flexible, and expressive data structures designed to make working with “relational” or “labeled” data both easy and intuitive. It aims to be the fundamental high-level building block for doing practical, real-world data analysis in Python. Additionally, it has the broader goal of becoming the most powerful and flexible open source data analysis/manipulation tool available in any language. It is already well on its way toward this goal.

![Pandas](https://miro.medium.com/max/819/1*Dss7A8Z-M4x8LD9ccgw7pQ.png)

---

# Seaborn
https://seaborn.pydata.org/
Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.

![seaborn](https://livecodestream.dev/post/how-to-build-beautiful-plots-with-python-and-seaborn/featured_hue585f61b28a74a671118de43150c5d63_166173_680x0_resize_q75_box.jpg)

---

# Scikit-learn
https://scikit-learn.org/stable/
Scikit-learn provides a range of supervised and unsupervised learning algorithms via a consistent interface in Python.

![Scikit](https://miro.medium.com/max/866/1*1ouD8HMkmJffNSAMfvBSkw.png)

---

* Plots created 
 


---
# Contributors
I completed this as a one man team, but learned the value of teamwork ten times over.



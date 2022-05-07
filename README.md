# Challenge-7


## ETF Performance

I will build a financial database and web application by using SQL, Python, and the Voilà library to analyze the performance of a hypothetical fintech ETF.


---

## Technologies

This project leverages Pandas, SQL and hvplot on Jupyter notebook

---

## Open Guide

Before running the application first open Jupyter lab in terminal:

```
  1. Activate dev environment by: "conda activate dev"
  2. Open Jupyter Notebook by: "Jupyter lab"
```


---

## Usage

To use the analysis simply clone the repository and run the **etf_analyzer.ipynb** within the Jupyter Notebook.\
*Import the following libraries and dependencies:*

``` python
import numpy as np
import pandas as pd
import hvplot.pandas
import sqlalchemy
```
Create a temporary SQLite database and create an engine to interact with the SQLite database. 

``` python
database_connection_string = 'sqlite:///etf.db'
engine = sqlalchemy.create_engine(database_connection_string)
``` 
The four stocks within the ETF are **GDOT, GS, PYPL** and **SQ**

---

## Analyze a single asset in the FinTech ETF

1. Use *SQL query* to *SELECT* the data from **PYPL**.
2. Use *pd.* to *read_sql_query* into a DataFrame. 
3. *head* and *tail* functions will show the top 5 and bottom 5 of the DataFrame. 
4. Use *hvplot* to visualize the **daily return** for **PYPL**.

![<PYPL>](<Image/PYPL daily return.png>)

5. *daily return +1.cumprod () - 1* will calculate the cumulative return for **PYPL**.

![<cum PYPL>](<Image/Cum PYPL.png>)

---

## Optimize the SQL Queries

1. Use *SELECT time, close FROM PYPL* and *WHERE close > 200* to filter the closing price higher than 200 in **PYPL**.
2. *pd.read_sql_query(query, con=engine)* will read the data from the database into DataFrame. 
3. Use *SELECT time, daily_returns FROM PYPL* and *ORDER BY daily_returns DESC* and *LIMIT 10* to get the top 10 return values in **PYPL** data on a descending order. 

---

## Analyze the Fintech ETF Portfolio

1. Use *SELECT * FROM GDOT* to *INNER JOIN* the portfolio into a single DataFrame. 
2. Use *pd.DataFrame* the **mean** of daily_return columns of all four assets. 
3. Use the average daily return multiple by *252* to get the **annualized returns** for the **portfolio**.
4. *average daily return +1.cumprod () - 1* will calculate the **cumulative return** for **portfolio**.
4. Use *hvplot* to visualize the **cumulative return** for the **portfolio**.

![<cum port>](<Image/cum port.png>)

---

## Deploy the Notebook as a Web Application

1. Use the Voilà library to deploy the notebook as a web application

![<viola>](<Image/voila.png>)

2. Web Application will appears like:

![<web>](<Image/web.png>)

---

## Contributors

Feier Ou 

ffeierou1003@gmail.com 

---

## License

Feier Ou 

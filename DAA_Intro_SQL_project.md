#**SQL Project: World Bank IDA Statement Insights**

**Project description:** This is an introductory SQL project that goes through historical data for IDA Statement Of Credits, Grants and Guaranteesvfrom The World Bank Group. [The raw data used is available here](https://financesone.worldbank.org/ida-statement-of-credits-grants-and-guarantees-historical-data/DS00976). These queries were written in DB Browser for SQLite after turning the .csv from The World Bank Group into a database.


### 1. Returning the entire table

```sql
SELECT * FROM IDA_Statements;
```

<img src="images/select_from_IDA_Statements_results.png"/>

### 2. Returning all records from table, but only the borrower & "Due to IDA" fields 

```sql
SELECT  Borrower, [Due to IDA (US$)] FROM IDA_Statements;
```

<img src="images/select_borrower_duetoIDA__statement_results.png"/>

### 3. Limiting the above query to only five records 

```sql
SELECT  Borrower, [Due to IDA (US$)] FROM IDA_Statements LIMIT 5; 
```
<img src="images/select_borrower_duetoIDA__statement_limited_results.png"/>

### 4. Created an alias for one field for clarity 

```sql
SELECT  Region, [Due to IDA (US$)] AS [Amount Due] FROM IDA_Statements LIMIT 20;
```
<img src="images/select_region_duetoIDA__statement_limited_results.png"/>


### 5. Pulling all records and all fields for Nicaragua only

```sql
SELECT * FROM IDA_Statements WHERE [Country / Economy] = 'Nicaragua';
```

<img src="images/select_where_nicaragua_statement_results.png"/>

### 6. Pulling the total number of transactions for Nicaragua

```sql
SELECT COUNT([Due to IDA (US$)]) FROM IDA_Statements WHERE [Country / Economy] = 'Nicaragua';
```

<img src="images/select_countIDA_nicaragua_statement_results.png"/>

### 7. Pulling the total number of transactions by Country/Economy 

```sql
SELECT [Country / Economy], COUNT(*) FROM IDA_Statements GROUP BY [Country / Economy];
```

<img src="images/group_by_country_statement_results.png"/>

### 8. Querying the maximum amount owed to The World Bank Group

```sql
SELECT MAX([Due to IDA (US$)]) FROM IDA_Statements;
```
<img src="images/MAX_IDA_statement_results.png"/>

### 9. Querying the total amount owed to The World Bank Group

```sql
SELECT SUM([Due to IDA (US$)]) FROM IDA_Statements;
```
<img src="images/SUM_IDA_statement_result.png"/>

```sql
--Other ways to approach Ninth Statement Cumulative sum
--In Thousands
SELECT SUM([Due to IDA (US$)])/1000 AS (Due to IDA in Thousands) FROM IDA_Statements;
--In Millions
SELECT SUM([Due to IDA (US$)])/1000000 AS (Due to IDA in Millions) FROM IDA_Statements;
--In Billions
SELECT SUM([Due to IDA (US$)])/1000000000 AS (Due to IDA in Billions) FROM IDA_Statements;
```

<img src="images/SUM_IDA_statement_K_results.png"/>
<img src="images/SUM_IDA_statement_M_results.png"/>
<img src="images/SUM_IDA_statement_B_results.png"/>


### 10. Querying the average service charge rate
```sql
SELECT AVG([Service Charge Rate]) AS [Average Service Charge Rate] FROM IDA_Statements;
```

<img src="images/select_avg_servchargerate_statement_results.png"/>


### 11. Selecting all records where there is a service charge rate (in ascending order)

```sql
SELECT * FROM IDA_Statements WHERE [Service Charge Rate] IS NOT NULL ORDER BY [Service Charge Rate] ASC;
```

<img src="images/order_by_service_charge_rate_statement_results_notNull.png"/>

### 11. Selecting all transactions for Honduras with a service charge rate greater than 1

```sql
SELECT * FROM IDA_Statements WHERE [Country / Economy] = 'Honduras' AND [Service Charge Rate] > 1;
```
<img src="images/order_by_service_charge_rate_statement_results_notNull.png"/>

### 12. Selecting all transactions for Project Cotton or Project River

```sql
SELECT * FROM IDA_Statements WHERE [Project Name] = 'COTTON' OR [Project Name] = 'RIVER';
```
<img src="images/where_project_cotton_or_river_statement_results.png"/>


### 13. Selecting all transactions except for those from Project Cotton

```sql
SELECT * FROM IDA_Statements WHERE [Project Name] IS NOT 'COTTON';
```

<img src="images/where_project_is_not_cotton_statement_results.png"/>


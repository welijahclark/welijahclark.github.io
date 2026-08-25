##SQL Project: World Bank IDA Statements

**Project description:** You can use this template to create projects in the future. Simply duplicate the page and change the text and images. 

Be sure to follow *The Interesting Project Template* as shown in [**The Data Science Project Studio**](https://www.datacareerjumpstart.com/products/the-data-science-project-studio/categories/2150357707/posts/2158441592). 

### 1. You can have sections and text.

Just like this. And you can even add internal coding blocks

```sql
SELECT * FROM IDA_Statements;
```

```sql
SELECT  Borrower, [Due to IDA (US$)] FROM IDA_Statements; 
```
```sql
SELECT  Borrower, [Due to IDA (US$)] FROM IDA_Statements LIMIT 5; 
```
```sql
SELECT  Region, [Due to IDA (US$)] AS [Amount Due] FROM IDA_Statements LIMIT 20;
```
```sql
SELECT * FROM IDA_Statements WHERE [Country / Economy] = 'Nicaragua';
```
```sql
SELECT COUNT([Due to IDA (US$)]) FROM IDA_Statements WHERE [Country / Economy] = 'Nicaragua';
```
```sql
SELECT [Country / Economy], COUNT(*) FROM IDA_Statements GROUP BY [Country / Economy];
```
```sql
SELECT MAX([Due to IDA (US$)]) FROM IDA_Statements;
```
```sql
SELECT SUM([Due to IDA (US$)]) FROM IDA_Statements;
```
```sql
--Other ways to approach Ninth Statement Cumulative sum
--In Thousands
SELECT SUM([Due to IDA (US$)])/1000 AS (Due to IDA in Thousands) FROM IDA_Statements;
--In Millions
SELECT SUM([Due to IDA (US$)])/1000000 AS (Due to IDA in Millions) FROM IDA_Statements;
--In Billions
SELECT SUM([Due to IDA (US$)])/1000000000 AS (Due to IDA in Billions) FROM IDA_Statements;
```

```sql
SELECT AVG([Service Charge Rate]) AS [Average Service Charge Rate] FROM IDA_Statements;
```

```sql
SELECT * FROM IDA_Statements WHERE [Service Charge Rate] IS NOT NULL ORDER BY [Service Charge Rate] ASC;
```

```sql
SELECT * FROM IDA_Statements WHERE [Country / Economy] = 'Honduras' AND [Service Charge Rate] > 1;
```

```sql
SELECT * FROM IDA_Statements WHERE [Project Name] = 'COTTON' OR [Project Name] = 'RIVER';
```

```sql
SELECT * FROM IDA_Statements WHERE [Project Name] IS NOT 'COTTON';
```


### 2. You can add any images you'd like. 

<img src="images/dummy_thumbnail.jpg?raw=true"/>



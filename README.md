![built with Python3](https://img.shields.io/badge/built%20with-Python3-blue.svg)    ![built with SQLite](https://img.shields.io/badge/built%20with-SQLite-red.svg)

# Gaming-Profit-Analysis

![alt text](https://raw.githubusercontent.com/david880110/Gaming-Profit-Analysis/master/image/Fantasy.jpg)

<p align="center">
  • <a href="#findings">Findings</a>
  • <a href="#syntax-detail">Syntax Detail</a>
  • <a href="#technology-Used">Technology Used</a>
</p>

To generate a report that breaks down the game's purchasing data into meaningful insights as the game is free-to-play, but players are encouraged to purchase optional items that enhance their playing experience.

## Findings 



## Syntax Detail

### Purchasing Analysis (Total)

```sql
SELECT 

DISTINCT(item_id) as 'Number of Unique Items',
AVG(price) as 'Average Price',
COUNT(item_id) as 'Number of Purchases',
SUM(price) as 'Total Revenue'

FROM purchase_table

;
```





Gender Demographics

###  Gender Demographics

```sql
SELECT 

gender as 'Gender',

(COUNT(gender)*100)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',

COUNT(gender) as 'Total Count'

FROM purchase_table

GROUP BY gender

ORDER BY "Percentage of Players" DESC
;
```





### Purchasing Analysis (Gender)

```sql
SELECT 

gender,
COUNT(gender) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

GROUP BY gender 
;
```





### Age Demographics

```sql
SELECT 

'06 - 10' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age < 10

Union

SELECT 

'10 - 14' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age BETWEEN 10 and 14

Union

SELECT 

'15 - 19' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age BETWEEN 15 and 19

Union

SELECT 

'20 - 24' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age BETWEEN 20 and 24

Union

SELECT 

'25 - 29' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age BETWEEN 25 and 29

Union

SELECT 

'30 - 34' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age BETWEEN 30 and 34

Union

SELECT 

'35 - 39' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age BETWEEN 35 and 39

Union

SELECT 

'40+' as Age,
COUNT(gender)/(SELECT COUNT(age) FROM purchase_table) || '%' as 'Percentage of Players',
COUNT(gender) as 'Total Count'

FROM purchase_table

WHERE age > 40

;
```



### Purchasing Analysis (Age)

```sql
SELECT 

'06 - 10' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age < 10

Union

SELECT 

'10 - 14' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age BETWEEN 10 and 14

Union

SELECT 

'15 - 19' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age BETWEEN 15 and 19

Union

SELECT 

'20 - 24' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age BETWEEN 20 and 24

Union

SELECT 

'25 - 29' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age BETWEEN 25 and 29

Union

SELECT 

'30 - 34' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age BETWEEN 30 and 34

Union

SELECT 

'35 - 39' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age BETWEEN 35 and 39

Union

SELECT 

'40+' as Age,
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

WHERE age > 40

;
```





### Top Spenders

```sql
SELECT 

DISTINCT(sn) as 'SN',
COUNT(price) as 'Purchase Count',
AVG(price) as 'Average Purchase Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

GROUP BY sn
ORDER BY "Total Purchase Value" DESC
LIMIT 5
;
```





### Most Popular Items

```sql
SELECT 

item_iD as 'Item ID',
item_name as 'Item Name',
COUNT(item_iD) as 'Purchase Count',
price as 'Item Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

GROUP BY sn
ORDER BY "Purchase Count" DESC
LIMIT 5
;
```





### Most Profitable Items

```sql
SELECT 

item_iD as 'Item ID',
item_name as 'Item Name',
COUNT(item_iD) as 'Purchase Count',
price as 'Item Price',
SUM(price) as 'Total Purchase Value'

FROM purchase_table

GROUP BY sn
ORDER BY "Total Purchase Value" DESC
LIMIT 5
;
```



## Technology Used

<img src="https://raw.githubusercontent.com/david880110/tech-logo/master/python%20logo.png" width="240" height="50"/>

<img src="https://raw.githubusercontent.com/david880110/tech-logo/master/sqlite%20logo.png" width="240" height="80"/>

<img src="https://raw.githubusercontent.com/david880110/tech-logo/master/tableau%20logo.png" width="240" height="60"/>
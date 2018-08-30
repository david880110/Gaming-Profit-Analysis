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

|         Gender        | Percentage of Players | Total Count |
|:---------------------:|:---------------------:|:-----------:|
|          Male         |        81.23543       |     697     |
|         Female        |        17.36597       |     149     |
| Other / Non-Disclosed |        1.398601       |      12     |

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

|         gender        | Purchase Count | Average Purchase Price | Total Purchase Value |
|:---------------------:|:--------------:|:----------------------:|:--------------------:|
|         Female        |       149      |        2.847584        |        424.29        |
|          Male         |       697      |        2.944448        |        2052.28       |
| Other / Non-Disclosed |       12       |          3.155         |         37.86        |

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

|   Age   | Percentage of Players | Total Count |
|:-------:|:---------------------:|:-----------:|
|  6 - 10 |        0.038462       |      33     |
| 11 - 14 |        0.044289       |      38     |
| 15 - 19 |        0.167832       |     144     |
| 20 - 24 |        0.433566       |     372     |
| 25 - 29 |        0.156177       |     134     |
| 30 - 34 |        0.082751       |      71     |
| 35 - 39 |        0.055944       |      48     |
|   40+   |        0.003497       |      3      |

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

|   Age   | Purchase Count | Average Purchase Price | Total Purchase Value |
|:-------:|:--------------:|:----------------------:|:--------------------:|
|  6 - 10 |       33       |        2.947879        |         97.28        |
| 11 - 14 |       38       |        2.787105        |        105.91        |
| 15 - 19 |       144      |        2.894653        |        416.83        |
| 20 - 24 |       372      |        2.923817        |        1087.66       |
| 25 - 29 |       134      |        2.958507        |        396.44        |
| 30 - 34 |       71       |        2.973803        |        211.14        |
| 35 - 39 |       48       |        2.932708        |        140.77        |
|   40+   |        3       |          2.88          |         8.64         |

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

|       SN      | Purchase Count | Average Purchase Price | Total Purchase Value |
|:-------------:|:--------------:|:----------------------:|:--------------------:|
|  Undirrala66  |        5       |          3.412         |         17.06        |
| Aerithllora36 |        4       |          3.775         |         15.1         |
|    Saedue76   |        4       |          3.39          |         13.56        |
|    Sondim43   |        4       |          3.255         |         13.02        |
|  Mindimnya67  |        4       |          3.185         |         12.74        |


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

| Item ID |              Item Name             | Purchase Count | Item Price | Total Purchase Value |
|:-------:|:----------------------------------:|:--------------:|:----------:|:--------------------:|
|   133   |          Faith's Scimitar          |        5       |    3.82    |         17.06        |
|   148   | Warmonger, Gift of Suffering's End |        4       |    4.65    |         15.1         |
|   122   |          Unending Tyranny          |        4       |    1.21    |         5.87         |
|   104   |         Gladiator's Glaive         |        4       |    1.84    |         9.68         |
|   161   |               Devine               |        4       |    1.45    |         12.74        |

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

| Item ID |              Item Name             | Purchase Count | Item Price | Total Purchase Value |
|:-------:|:----------------------------------:|:--------------:|:----------:|:--------------------:|
|   133   |          Faith's Scimitar          |        5       |    3.82    |         17.06        |
|   148   | Warmonger, Gift of Suffering's End |        4       |    4.65    |         15.1         |
|    73   |             Ritual Mace            |        4       |    3.74    |         13.56        |
|    94   |           Mourning Blade           |        4       |    3.64    |         13.02        |
|   161   |               Devine               |        4       |    1.45    |         12.74        |

## Technology Used

<img src="https://raw.githubusercontent.com/david880110/tech-logo/master/python%20logo.png" width="240" height="50"/>

<img src="https://raw.githubusercontent.com/david880110/tech-logo/master/sqlite%20logo.png" width="240" height="80"/>

<img src="https://raw.githubusercontent.com/david880110/tech-logo/master/tableau%20logo.png" width="240" height="60"/>
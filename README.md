# goit-rdb-hw-07
## 1. Date components
```sql
USE mydb;

SELECT
	date as original_date,
    YEAR(date) as year,
    MONTH(date) as month,
    DAY(date) as day
FROM orders;
```

## 2. Add date
```sql
USE mydb;

SELECT
	id,
	date as original_date,
    date + INTERVAL 1 DAY as next_day
FROM orders;
```

## 3. Timestamp
```sql
USE mydb;

SELECT
	id,
	date as original_date,
    UNIX_TIMESTAMP(date) as date_timestamp
FROM orders;
```

## 4. BETWEEN
```sql
USE mydb;

SELECT
	COUNT(*) as rows_count
FROM orders
WHERE date BETWEEN "1996-07-10" AND "1996-10-08"
```

## 5. JSON
```sql
USE mydb;

SELECT
	id,
    date,
    JSON_OBJECT('id', id, 'date', date) as json_data
FROM orders
```

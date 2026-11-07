## Task 1

```
mysql> SELECT 
    ->     SUM(index_length) AS total_index_size_bytes,
    ->     SUM(data_length) AS total_data_size_bytes,
    ->     ROUND((SUM(index_length) / SUM(data_length)) * 100, 2) AS index_to_data_percentage
    -> FROM information_schema.tables
    -> WHERE table_schema = 'sakila';
+------------------------+-----------------------+--------------------------+
| total_index_size_bytes | total_data_size_bytes | index_to_data_percentage |
+------------------------+-----------------------+--------------------------+
|                2392064 |               4374528 |                    54.68 |
+------------------------+-----------------------+--------------------------+
1 row in set (0.03 sec)

```

---


## Task 2 

```
EXPLAIN ANALYZE
select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id, f.title)
from payment p, rental r, customer c, inventory i, film f
where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id

mysql> EXPLAIN ANALYZE
    -> select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id, f.title)
    -> from payment p, rental r, customer c, inventory i, film f
    -> where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id
    -> 
    -> ;

#####################################################################################################################
 EXPLAIN                                                                                                               
 -> Table scan on <temporary>  (cost=2.5..2.5 rows=0) (actual time=5028..5028 rows=391 loops=1)
    -> Temporary table with deduplication  (cost=0..0 rows=0) (actual time=5028..5028 rows=391 loops=1)
        -> Window aggregate with buffering: sum(payment.amount) OVER (PARTITION BY c.customer_id,f.title )   (actual time=2209..4855 rows=642000 loops=1)
            -> Sort: c.customer_id, f.title  (actual time=2209..2267 rows=642000 loops=1)
                -> Stream results  (cost=22e+6 rows=16.1e+6) (actual time=1.01..1575 rows=642000 loops=1)
                    -> Nested loop inner join  (cost=22e+6 rows=16.1e+6) (actual time=0.996..1349 rows=642000 loops=1)
                        -> Nested loop inner join  (cost=20.4e+6 rows=16.1e+6) (actual time=0.986..1167 rows=642000 loops=1)
                            -> Nested loop inner join  (cost=18.8e+6 rows=16.1e+6) (actual time=0.972..970 rows=642000 loops=1)
                                -> Inner hash join (no condition)  (cost=1.61e+6 rows=16.1e+6) (actual time=0.933..43.8 rows=634000 loops=1)
                                    -> Filter: (cast(p.payment_date as date) = '2005-07-30')  (cost=1.68 rows=16086) (actual time=0.244..6.23 rows=634 loops=1)
                                        -> Table scan on p  (cost=1.68 rows=16086) (actual time=0.228..4.06 rows=16044 loops=1)
                                    -> Hash
                                        -> Covering index scan on f using idx_title  (cost=103 rows=1000) (actual time=0.345..0.59 rows=1000 loops=1)
                                -> Covering index lookup on r using rental_date (rental_date=p.payment_date)  (cost=0.969 rows=1) (actual time=925e-6..0.00132 rows=1.01 loops=634000)
                            -> Single-row index lookup on c using PRIMARY (customer_id=r.customer_id)  (cost=250e-6 rows=1) (actual time=144e-6..169e-6 rows=1 loops=642000)
                        -> Single-row covering index lookup on i using PRIMARY (inventory_id=r.inventory_id)  (cost=250e-6 rows=1) (actual time=119e-6..149e-6 rows=1 loops=642000)
 |


```

```
mysql> EXPLAIN ANALYZE
    -> SELECT 
    ->     CONCAT(c.last_name, ' ', c.first_name) AS customer_name,
    ->     SUM(p.amount) AS total_amount
    -> FROM payment p
    -> INNER JOIN rental r ON p.rental_id = r.rental_id
    -> INNER JOIN customer c ON r.customer_id = c.customer_id
    -> INNER JOIN inventory i ON r.inventory_id = i.inventory_id
    -> INNER JOIN film f ON i.film_id = f.film_id
    -> WHERE p.payment_date >= '2005-07-30 00:00:00' 
    ->   AND p.payment_date < '2005-07-31 00:00:00'
    -> GROUP BY c.customer_id, f.title;

#####################################################################################################################
| EXPLAIN

| -> Table scan on <temporary>  (actual time=17.1..17.2 rows=634 loops=1)
    -> Aggregate using temporary table  (actual time=17.1..17.1 rows=634 loops=1)
        -> Nested loop inner join  (cost=5475 rows=1787) (actual time=5.31..16 rows=634 loops=1)
            -> Nested loop inner join  (cost=4849 rows=1787) (actual time=5.29..14.9 rows=634 loops=1)
                -> Nested loop inner join  (cost=4224 rows=1787) (actual time=5.27..14 rows=634 loops=1)
                    -> Nested loop inner join  (cost=3599 rows=1787) (actual time=5.15..13.2 rows=634 loops=1)
                        -> Filter: ((p.payment_date >= TIMESTAMP'2005-07-30 00:00:00') and (p.payment_date < TIMESTAMP'2005-07-31 00:00:00') and (p.rental_id is not null))  (cost=1633 rows=1787) (actual time=0.35..5.41 rows=634 loops=1)
                            -> Table scan on p  (cost=1633 rows=16086) (actual time=0.337..4.04 rows=16044 loops=1)
                        -> Single-row index lookup on r using PRIMARY (rental_id=p.rental_id)  (cost=1 rows=1) (actual time=0.0119..0.0119 rows=1 loops=634)
                    -> Single-row index lookup on c using PRIMARY (customer_id=r.customer_id)  (cost=0.25 rows=1) (actual time=0.00112..0.00115 rows=1 loops=634)
                -> Single-row index lookup on i using PRIMARY (inventory_id=r.inventory_id)  (cost=0.25 rows=1) (actual time=0.00119..0.00121 rows=1 loops=634)
            -> Single-row index lookup on f using PRIMARY (film_id=i.film_id)  (cost=0.25 rows=1) (actual time=0.00161..0.00163 rows=1 loops=634)
 |

1 row in set (0.03 sec)
```

```
mysql> CREATE INDEX idx_payment_date_rental_amount ON payment(payment_date, rental_id, amount);
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> EXPLAIN ANALYZE SELECT      CONCAT(c.last_name, ' ', c.first_name) AS customer_name,     SUM(p.amount) AS total_amount FROM payment p INNER JOIN rental r ON p.rental_id = r.rental_id INNER JOIN customer c ON r.customer_id = c.customer_id INNER JOIN inventory i ON r.inventory_id = i.inventory_id INNER JOIN film f ON i.film_id = f.film_id WHERE p.payment_date >= '2005-07-30 00:00:00'    AND p.payment_date < '2005-07-31 00:00:00' GROUP BY c.customer_id, f.title;

#####################################################################################################################

EXPLAIN                                                                                                               
| -> Table scan on <temporary>  (actual time=4.26..4.33 rows=634 loops=1)
    -> Aggregate using temporary table  (actual time=4.25..4.25 rows=634 loops=1)
        -> Nested loop inner join  (cost=1462 rows=634) (actual time=0.134..3.53 rows=634 loops=1)
            -> Nested loop inner join  (cost=1240 rows=634) (actual time=0.128..2.77 rows=634 loops=1)
                -> Nested loop inner join  (cost=1018 rows=634) (actual time=0.123..1.98 rows=634 loops=1)
                    -> Nested loop inner join  (cost=796 rows=634) (actual time=0.118..1.24 rows=634 loops=1)
                        -> Filter: ((p.payment_date >= TIMESTAMP'2005-07-30 00:00:00') and (p.payment_date < TIMESTAMP'2005-07-31 00:00:00') and (p.rental_id is not null))  (cost=129 rows=634) (actual time=0.106..0.415 rows=634 loops=1)
                            -> Covering index range scan on p using idx_payment_date_rental_amount over ('2005-07-30 00:00:00' <= payment_date < '2005-07-31 00:00:00')  (cost=129 rows=634) (actual time=0.104..0.3 rows=634 loops=1)
                        -> Single-row index lookup on r using PRIMARY (rental_id=p.rental_id)  (cost=0.952 rows=1) (actual time=0.0011..0.00113 rows=1 loops=634)
                    -> Single-row index lookup on c using PRIMARY (customer_id=r.customer_id)  (cost=0.25 rows=1) (actual time=982e-6..0.00101 rows=1 loops=634)
                -> Single-row index lookup on i using PRIMARY (inventory_id=r.inventory_id)  (cost=0.25 rows=1) (actual time=0.00106..0.00109 rows=1 loops=634)
            -> Single-row index lookup on f using PRIMARY (film_id=i.film_id)  (cost=0.25 rows=1) (actual time=0.001..0.00103 rows=1 loops=634)
 |

1 row in set (0.00 sec)

```


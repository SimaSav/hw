## Task 1
```
mysql> SELECT 
    ->     CONCAT(st.first_name, ' ', st.last_name) AS staff_name,
    ->     c.city,
    ->     COUNT(cu.customer_id) AS customer_count
    -> FROM store s
    -> JOIN staff st ON s.manager_staff_id = st.staff_id --  s.store_id = st.store_id
    -> JOIN address a ON s.address_id = a.address_id
    -> JOIN city c ON a.city_id = c.city_id
    -> JOIN customer cu ON s.store_id = cu.store_id
    -> GROUP BY s.store_id, st.first_name, st.last_name, c.city
    -> HAVING COUNT(cu.customer_id) > 300;
+--------------+------------+----------------+
| staff_name   | city       | customer_count |
+--------------+------------+----------------+
| Mike Hillyer | Lethbridge |            326 |
+--------------+------------+----------------+
1 row in set (0.01 sec)
```
---

## Task 2

```
mysql> SELECT COUNT(*) AS film_count
    -> FROM film
    -> WHERE length > (SELECT AVG(length) FROM film);
+------------+
| film_count |
+------------+
|        489 |
+------------+
1 row in set (0.00 sec)

```

---

## Task 3

```
mysql> SELECT 
    ->     DATE_FORMAT(p.payment_date, '%Y-%m') AS payment_month,
    ->     SUM(p.amount) AS total_payments,
    ->     COUNT(DISTINCT p.rental_id) AS rental_count
    -> FROM payment p
    -> GROUP BY DATE_FORMAT(p.payment_date, '%Y-%m')
    -> ORDER BY total_payments DESC
    -> LIMIT 1;
+---------------+----------------+--------------+
| payment_month | total_payments | rental_count |
+---------------+----------------+--------------+
| 2005-07       |       28368.91 |         6709 |
+---------------+----------------+--------------+
1 row in set (0.03 sec)

```

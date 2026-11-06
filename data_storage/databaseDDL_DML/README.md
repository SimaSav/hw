Task 1


![task1](<./img/Screenshot1t1.png>)

![task1](<./img/Screenshot2t1.png>)

![task1](<./img/Screenshot3t1.png>)
```
sudo docker run --name mysql-sakila -e MYSQL_ROOT_PASSWORD=root_password -p 3306:3306 -d mysql:8.0
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'qwe123!@#';
SELECT user, host FROM mysql.user;
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
SHOW GRANTS FOR 'sys_temp'@'localhost';
ALTER USER 'sys_temp'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password';
FLUSH PRIVILEGES;
sudo docker exec -i mysql-sakila mysql -usys_temp -pyour_password < sakila-schema.sql
sudo docker exec -i mysql-sakila mysql -usys_temp -pyour_password sakila < sakila-data.sql
USE sakila;
SHOW TABLES;
```
---

Task 2

![task2](<./img/t2.png>)
```
mysql> SELECT      table_name AS 'table',      column_name AS 'PRIMARY' FROM      information_schema.key_column_usage WHERE      table_schema = 'sakila'      AND constraint_name = 'PRIMARY' ORDER BY      table_name;
+---------------+--------------+
| table         | PRIMARY      |
+---------------+--------------+
| actor         | actor_id     |
| address       | address_id   |
| category      | category_id  |
| city          | city_id      |
| country       | country_id   |
| customer      | customer_id  |
| film          | film_id      |
| film_actor    | actor_id     |
| film_actor    | film_id      |
| film_category | film_id      |
| film_category | category_id  |
| film_text     | film_id      |
| inventory     | inventory_id |
| language      | language_id  |
| payment       | payment_id   |
| rental        | rental_id    |
| staff         | staff_id     |
| store         | store_id     |
+---------------+--------------+
18 rows in set (0.00 sec)

```

Conexión
`mysql -u root -h sql.myserver.com -P 3306 -p`

MariaDB [nc_coffe]> show tables;
Empty set (0.001 sec)

MariaDB [nc_coffe]> create table coffe_table (
    -> id int,
    -> name varchar(255),
    -> region varchar(255),
    -> roast varchar(255)
    -> );
Query OK, 0 rows affected (0.016 sec)

MariaDB [nc_coffe]> show tables
    -> ;
+--------------------+
| Tables_in_nc_coffe |
+--------------------+
| coffe_table        |
+--------------------+
1 row in set (0.001 sec)

MariaDB [nc_coffe]> describe coffe_table;
+--------+--------------+------+-----+---------+-------+
| Field  | Type         | Null | Key | Default | Extra |
+--------+--------------+------+-----+---------+-------+
| id     | int(11)      | YES  |     | NULL    |       |
| name   | varchar(255) | YES  |     | NULL    |       |
| region | varchar(255) | YES  |     | NULL    |       |
| roast  | varchar(255) | YES  |     | NULL    |       |
+--------+--------------+------+-----+---------+-------+
4 rows in set (0.002 sec)
***
MariaDB [nc_coffe]> insert into coffe_table values (1, "default route", "ethiopia", "light");
Query OK, 1 row affected (0.002 sec)

MariaDB [nc_coffe]> select * from coffe_table;
+------+---------------+----------+-------+
| id   | name          | region   | roast |
+------+---------------+----------+-------+
|    1 | default route | ethiopia | light |
+------+---------------+----------+-------+
1 row in set (0.001 sec)


MariaDB [nc_coffe]> insert into coffe_table values ( 2, "docker run", "mexico", "medium");
Query OK, 1 row affected (0.002 sec)

MariaDB [nc_coffe]> insert into coffe_table values ( 3, "helpdesk", "honduras", "medium");
Query OK, 1 row affected (0.002 sec)

MariaDB [nc_coffe]> insert into coffe_table values ( 4, "on-call", "peru", "dark");
Query OK, 1 row affected (0.002 sec)

MariaDB [nc_coffe]> insert into coffe_table values ( 5, "ifconfig", "tanzania", "blonde");
Query OK, 1 row affected (0.002 sec)

MariaDB [nc_coffe]> insert into coffe_table values ( 6, "traceroute", "bali", "med-dark");
Query OK, 1 row affected (0.002 sec)

***
MariaDB [nc_coffe]> select * from avengers;
+------+------------+-----------+----------+------+-------------------+
| id   | first_name | last_name | origin   | age  | alias             |
+------+------------+-----------+----------+------+-------------------+
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |
|    2 | clint      | barton    | earth    |   35 | hawkeye           |
|    3 | tony       | stark     | earth    |   52 | iron man          |
|    4 | peter      | parker    | earth    |   17 | spiderman         |
|    5 | groot      | groot     | planet x |   18 | tree              |
+------+------------+-----------+----------+------+-------------------+
5 rows in set (0.001 sec)

MariaDB [nc_coffe]> select * from avengers where origin = "earth";
+------+------------+-----------+--------+------+-----------+
| id   | first_name | last_name | origin | age  | alias     |
+------+------------+-----------+--------+------+-----------+
|    2 | clint      | barton    | earth  |   35 | hawkeye   |
|    3 | tony       | stark     | earth  |   52 | iron man  |
|    4 | peter      | parker    | earth  |   17 | spiderman |
+------+------------+-----------+--------+------+-----------+
3 rows in set (0.001 sec)

MariaDB [nc_coffe]> select * from avengers where origin = "earth" or origin = "asgard";
+------+------------+-----------+--------+------+-------------------+
| id   | first_name | last_name | origin | age  | alias             |
+------+------------+-----------+--------+------+-------------------+
|    1 | thor       | odinson   | asgard | 1500 | strongest avenger |
|    2 | clint      | barton    | earth  |   35 | hawkeye           |
|    3 | tony       | stark     | earth  |   52 | iron man          |
|    4 | peter      | parker    | earth  |   17 | spiderman         |
+------+------------+-----------+--------+------+-------------------+

MariaDB [nc_coffe]> select * from avengers where age <= 30;
+------+------------+-----------+----------+------+-----------+
| id   | first_name | last_name | origin   | age  | alias     |
+------+------------+-----------+----------+------+-----------+
|    4 | peter      | parker    | earth    |   17 | spiderman |
|    5 | groot      | groot     | planet x |   18 | tree      |
+------+------------+-----------+----------+------+-----------+
2 rows in set (0.001 sec)


MariaDB [nc_coffe]> select * from avengers where not origin = "earth";
+------+------------+-----------+----------+------+-------------------+
| id   | first_name | last_name | origin   | age  | alias             |
+------+------------+-----------+----------+------+-------------------+
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |
|    5 | groot      | groot     | planet x |   18 | tree              |
+------+------------+-----------+----------+------+-------------------+
2 rows in set (0.001 sec)


MariaDB [nc_coffe]> select * from avengers;
+------+------------+-----------+----------+------+-------------------+
| id   | first_name | last_name | origin   | age  | alias             |
+------+------------+-----------+----------+------+-------------------+
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |
|    2 | clint      | barton    | earth    |   35 | hawkeye           |
|    3 | tony       | stark     | earth    |   52 | iron man          |
|    4 | peter      | parker    | earth    |   17 | spiderman         |
|    5 | groot      | groot     | planet x |   18 | tree              |
|    6 | jeff       | smith     | earth    |   43 | jeff the man      |
+------+------------+-----------+----------+------+-------------------+
6 rows in set (0.001 sec)

MariaDB [nc_coffe]> delete from avengers where first_name = "jeff";
Query OK, 1 row affected (0.002 sec)

MariaDB [nc_coffe]> select * from avengers;
+------+------------+-----------+----------+------+-------------------+
| id   | first_name | last_name | origin   | age  | alias             |
+------+------------+-----------+----------+------+-------------------+
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |
|    2 | clint      | barton    | earth    |   35 | hawkeye           |
|    3 | tony       | stark     | earth    |   52 | iron man          |
|    4 | peter      | parker    | earth    |   17 | spiderman         |
|    5 | groot      | groot     | planet x |   18 | tree              |
+------+------------+-----------+----------+------+-------------------+
5 rows in set (0.001 sec)


MariaDB [nc_coffe]> update avengers set last_name = NULL where first_name = "groot"
    -> ;
Query OK, 1 row affected (0.002 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [nc_coffe]> select * from avengers;
+------+------------+-----------+----------+------+-------------------+
| id   | first_name | last_name | origin   | age  | alias             |
+------+------------+-----------+----------+------+-------------------+
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |
|    2 | clint      | barton    | earth    |   35 | hawkeye           |
|    3 | tony       | stark     | earth    |   52 | iron man          |
|    4 | peter      | parker    | earth    |   17 | spiderman         |
|    5 | groot      | NULL      | planet x |   18 | tree              |
+------+------------+-----------+----------+------+-------------------+
5 rows in set (0.001 sec)

***
MariaDB [nc_coffe]> select * from avengers order by age asc;
+------+------------+-----------+----------+------+-------------------+
| id   | first_name | last_name | origin   | age  | alias             |
+------+------------+-----------+----------+------+-------------------+
|    4 | peter      | parker    | earth    |   17 | spiderman         |
|    5 | groot      | NULL      | planet x |   18 | tree              |
|    2 | clint      | barton    | earth    |   35 | hawkeye           |
|    3 | tony       | stark     | earth    |   52 | iron man          |
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |
+------+------------+-----------+----------+------+-------------------+

********
MariaDB [nc_coffe]> alter table avengers add beard boolean;
Query OK, 0 rows affected (0.015 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [nc_coffe]> select * from avengers;
+------+------------+-----------+----------+------+-------------------+-------+
| id   | first_name | last_name | origin   | age  | alias             | beard |
+------+------------+-----------+----------+------+-------------------+-------+
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |  NULL |
|    2 | clint      | barton    | earth    |   35 | hawkeye           |  NULL |
|    3 | tony       | stark     | earth    |   52 | iron man          |  NULL |
|    4 | peter      | parker    | earth    |   17 | spiderman         |  NULL |
|    5 | groot      | NULL      | planet x |   18 | tree              |  NULL |
+------+------------+-----------+----------+------+-------------------+-------+
5 rows in set (0.001 sec)

***

MariaDB [nc_coffe]> update avengers set beard = true  where id = 1 or id = 3;
Query OK, 2 rows affected (0.002 sec)
Rows matched: 2  Changed: 2  Warnings: 0

MariaDB [nc_coffe]> select * from avengers;
+------+------------+-----------+----------+------+-------------------+-------+
| id   | first_name | last_name | origin   | age  | alias             | beard |
+------+------------+-----------+----------+------+-------------------+-------+
|    1 | thor       | odinson   | asgard   | 1500 | strongest avenger |     1 |
|    2 | clint      | barton    | earth    |   35 | hawkeye           |     0 |
|    3 | tony       | stark     | earth    |   52 | iron man          |     1 |
|    4 | peter      | parker    | earth    |   17 | spiderman         |     0 |
|    5 | groot      | NULL      | planet x |   18 | tree              |     0 |
+------+------------+-----------+----------+------+-------------------+-------+


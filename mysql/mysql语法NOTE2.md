1、mysql 连接：
      JOIN 按照功能大致分为如下三类：
            INNER JOIN（内连接,或等值连接）：获取两个表中字段匹配关系的记录。
            LEFT JOIN（左连接）：获取左表所有记录，即使右表没有对应匹配的记录。
            RIGHT JOIN（右连接）： 与 LEFT JOIN 相反，用于获取右表所有记录，即使左表没有对应匹配的记录。
      1、INNER JOIN 为交集：
            NNER JOIN(也可以省略 INNER 使用 JOIN，效果一样)来连接以上两张表来读取runoob_tbl表中所有runoob_author字段
            在tcount_tbl表对应的runoob_count字段值：
                mysql> SELECT a.runoob_id, a.runoob_author, b.runoob_count FROM
                    -> runoob_tbl a INNER JOIN tcount_tbl b ON a.runoob_author = b.runoob_author;
                +-----------+---------------+--------------+
                | runoob_id | runoob_author | runoob_count |
                +-----------+---------------+--------------+
                |         1 | 菜鸟教程      |           10 |
                |         2 | 菜鸟教程      |           10 |
                |         3 | RUNOOB.COM    |           20 |
                |         4 | RUNOOB.COM    |           20 |
                +-----------+---------------+--------------+
                4 rows in set (0.00 sec) 
                ![image img_innerjoin.gif](https://github.com/fenglinupc/HelloWorld/blob/master/img-folder/img_innerjoin.gif)
       2、LEFT JOIN
              MySQL left join 与 join 有所不同。 MySQL LEFT JOIN 会读取左边数据表的全部数据，即便右边表无对应数据。        

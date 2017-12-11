<h3>1、mysql 连接：<br/></h3>
      JOIN 按照功能大致分为如下三类：<br/>
            INNER JOIN（内连接,或等值连接）：获取两个表中字段匹配关系的记录。<br/>
            LEFT JOIN（左连接）：获取左表所有记录，即使右表没有对应匹配的记录。<br/>
            RIGHT JOIN（右连接）： 与 LEFT JOIN 相反，用于获取右表所有记录，即使左表没有对应匹配的记录。<br/>
      1、INNER JOIN 为交集：<br/>
            NNER JOIN(也可以省略 INNER 使用 JOIN，效果一样)来连接以上两张表来读取runoob_tbl表中所有runoob_author字段<br/>
            在tcount_tbl表对应的runoob_count字段值：<br/>
                mysql> SELECT a.runoob_id, a.runoob_author, b.runoob_count FROM<br/>
                    -> runoob_tbl a INNER JOIN tcount_tbl b ON a.runoob_author = b.runoob_author;<br/>
                +-----------+---------------+--------------+<br/>
                | runoob_id | runoob_author | runoob_count |<br/>
                +-----------+---------------+--------------+<br/>
                |         1 | 菜鸟教程      |           10 |                <br/>
                |         2 | 菜鸟教程      |           10 |       <br/>
                |         3 | RUNOOB.COM    |           20 | <br/>
                |         4 | RUNOOB.COM    |           20 | <br/>
                +-----------+---------------+--------------+ <br/>
                4 rows in set (0.00 sec) <br/>
                ![image img_innerjoin.gif](https://github.com/fenglinupc/HelloWorld/blob/master/img-folder/img_innerjoin.gif) 
       2、LEFT JOIN   <br/>
              MySQL left join 与 join 有所不同。 MySQL LEFT JOIN 会读取左边数据表的全部数据，即便右边表无对应数据。   <br/>
              mysql> select a.runoob_id, a.runoob_author, b.runoob_count FROM   <br/>
                  -> runoob_tbl a LEFT JOIN tcount_tbl b ON a.runoob_author = b.runoob_author;   <br/>
                        +-----------+---------------+--------------+   <br/>
                        | runoob_id | runoob_author | runoob_count |   <br/>
                        +-----------+---------------+--------------+  <br/>
                        |         1 | 菜鸟教程      |           10 |  <br/>
                        |         2 | 菜鸟教程      |           10 |  <br/>
                        |         3 | RUNOOB.COM    |           20 |  <br/>
                        |         4 | RUNOOB.COM    |           20 | <br/>
                        |         5 | FK            |         NULL |  <br/>
                        +-----------+---------------+--------------+ <br/>
                        5 rows in set (0.00 sec)  <br/>
                ![image img_innerjoin.gif](https://github.com/fenglinupc/HelloWorld/blob/master/img-folder/img_leftjoin.gif) <br/>
        3、RIGHT JOIN  <br/>
             MySQL RIGHT JOIN 会读取右边数据表的全部数据，即便左边边表无对应数据。 <br/>
             实例:mysql> select a.runoob_id, a.runoob_author, b.runoob_count FROM  <br/>
                      -> runoob_tbl a RIGHT JOIN tcount_tbl b ON a.runoob_author = b.runoob_author;
                        +-----------+---------------+--------------+  <br/>
                        | runoob_id | runoob_author | runoob_count |  <br/>
                        +-----------+---------------+--------------+  <br/>
                        |         1 | 菜鸟教程      |           10 |   <br/>
                        |         2 | 菜鸟教程      |           10 |   <br/>
                        |         3 | RUNOOB.COM    |           20 |  <br/>
                        |         4 | RUNOOB.COM    |           20 |  <br/>
                        |      NULL | NULL          |           22 |  <br/>
                        +-----------+---------------+--------------+  <br/>
                        5 rows in set (0.00 sec)  <br/>
                ![image img_innerjoin.gif](https://github.com/fenglinupc/HelloWorld/blob/master/img-folder/img_rightjoin.gif) 

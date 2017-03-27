## 与Apache一起使用MySQL

还有一些项目，你可以从MySQL数据库鉴别用户，并且你还可以将日志文件写入MySQL数据库表。你可以将以下内容放到Apache配置文件中，更改Apache日志格式，使MySQL更容易读取：

```Apache
LogFormat \
        "\"%h\",%{%Y%m%d%H%M%S}t,%>s,\"%b\",\"%{Content-Type}o\",  \
        \"%U\",\"%{Referer}i\",\"%{User-Agent}i\""
```

要想将该格式的日志文件装载到MySQL，你可以使用以下语句:

```mysql
LOAD DATA INFILE '/local/access_log' INTO TABLE tbl_name
FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"' ESCAPED BY '\\'
```

所创建的表中的列应与写入日志文件的LogFormat行对应。

http://doc.mysql.cn/mysql5/refman-5.1-zh.html-chapter/tutorial.html#connecting-disconnecting
left join 关键字会从左表(table_name1)那里返回所有的行,即使从右表(table_name2)中没有匹配的行.
```sql
select column_name
from table_name1
left join table_name2
on table_name1.column_name = table_name2.column_name
```


# 参考资料
- [W3school : SQL教程](http://www.w3school.com.cn/sql/index.asp)
在对数据库操作过程中，最主要的操作就是select操作，select语句的语法结构：

```sql
SELECT [DISTINCT] 目标表的列名或列表达式序列	---DISTINCT选项可保证查询结果集中不存在重复元组
FROM 关系名表序列
[WHERE 行条件表达式]
[GROUP BY 列名序列
[HAVING 组条件表达式]]
[ORDER BY 列名[ASC|DESC]…]
```

> WHERE子句的条件表达式中可以使用的运算符有：
>
> - 比较运算符（<、<=、>、>=、=、<>）和BETWEEN运算符；
> - 逻辑运算符（AND、OR、NOT）；
> - 集合成员运算符（IN、NOT IN）；
> - 字符串匹配运算符（LIKE）；
> - 谓词（EXISTS、ALL、SOME、UNIQUE）；
> - 聚合函数；
> - 空值比较运算符（IS NULL、IS NOT NULL）；
> - 集合运算符（UNION、INTERSECT、EXCEPT）等  



## 字符串的匹配运算

通常可以利用字符串的匹配运算进行模糊查询。谓词LIKE可以用来进行字符串的匹配运算，其一般语法格式如下：

```sql
[NOT] LIKE '匹配串' [ESCAPE '匹配串']
```

其含义是查找指定的属性列值与“匹配串”相匹配的元组。“匹配串”可以是一个完整的字符串，也可以含有通配符％和 _ 。

-  `％（百分号）`代表任意长度（长度可以为 0）的字符串。例如 a％b 表示以 a 开头，以 b 结尾的任意长度的字符串，如 acb、addgb、ab 等都满足该匹配串。
-  `_（下划线）`代表任意单个字符。例如 a_b 表示以 a 开头，以 b 结尾的长度为 3 的任意字符串，acb、afb 等都满足该匹配串。  





当 WHERE 子句、GROUP BY 子句、HAVING 子句和聚合函数同时出现在一个查询中时，SELECT 命令的执行顺序如下：

1. 执行WHERE子句，从表中选取行。
2. 由GROUP BY对选取的行进行分组。
3. 执行聚合函数。
4. 执行HAVING子句选取满足条件的分组。  



外连接

- LEFT OUTER JOIN 或 LEFT JOIN（左外连接）。
- RIGHT OUTER JOIN 或 RIGHT JOIN（右外连接）。
- FULL OUTER JOIN 或 FULL JOIN（全外连接）。  



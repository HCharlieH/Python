# Python

The pandas.io.sql module provides a collection of query wrappers to both facilitate data retrieval and to reduce dependency on DB-specific API. 
Database abstraction is provided by SQLAlchemy if installed. 
In addition you will need a driver library for your database. 
Examples of such drivers are psycopg2 for PostgreSQL or pymysql for MySQL. 
For SQLite this is included in Python’s standard library by default. 



If SQLAlchemy is not installed, a fallback is only provided for sqlite (and for mysql for backwards compatibility, but this is deprecated and will be removed in a future version). 
This mode requires a Python database adapter which respect the Python DB-API.



pandas.read_sql(sql, con, index_col=None, coerce_float=True, params=None, parse_dates=None, columns=None, chunksize=None)
sql:SQL命令字符串
con：连接sql数据库的engine，一般可以用SQLalchemy或者pymysql之类的包建立
index_col: 选择某一列作为index
coerce_float:非常有用，将数字形式的字符串直接以float型读入
parse_dates:将某一列日期型字符串转换为datetime型数据，与pd.to_datetime函数功能类似。可以直接提供需要转换的列名以默认的日期形式转换，也可以用字典的格式提供列名和转换的日期格式，比如{column_name: format string}（format string："%Y:%m:%H:%M:%S"）。
columns:要选取的列。一般没啥用，因为在sql命令里面一般就指定要选择的列了
chunksize：如果提供了一个整数值，那么就会返回一个generator，每次输出的行数就是提供的值的大小。


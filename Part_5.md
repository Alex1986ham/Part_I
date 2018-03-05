# Virtual Machines

### Look up how virtual machines work

https://www.youtube.com/watch?v=djnqoEO2rLc

# SQL

### Text and string types
- text — a string of any length, like Python str or unicode types.
- char(n) — a string of exactly n characters.
- varchar(n) — a string of up to n characters.

### Numeric types
- integer — an integer value, like Python int.
- real — a floating-point value, like Python float. Accurate up to six decimal places.
- double precision — a higher-precision floating-point value. Accurate up to 15 decimal places.
- decimal — an exact decimal value.

### Date and time types
- date — a calendar date; including year, month, and day.
- time — a time of day.
- timestamp — a date and time together.
- timestamp with time zone — a timestamp that carries time zone information.

- The type timestamp with time zone can be abbreviated to timestamptz in PostgreSQL.


### Info about having statement

https://www.postgresql.org/docs/9.4/static/sql-select.html#SQL-HAVING

# Virtual Machines

### Look up how virtual machines work

https://www.youtube.com/watch?v=djnqoEO2rLc

# SQL

### Text and string types
- text — a string of any length, like Python str or unicode types.
- char(n) — a string of exactly n characters.
- varchar(n) — a string of up to n characters.

### Numeric types
- integer — an integer value, like Python int.
- real — a floating-point value, like Python float. Accurate up to six decimal places.
- double precision — a higher-precision floating-point value. Accurate up to 15 decimal places.
- decimal — an exact decimal value.

### Date and time types
- date — a calendar date; including year, month, and day.
- time — a time of day.
- timestamp — a date and time together.
- timestamp with time zone — a timestamp that carries time zone information.

- The type timestamp with time zone can be abbreviated to timestamptz in PostgreSQL.

### PSQL

- Documentation: https://www.postgresql.org/docs/9.4/static/app-psql.html

- To connect psql to a database running on the same machine (such as your VM), all you need to give it is the database name. For instance, the command psql forum

- The \d posts command shown in the video is one example — this displays the columns of the posts table.

- \dt — list all the tables in the database.

- \dt+ — list tables plus additional information (notably, how big each table is on disk).

- \H — switch between printing tables in plain text vs. HTML

#### To see any changes on the database
select * from posts \watch

#### How to replace content of a column:

# Virtual Machines

### Look up how virtual machines work

https://www.youtube.com/watch?v=djnqoEO2rLc

# SQL

### Text and string types
- text — a string of any length, like Python str or unicode types.
- char(n) — a string of exactly n characters.
- varchar(n) — a string of up to n characters.

### Numeric types
- integer — an integer value, like Python int.
- real — a floating-point value, like Python float. Accurate up to six decimal places.
- double precision — a higher-precision floating-point value. Accurate up to 15 decimal places.
- decimal — an exact decimal value.

### Date and time types
- date — a calendar date; including year, month, and day.
- time — a time of day.
- timestamp — a date and time together.
- timestamp with time zone — a timestamp that carries time zone information.

- The type timestamp with time zone can be abbreviated to timestamptz in PostgreSQL.

### PSQL

- Documentation: https://www.postgresql.org/docs/9.4/static/app-psql.html

- To connect psql to a database running on the same machine (such as your VM), all you need to give it is the database name. For instance, the command psql forum

- The \d posts command shown in the video is one example — this displays the columns of the posts table.

- \dt — list all the tables in the database.

- \dt+ — list tables plus additional information (notably, how big each table is on disk).

- \H — switch between printing tables in plain text vs. HTML

#### how to rename content of a column

update table
set content = 'cheese'
where content = '%fish%';


#### how to delete content in columns

delete from table
where content like '%cheese%';

### sample for get and post for a server to sql database

```python
import psycopg2, bleach

DBNAME = "forum"

def get_posts():
  """Return all posts from the 'database', most recent first."""
  db = psycopg2.connect(database=DBNAME)
  c = db.cursor()
  c.execute("select content, time from posts order by time desc")
  posts = c.fetchall()
  db.close()
  return posts

def add_post(content):
  """Add a post to the 'database' with the current timestamp."""
  db = psycopg2.connect(database=DBNAME)
  c = db.cursor()
  c.execute("insert into posts values (%s)", (content,))  # Better, but ...
  db.commit()
  db.close()
  ```

### Normalization of database

link: http://www.bkent.net/Doc/simple5.htm

1. rule: every row has the same number of colums
2. rule: there is a key, and everything in a row says something about the key
3. rule: facts that don't relate to the key, belong in different tables
4. rule: tables shouldn't imply relationships that don't exist

[wikipedia about normalization](https://en.wikipedia.org/wiki/Database_normalization)

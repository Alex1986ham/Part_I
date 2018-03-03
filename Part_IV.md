# Part_4
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


## SQL queries

- select max(name) from animals;

- select * from animals limit 10;

- select * from animals where species = 'orangutan' order by birthdate;

- select name from animals where species = 'orangutan' order by birthdate desc;

- select name, birthdate from animals order by name limit 10 offset 20; (offset means with which row it should start)

- select species, min(birthdate) from animals group by species;

-  select name, count(*) as num from animals
-  group by name
-  order by num desc (desc means arranged 9,8,7...)
-  limit 5;


where
The where clause expresses restrictions — filtering a table for rows that follow a particular rule. where supports equalities, inequalities, and boolean operators (among other things):
where species = 'gorilla' — return only rows that have 'gorilla' as the value of the species column.
where name >= 'George' — return only rows where the name column is alphabetically after 'George'.
where species != 'gorilla' and name != 'George' — return only rows where species isn't 'gorilla' and name isn't 'George'.
limit / offset
The limit clause sets a limit on how many rows to return in the result table. The optional offset clause says how far to skip ahead into the results. So limit 10 offset 100 will return 10 results starting with the 101st.
order by
The order by clause tells the database how to sort the results — usually according to one or more columns. So order by species, name says to sort results first by the species column, then by name within each species.
Ordering happens before limit/offset, so you can use them together to extract pages of alphabetized results. (Think of the pages of a dictionary.)

The optional desc modifier tells the database to order results in descending order — for instance from large numbers to small ones, or from Z to A.

group by
The group by clause is only used with aggregations, such as max or sum. Without a group by clause, a select statement with an aggregation will aggregate over the whole selected table(s), returning only one row. With a group by clause, it will return one row for each distinct value of the column or expression in the group by clause.

### Insert something into table

SELECT_QUERY = '''
select name, birthdate from animals where species='opossum';
'''

INSERT_QUERY = '''
insert into animals values('max','opossum','2017-09-17');
'''

### Join syntax (older one)

select name 
from animals 
join diet on animals.species = diet.species
where food = 'fish';

### Join syntax (new one)

select name
from animals, diet
where animals.species = diet.species
and diet.food = 'fish';

### Using count in joined tables

select food, count(*) as num
from animals join diet
on animals.species = diet.species
group by food
having num = 1

### More information about Taxonomy

https://en.wikipedia.org/wiki/Taxonomy_(biology)

### Biological classification

https://en.wikipedia.org/wiki/Taxonomy_(biology)

### Joining three tables together

select ordernames.name, count(*) as num
  from animals, taxonomy, ordernames
  where animals.species = taxonomy.name
    and taxonomy.t_order = ordernames.t_order
  group by ordernames.name
  order by num desc


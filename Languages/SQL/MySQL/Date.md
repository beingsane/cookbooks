## Invert date format

	UPDATE table_name SET column_name = DATE_FORMAT(STR_TO_DATE(column_name, '%d/%m/%Y'), '%Y-%m-%d');

## Where examples

Between

	SELECT * FROM table_name WHERE column_name BETWEEN ‘2010-11-11’ AND ‘2010-11-30’

Simple compare

	SELECT * FROM table_name WHERE YEAR(column_name) = ‘2010’

Having

	SELECT * from table_name HAVING column_name > CURDATE()

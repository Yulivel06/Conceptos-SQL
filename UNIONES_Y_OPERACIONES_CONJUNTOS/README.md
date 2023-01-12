Primary key: columna que identifica de manera exclusiva los registros de una columna

Uniones internas en SQL (crecen horizontal)

INNER JOIN: Busca registro en ambas tablas con los mismos valores en el campo clave, id 

![enter image description here](https://github.com/Yulivel06/Conceptos-SQL/blob/master/UNIONES_Y_OPERACIONES_CONJUNTOS/inner%20join.png)

SELECT ----- seleccionamos las columnas que queremos ver
FROM ------- Tabla de la izquiera, seguida de la palabra clave INNER JOIN mas la tabla de la derecha
Especificamos el campo para que coincidan las tablas, utilizando la palabra clave ON

uniones externas, LEFT-RIGHT- FULL JOIN:

LEFT JOIN conserva todos los registros de la tabla izquierda, así como valroes nulos para los valores de la 
derecha donde no hay coincidencia en tabla derecha. Los valores id 5 y 6 que no aparecen en la left_table 
no aparecen en ningun lado. 

RIGHT JOIN (poco usado): se conservan todos los registros de la tabla right_table, se devulven valores nulos para el campo left_value
en los registros donde no encuentra coincidencia
 
FULL JOIN (Union completa): devuelve todos los Id independiente si existe o no una coincidencia con la tabla que se este uniendo 
regresa valores faltantes cuando no encuntra una coincidencia 

Tambien se puede usar FULL OUTER JOIN 


Uniones cruzadas (cross join): crean todas las uniones posibles de dos tablas.

el resultado de Cross join son las nueve combinaciones del id 

No se especifica ON o USING

Autouniones (SELF JOIN): Una tabla se une consigo misma
Se utiliza para comparar valores de parte de una tabla con otros valores dentro de la misma tabla
Para hacer una consulta con autouniones no existe una sintaxis dedicadas, es decir no podemos escribir simplemente SELF JOIN
para esto es necesario crear un alias 
el campo vital es establecer los campos de union que usamos para hacer coincidir la tabla con ella misma. 


En lugar de comparar y fusionar tablas al a izquiera y a la derecha, apila los campos uno encima del otro 

--OPERACIONES DE CONJUNTOS (UNION, INTERSECT, EXCEPT) (CRECE VERTICALMENTE)
UNION -UNION ALL
union: devuelve todos los registros de cada tabla, si dos registros son identicos UNION solo los devuelve una vez.
union all: incluye registros duplicados 

Nota: el numero de columnas seleccionadas y sus respectivos tipso de datos deben ser identicos. 
el resultado solo usara nombres de campos o alias de la primera instruccion select en la consulta. 

intersect solo devuleve registros comunes una vez, mientras que inner join devovlera valores duplicados. 
inner join agrega mas columna al conjunto de resultados 


EXCEPT: Nos permite indentificar los registros que presentes en una tabla, pero no en la otra,
es decir, conserva solo los registros de la tabla de la izquiera que no esten presenten en la tabla derecha 

# 5 y 6: SQL

**Es declarativo:** hacemos las consultas sin describir como se computa

- **DDL:**
    - Lenguaje de definición de datos:
        - Crear y modificar tablas, atributos y llaves
- DML:
    - Lenguaje de manipulación de datos:
        - Consultar tablas
        - Insertar, eliminar, modificar tuplas

En este caso PostgreSQL es un motor RDBMS

Se pueden hacer distintas operaciones de Algebra Relacional

### Eliminar con llave foránea (soluciones):

Caso en que queramos eliminar algo de una tabla R y de esta depende una tabla S

1. No permitir la eliminación (default en SQL)
2. Borrar también en la tupla en S: `FOREIGN KEY(a) REFERENCES R ON DELETE CASCADE, …)` 
3. Dejar el valor dependiente de S como null: `FOREIGN KEY(a) REFERENCES R ON DELETE SET NULL, …)`

### s LIKE p

“S es como P” donde p es un patrón. Se puede usar:

- `%` : Cualquier secuencia de caracteres
- `_` : Cualquier caracter (solo uno)
    - Ej: `WHERE name LIKE '%Potter%'`

### Operador `DISTINCT`:

- Es un `NOT`

## Agregación

- `SELECT AVG(precio) ...` ⇒ También se puede usar SUM, MIN, MAX, COUNT, ETC

### Consultas Anidadas

Hasta ahora una consulta en SQL se veía más o menos así

```sql
SELECT <S>
FROM R1, …, Rn
WHERE<Condición 1>
GROUP BY a1, …, ak
HAVING <Condición 2>
```

Como aparece en la ultima linea, se suma `HAVING`

También podemos hacer otra consulta dentro de la consulta (por ejemplo hacer una consulta dentro de un where y que entregue un escalar que lo usaremos en esa condición), si está no entrega un escalar podemos usar: `IN`, `ALL`, `ANY`, `EXISTS`

### NULLs

- Cualquier operación aritmetica con `NULL` da como resultado `NULL`
- Hacer una operación de logica con un `null` da como resultado `unknown`
- En funciones de agregación se ignoran los nulos, después se computa el resultado (excepto con `COUNT(*)`)

### JOINS

- https://blog.jooq.org/say-no-to-venn-diagrams-when-explaining-joins/
- `JOIN` = `INNER JOIN`
- LEFT y RIGHT JOIN mantiene las tuplas de las respectivas tablas que no tienen correspondencia
    - El `FULL OUTER JOIN` mantiene todas las tuplas que no tienen correspondencia
    
    ![Untitled](fotos/Clase5y6.png)
    

## Conexión con python

- Para PostgreSQL se usa la librería `psycopg2`
- Crear una conexión (funciones de la libreria) y a partir de esa conexión crear un cursor (no explican lo que es)
- Se ejecutan las consultas con `cursor.execute("...")` (es un método del cursor)
    - Si hacemos cambios en una BBDD, no olvidar hacer `connection.commit()` y `connection.close()`
- Para ver lo que nos entrega la DBMS se usa:
    - `cur.fetchone()`: tupla a tupla
    - `cur.fetchall()`: entrega todas las tuplas en una lista
- Para insertar variables dentro de las consultas, se pone `%s` dentro de la consulta y las variables como una tupla o diccionario en el segundo argumento del método `execute`
    - NUNCA CONCATENAR O HACER F-STRINGS: pueden causar inyecciones sql

## Observaciones:

- Si nos olvidamos de poner `WHERE` en una consulta `UPDATE`o `DELETE FROM` se hace la operación para todas las tuplas
- Las `||` sirven para crear un string de acuerdo a otras tuplas
- Se suma a las consultas `GROUP BY ...` sirve para agrupar por los valores repetidos de la columna que se le entregó
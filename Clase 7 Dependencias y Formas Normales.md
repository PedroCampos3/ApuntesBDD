# Clase 7: Dependencias y Formas Normales

Ejemplo de mala normalización:

Imaginemos que tenemos una tabla de empleados en una empresa, en esta tabla tenemos Empleados, Jefes y el departamento al que pertenece

- Problemas:
    - Si hay un jefe tiene un solo empleado y este renuncia, el jefe deja de aparecer en la base de datos también
    - Si se contrata a alguien pero no se le a asignado a nada, tampoco puede aparecer en la base de datos
    - Redundancia de datos
    - **Al final** el problema es que la asociación entre jefes y empleados está en la misma tabla con la que se asocian a departamentos
- Hay varias observaciones sobre dependencia en el pdf que no anotaré, porque son intiuitivas
- Hay una estandarización sobre las dependencias que hay que seguir para evitar los problemas que mencionamos en el ejemplo, estás son las Formas normales

### 1NF

- No puede haber una relación (tupla) como elemento de una tupla
    - Además, cada registro debe ser único (Tiene que haber llave primaria)
    - **Solución:** crear otra tabla que tenga a la relación y añadirle el id de la “tabla padre”

### 2NF

- Está en 1NF
- Ninguna llave candidata es funcionalmente dependiente de otra llave candidata
    - No tiene dependencia parciales

…

(como no entendí mucho me limitaré a decir)

### BCNF

- Está en 3NF
- Como ninguna NF revisa las llaves, esta lo hace.
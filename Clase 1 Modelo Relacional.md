# 1. Modelo Relacional

- ¿Como se almacenan los datos en este modelo?
    
    Como en una tabla
    
    - ¿Como uno se refiere a cada parte de la tabla?
        - Relación
            
            Tabla
            
        - Argumentos
            
            Columnas
            
        - Tuplas
            
            Filas
            
        - Esquema
            
            A la forma `Tabla(arg1, arg2, arg3...)`
            
        - Instancias
            
            A cuando a un esquema se le agregan las tuplas
            
    - ¿Que son las restricciones de Integridad?
        
        Son restricciones que uno le pone a una tabla, para que (por ejemplo) no se repita un elemento
        
    - ¿Que nos sirve para identificar una relación?
        
        Las llaves
        
        - ¿De que tipos hay?
            - SuperKey
                
                Conjuntos de atributos que **podrían** identificar una tupla
                
            - Llave Candidata (o minimal)
                
                Atributos que nos sirven para identificar una tupla
                
            - Llave Primaria
                
                El atributo que usaremos para identificar. Se subraya
                
            - Surrogate Key
                
                Agregamos un atributo para hacer una llave generica que nos pueda servir más. Ejemplo: ID
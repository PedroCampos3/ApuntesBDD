# 3. Modelo E/R

- ¿Como se llaman los tipos de elementos de un diagrama
    
    ¿Con que forma se dibujan y que son?
    
    - Relación
        - Rombo
        - Otra tabla que relaciona dos tablas (Con sus llaves)
    - Atributo
        - Ovalo
        - Los atributos de una tabla
    - Entidad
        - Rectángulo
        - Una tabla
        - ¿Que debe y no tener obligatoriamente?
            - Debe tener una llave
            - Pero puede pasar el caso que la entidad no tenga una, como se llaman en este caso.
                - Entidad debil
                - ¿Como identifico una tupla de esta entidad?
                    - Con un atributo de esta llamado llave parcial y la llave de otra entidad
    - ¿Que significa la flecha en la ariedad?
        
        Que tiene a lo más 1 de lo que está apuntando:
        
        [Producto]→<fabricado>-[empresa] // El producto es fabricado a lo más por una empresa
        
    - Jerarquía de clases
        - Super y sub-clases
        - Triangulo (IsA)
        - Una sub-clase hereda los atributos de su Super-clase
# 2. Algebra Relacional

- ¿Que operaciones existen en Algebra Relacional?
    
    $\pi, \sigma, \cup, \cap, \Join,\rho, \times$
    
    - ¿Como se llama a la operación $\pi_{something}$?
        
        Proyección 
        
        - ¿Para que sirve?
            
            Entrega un tupla con los elementos de un atributo de una instancia (Filtra los elemento de una columna de una tabla)
            
    - ¿Como se llama la operación $\sigma_{something}$?
        
        Selección 
        
        - ¿Para que sirve?
            
            Entrega las tuplas que coincidan con lo que se le pide
            
            - ¿Que operandos puedo usar?
                
                $>, \geq, <, \leq, =, \land, \lor$
                
    - ¿Como se llama las operaciones $\cup$ y $\cap$?
        
        Unión e Intersección
        
        Es intuitivo para que sirven
        
    - ¿Como se llama $\times$?
        
        Producto Cruz
        
        - ¿Que hace?
            
            Combina 2 instancias adjuntando la primera tupla de la primera con todas de la segunda y así con todas las tuplas de la primera instancia
            
    - ¿Como se llama $\Join_{something}$?
        
        Join
        
        - ¿Para que sirve?
            
            Es el resultado de hacer $\times$ y después $\sigma$
            
    - ¿Para que sirve $\rho$?
        
        Para cambiar el nombre de los argumentos de una relación
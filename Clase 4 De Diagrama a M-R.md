# 4. De Diagrama a M. R.

### Tablas para las relaciones entre entidades:

[no entendí nada]

### Jerarquía de clases (soluciones):

- Crear tablas solo para las subclases
- Hacer tabla para la superclase haciendo joins en las consultas
- Eliminar la jerarquía

### Entidades Débiles (soluciones)

- Si hay redundancia: Directamente no crear la tabla relación

## Observaciones:

1. Flechas:
    1. **GRUESA:** *A lo menos UNO*
    2. **DELGADA**: *a lo menos CERO*
2. Restricciones de Seguridad en SQL:
    1. Con CHECK
        1. `CHECK( precio BETWEEN 1000 AND 10000 ),`
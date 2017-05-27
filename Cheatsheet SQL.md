## Chuleta de SQL

#### Crear BD

``` sql
CREATE DATABASE nombre;
```

#### Crear tabla
``` sql
CREATE TABLE tabla(
  columna tipo PRIMARY KEY,
  columna tipo,
  columna tipo REFERENCES otratabla(otracolumna),
  ...
);
```
#### Modificar tabla
``` sql
ALTER TABLE tabla
ADD (CONSTRAINT fk_orders1) FOREIGN KEY (Customer_SID) REFERENCES CUSTOMER (SID);
```
#### Insertar elementos en tabla
``` sql
INSERT INTO tabla (columna, columna2, ...)
VALUES (valor1, valor2, ...);
```

#### Eliminar tabla
```sql
DROP TABLE tabla;
```

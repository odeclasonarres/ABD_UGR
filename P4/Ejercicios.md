### EJERCICIOS PRÁCTICA 4

#### Tanda 1(página 10 diapositivas)
##### 1.Encontrar la localización del fichero de control y y su nombre, usando V$controlfile, V$parameter y la Consola de Administración.
```sql

```

##### 2.¿Qué sucede si se arranca la BD sin ficheros de control? 
```sql

```


3.Crear el directorio /databases/app/ejercicios/control_files 
```sql

```

4.Poner en el directorio /databases/app/ejercicios/control_files una copia del fichero de control, asegurando que el servidor la tenga actualizada constantemente.
```sql

```

#### Tanda 2(página 27 diapositivas)
##### 1.Listar número y localización de los log files y los grupos y miembros que hay.
```sql

```

##### 2.Encontrar el modo actual de redo.
```sql

```

##### 3.añadir un miembro más a los grupos de redo log y verficar resultado. 
```sql

```

##### 4.Crear un nuevo grupo de redo log.
```sql

```

#### Tanda 3(página 48 diapositivas)
##### 1. Crear los sisguientes tablespaces permanentes:
##### - DATA con extensiones mínimas de 500 K, incluyendo la inicial.
```sql

```
##### - RONLY de solo lectura y obligar a que lo sea. Crear una tabla en él.
```sql

```

##### 2.Ampliar a 2M el tamaño de DATA01.dbf.
```sql

```

##### 3.Crear una tabla en DATA.
```sql

```

##### 4.Cambiar el nombre al datafile de DATA.
```sql

```

##### 5.Eliminar los tablespaces creados.
```sql

```

#### Tanda 4(página 61 diapositivas)
##### 1.Retocar y ejecutar el script cr_segs.sql
```sql

```

##### 2.Identificar los distintos tipos de segmentos que hay en la BD.
```sql

```

##### 3.Averiguar qué segmentos están a menos de 5 extensiones del límite permitido.
```sql

```

##### 4.¿Qué ficheros contienen datos de la tabla EMP?(dba_extents-dba_data_files).






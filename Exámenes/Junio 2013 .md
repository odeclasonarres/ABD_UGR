### Cuestionario
#### 1. ¿Qué pasará si todos los miembros del grupo log actual quedaran inaccesibles al proceso LGWR cuando se va a escribir en ellos?
 - Se detendrı́a la instancia de la BD.
 - Se eliminarı́a el grupo log actual.
 - El DBA tendrı́a que forzar un log “switch”.
 - El grupo log se ignorarı́a por el LGWR y los datos a archivar se escribirı́an en el grupo siguiente.

#### 2. Usando SQL*Plus, ¿cómo podrı́as visualizar los valores actuales para la “spool area”?
 - Abriendo el init.ora.
 - Usando el comando SET.
 - Usando el comando SHOW.
 - Usando el comando DESCRIBE.
 - Consultando el diccionario/catálogo de la BD.

#### 3. ¿Cuáles son los pasos correctos a seguir para resolver un error del S.O. causado por un espacio de disco insuficiente mientras se crea una base de datos?
 - Reservar espacio para los “datafiles” usando el comando ALTER DATABASE.
 - Detener la instancia de BD, modificar el tamaño del bloque de BD y reiniciar la instancia.
 - Redimensionar los “datafiles” creados por la sentencia CREATE DATABASE usando la sentencia ALTER DATABASE.
 - Detener la instancia de BD, eliminar todos los archivos creados por la sentencia CREATE DATABASE, corregir el problema e intentar crear la BD de nuevo.

#### 4. ¿Qué dos vistas deberı́as consultar para visualizar los nombres y localización de los archivos de control para la BD oradba? Elige dos:
 - V$INSTANCE
 - V$DATABASE
 - V$SYSTEM PARAMETER
 - V$CONTROLFILE
 - V$CONTROLFILE RECORD SECTION

### Supuestos prácticos
#### 1. Cread el “tablespace” de tipo permanente EXAMEN asociándole el archivo de datos: examen01.dbf, alojado en C:\oracle\oradata\oradba, con 10 MB de tamaño y con ampliación automática de tamaño en incrementos de 100K hasta un máximo de 100MB. Guardad en el archivo de texto C:\creatablespace.sql las sentencias SQL mediante las cuales se crearı́an el “tablespace” y archivo de datos mencionados.
```sql

```

#### 2. Haz un “backup” en caliente (“on-line”) del archivo de datos examen01.dbf en C:\oracle\. Eliminad el archivo C:\oracle\oradata\oradba\examen01.dbf y después realizar una recuperación de dicho archivo a partir de la copia alma- cenada en C:\oracle\. Guardad en el archivo de texto C:\backuptablespace.sql las sentencias SQL mediante las cuales se realiza lo anterior.
```sql

```

#### 3. Cread el usuario exa1 con clave exa1, con cuota 1Mb en el “tablespace” USERS(su “tablespace” por defecto) y con “tablespace” temporal TEMP, asignadle los roles CONNECT y RESOURCE y el privilegio de sistema que le permita crear tablas en cualquier esquema. Estableced que tenga que cambiar su clave en cuanto ingrese por primera vez y que ésta expire a los 30 dı́as (habrá de crearse un “profile”). Guardad en el archivo de texto C:\creausuario.sql las sentencias SQL mediante las cuales se crea lo anterior.
```sql

```
### Cuestionario
#### 1. Necesita exportar la tabla PEDIDOS de la BD PROD que está abierta y en ese momento no tiene ningún usuario conectado. ¿Como podrı́as la BD en modo restringido?
 - Usando la sentencia ALTER SYSTEM con la opción KILL SESSION.
 - Usando la sentencia ALTER DATABASE con la opción RESTRICTED.
 - Usando la sentencia ALTER SYSTEM con la opción RESTRICTED SESSION.
 - Usando la sentencia ALTER SESSION con la opción RESTRICTED SESSION.

#### 2. Como Administrador desea realizar tareas de administración sin usar un fichero de “password”. ¿Como deberı́a entonces establecer un método de autentificación para el ABD?
 - Conceder el role DBA a tu cuenta del sistema operativo.
 - Ejecutar la utilidad de “password”, establecer el parámetro REMOTE LOGIN PASSWORDFILE a ‘SHARED’ y usar ‘CONNECT / AS SYSDBA’ para conectarte a la BD.
 - Establecer autentificación por sistema operativo, establecer el parámetro REMOTE LOGIN PASSWORDFILE a ‘NONE’ y usar ‘CONNECT / AS SYSDBA’ para conectarte a la BD.
 - Ejecutar la utilidad de “password”, establecer el parámetro REMOTE LOGIN PASSWORDFILE a ‘EXCLUSIVE’ y usar ‘CONNECT SYS/<password> AS SYSDBA’ para conectarte a la BD.

#### 3. El DBA concede el privilegio CREATE TABLE a LYNN con la opción ADMIN OPTION. LYNN crea la tabla EMP y concede el privilegio CREATE TABLE a SCOTT. SCOTT crea la tabla DEPT y concede a LYNN el privilegio SELECT sobre esa tabla. ¿Que pasa si el DBA retira a LYNN el privilegio CREATE TABLE?
 - SCOTT mantendrá el privilegio CREATE TABLE y las tablas se conservarán.
 - SCOTT mantendrá el privilegio CREATE TABLE y LYNN perderá el privilegio SELECT.
 - SCOTT perderá el privilegio CREATE TABLE y las tablas DEPT y EMP se eliminarán.
 - SCOTT perderá el privilegio CREATE TABLE y las tablas DEPT y EMP se conservarán.
 - SCOTT mantendrá el privilegio CREATE TABLE, la tabla EMP se eliminará y la tabla DEPT se conservará.f) SCOTT perderá el privilegio CREATE TABLE, las tablas DEPT y EMP se eliminarán y LYNN perderá el privilegio SELECT.

#### 4. Tienes creada la BD PROD con un sólo archivo de control. ¿Que habrı́as de hacer para multiplexar ese archivo de control?
 - Usar la sentencia ALTER DATABASE para editar el parámetro CONTROL FILES.
 - Detener la BD, editar el parámetro CONTROL FILES e iniciar la BD.
 - Usar la sentencia ALTER DATABASE para copiar el archivo de control existente a un dispositivo diferente y editar el parámetro CONTROL FILES.
 - Detener la BD, usar los comandos del sistema operativo para copiar el archivo de control existente a un dispositivo diferente, editar el parámetro CONTROL FILES e iniciar la BD.

### Supuestos prácticos
#### 1. Cread el usuario exa1 con clave exa1, que se le obligue a cambiar la clave la primera vez que se conecte, con cuota 1Mb en el “tablespace” USERS (su “tablespace” por defecto) y con “tablespace” temporal TEMP, asignadle los roles CONNECT y RESOURCE. Estableced que el sistema desconecte las sesiones de este usuario después de 30 minutos de inactividad (habrá de crearse un “profile”). Guardad en el archivo de texto C:\creausuario.sql las sentencias SQL mediante las cuales se crea lo anterior.
```sql

```

#### 2. Cread el “tablespace” de tipo permanente EXAMEN asociándole el archivo de datos: examen01.dbf, alojado en C:\oracle\oradata\oradba, con 5 MB de tamaño y con ampliación automática de tamaño en incrementos de 200K hasta un máximo de 200MB. Haz un backup en “frio” de dicho archivo en C:\oracle\backup\oradba. Guardad en el archivo C:\creatablespace.sql las sentencias SQL mediante las cuales se crearı́an el “tablespace”, el archivo de datos y el backup mencionados.
```sql

```

#### 3. Moved el archivo de datos examen01.dbf creado en el ejercicio anterior al directorio C:\oracle\oradata\nuevo\oradba, dejando la instancia de BD abierta y el “tablespace” EXAMEN accesible después de ese cambio. Guardad en el archivo de texto C:\muevearchivo.sql las sentencias SQL mediante las cuales se realiza lo anterior.
```sql

```
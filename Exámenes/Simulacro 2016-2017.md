## Simulacro de examen 2016-2017


### CUESTIONARIOS

##### 1.Tienes creada la BD PROD con un sólo archivo de control. ¿Que habrías de hacer para multiplexar ese archivo de control?
 - **Detener la BD, usar los comandos del sistema operativo para copiar el archivo de control existente a un dispositivo diferente, editar el parámetro CONTROL_FILES e iniciar la BD**
 - Detener la BD, editar el parámetro CONTROL_FILES e iniciar la BD
 - Usar la sentencia ALTER DATABASE para editar el parámetro CONTROL_FILES
 - Usar la sentencia ALTER DATABASE para copiar el archivo de control existente a un dispositivo diferente y editar el parámetro CONTROL_FILES

##### 2.Si ejecutas desde SQL*Plus la sentencia: ALTER TABLESPACE data_02 RENAME DATAFILE ‘d:\data02.dbf’ TO ‘e:\data02.dbf’;  ¿Qué tarea se ha realizado?
 - Creación de un archivo nuevo en el disco e: y actualización del diccionario de datos
 - Renombrar físicamente un archivo y actualización del diccionario de datos
 - Renombrado de un tablespace
 - Mover físicamente un archivo de datos del disco d: al e:
 - **Actualización del diccionario de datos si el archivo destino existe**

##### 3.La BD PROD tiene cuatro grupos de archivos "redo log" con dos miembros en cada grupo. ¿Cómo podría añadir un nuevo miembro a cada uno de los grupos existentes?
 - Deteniendo la instancia de BD y usando el comando ALTER DATABASE RENAME FILE 
 - **Usando el comando ALTER DATABASE ADD LOGFILE MEMBER**
 - Deteniendo la instancia de BD, modificando el archivo de parámetros y reiniciando la instancia
 - Usando el comando ALTER DATABASE ADD LOGFILE GROUP
 - Eliminando los grupos y recreándolos a continuación
 - Deteniendo la instancia de BD y copiando los archivos log usando comandos del sistema operativo

##### 4.La cuenta de usuario JANE ha sido bloqueada por el sistema. ¿Cómo desbloquearías dicha cuenta sin eliminar los objetos de ese esquema?
 - Usando la sentencia ALTER USER con la cláusula ACCOUNT.
 - Usando la sentencia ALTER SYSTEM UNLOCK ACCOUNT.
 - Usando la sentencia DROP USER con la cláusula CASCADE.
 - Usando la sentencia ALTER USER con la cláusula QUOTA.
 - Modificando la clave del usuario JANE

### EJERCICIOS PRÁCTICOS

##### Ejercicio 1
``` sql
//Crear usuario 1
create user examen1 identified by examen1 default tablespace USERS temporary tablespace TEMP quota unlimited on USERS password expire;
//Asignar roles
grant CONNECT to examen1;
grant RESOURCE to examen1;

//Crear usuario 1
create user examen2 identified by examen2 default tablespace USERS temporary tablespace TEMP quota unlimited on USERS;
grant CONNECT to examen2;
grant RESOURCE to examen2;

//Conectar como examen1, pide que cambies la contraseña
connect examen1;

//Crear tabla
create table tabla_examen1(primera NUMBER PRIMARY KEY); 

//permitir que 
grant insert on tabla_examen1 to examen2;

//Conectar como examen2 en otra terminal
connect examen1;

//examen2 inserta tupla
insert into examen1.tabla_examen1(primera) values(15);
```

//EJERCICIO 2
//Crear el tablespace
create tablespace examen datafile '/databases/app/oracle/examen01.dbf' size 20M PERMANENT ONLINE;

//Añadir segundo fichero de datos
alter tablespace examen add datafile '/databases/app/oracle/examen02.dbf' size 20M;

//Cambiar la ubicación de los archivos
//poner offline
alter tablespace examen OFFLINE;
//mover archivos(fuera de sql)
cp /databases/app/oracle/examen01.dbf /databases/app/oracle/oradata/oradba/examen01.dbf
cp /databases/app/oracle/examen02.dbf /databases/app/oracle/oradata/oradba/examen02.dbf
//alterar el tablespace
alter tablespace examen rename datafile '/databases/app/oracle/examen02.dbf' to '/databases/app/oracle/oradata/oradba/examen02.dbf';
alter tablespace examen rename datafile '/databases/app/oracle/examen01.dbf' to '/databases/app/oracle/oradata/oradba/examen01.dbf';
//poner online el tablespace
alter tablespace examen online;
//borrar archivos 
rm /databases/app/oracle/examen01.dbf
rm /databases/app/oracle/examen02.dbf


//EJERCICIO 3
//Tiramos la bd

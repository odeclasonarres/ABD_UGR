### EJERCICIOS PRÁCTICA 5

#### Tanda 1(página 15 diapositivas)
##### 1. Crear el usuario Bob con password ALONG, asegurando que no utilice espacio en SYSTEM y que no sobrepase 1M en eltablespace USERS. Dejar que se conecte.
```sql
create user bob identified by ALONG default tablespace users temporary tablespace temp quota 0M on system quota 1M on users;
grant connect to bob;
```
##### 2. Crear el usuario Kay con password Mary asegurando que los objetos y el espacio temporal necesarios no sean de SYSTEM. Asignar cuota ilimitada en el tb de datos.
```sql
create user kay identified by Mary default tablespace users temporary tablespace temp quota unlimited on system;
```
##### 3. Copiar la tabla EMP del ususario SCOTT en la cuenta de Kay.
```sql 
create table kay.emp as select * from scott.emp;
```

##### 4. Mostrar la información sobre Bob y Kay y sobre sus límites de espacio en los tablespaces correspondientes.
```sql
select username, tablespace_name, max_bytes from dba_ts_quotas where username in ('BOB', 'KAY');
```

#### Tanda 2(página 36 diapositivas)
##### 1. Crear un perfil "nuevo" que permita dos sesiones concurrentes por usuario y un máx. de un minuto de inactividad. Asignárselo a Bob.
```sql
create profile nuevo limit
sessions_per_user 2
idle_time 1;
```
##### 2. Conectarse como Bob más de dos veces
```sql

```
##### 3. Asignar los siguientes límites al perfil default:
##### - Bloquear la cuenta tras dos intentos fallidos.
##### - La password expira a los 30 días.
##### - La password tiene un periodo de gracia de 5 días para ser cambiada.
```sql
alter profile default limit 2 failed_login_attempts password_life_time 30 password_grace_time 5;
```
##### Comprobar resultados.
```sql
select * from dba_profiles where profile='DEFAULT' and resource_type='PASSWORD';
```

##### 4. Alterar el perfil por defecto para que la password no expire nunca.
```sql
alter profile default limit password_life_time unlimited;
```

#### Tanda 3(páginas 53-54 diapositivas)
##### 1. Permitir a Kay conectarse a la BD y crear tablas propias
```sql

```

##### 2. Conectar como Kay y crear la tabla DEPT(ejecutar script ulcase1.sql)
```sql

```

##### 3. Conectar como sys y rellenar las tablas de Kay con las de scott.EMP y scott.DEPT.
```sql

```

##### 4. Conceder a Bob(como sys) el privilegio de consultar la tabla EMP de Kay. Hacerlo como Kay y conceder grant option.
```sql

```

##### 5. Consultar los cambios en el catálogo.
```sql

```

##### 6. Crear el usuario Todd con capacidad de conexión.
```sql

```

##### 7. Conectar como Bob y permitir a Todd acceder a la tabla EMP de Kay.
```sql

```

##### 8. Conectar como Kay y quitarle el privilegio a Bob de consultar su tabla EMP.
```sql

```

##### 9. Conectar como Todd y consultar la tabla EMP de Kay.
```sql

```

#### Tanda 4(página 66 diapositivas)
##### 1. Listar todos los privilegios que tiene el role RESOURCE.
```sql

```

##### 2. Crear el role DEV para crear tablas, crear vistas y consultar la tabla EMP de Kay.
```sql

```

##### 3. Conceder a Bob los roles DEV y RESOURCE, pero habilitarle sólo RESOURCE cuando se conecte.
```sql

```

##### 4. Conceder a Bob el role que le permite consultar todo el catálogo. Comprobar alcance.
```sql

```
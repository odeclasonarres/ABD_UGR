## Chuleta inicio y derribo BD y servicios.

#### 1.Iniciar servicios y BD
``` sql
// Iniciar listener
      lsnrctl start

// Iniciar BD
      sqlplus /nolog

// Conectar (En la SQLShell)
      connec sys as sysdba
      startup
      exit

// Iniciar Oracle Enterprise Manager(opcional)
      emctl start dbconsole
```

#### 2.Detener BD y servicios
``` sql
// Detener Oracle Enterprise Manager(opcional)
    emctl stop dbconsole

// Cerrar y desmontar BD
      sqlplus /nolog

// En la SQLShell
      shutdown immediate
      exit

// Detener listener
      lsnrctl stop
```

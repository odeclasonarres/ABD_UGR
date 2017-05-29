### EJERCICIOS PRÁCTICA 5

#### Tanda 1
creacion de 
1:
create user bob identified by ALONG default tablespace users
  2  temporary tablespace temp
  3  quota 0M on system
  4  quota 1M on users;

grant connect to bob;

2:
create user kay identified by Mary
  2  default tablespace users
  3  temporary tablespace temp
  4  quota unlimited on system;

3: 
create table kay.emp as select * from scott.emp;

4: 
select username, tablespace_name, max_bytes from dba_ts_quotas where username in ('BOB', 'KAY');


#### Tanda 2
1: create profile nuevo limit
sessions_per_user 2
idle_time 1;


3:
alter profile default limit
  2  failed_login_attempts 2
  3  password_life_time 30
  4  password_grace_time 5;

select * from dba_profiles where profile='DEFAULT' and resource_type='PASSWORD';


4:
alter profile default limit
  2  password_life_time unlimited;

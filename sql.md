### Mysqlsh Note
When in mysqlsh, first need to connect to the SQL server.
```
\connect [user]@[ip_address]
```
In local, it's like
```
\c root@localhost
```
Then if want to run .sql file, run :
```
\. file.sql ;
```

#### Local infile
If you want to load file into database from client side, you have to set `local_infile` on both on client and server side.
Run command below : 
```sql
SHOW GLOBAL VARIABLES LIKE 'local_infile';
SET GLOBAL local_infile = 'ON';
SHOW GLOBAL VARIABLES LIKE 'local_infile';
```
to check and set the variable.
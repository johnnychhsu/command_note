## Command note
Here I save some useful command for me, help to improve my working efficiency.

### Using jupyter lab on remote server
First start up the jupyter server on remote machine
```
jupyter lab --port=9000 --no-browser
```
Then run this on local machine 
```
ssh -N -f -L [local_port]:localhost:[remote_port] [User]@remote_machine
```

### Python Tip
ord() : take str as input, output its ascii.
chr() : take number as input, output its str.

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
i
### Git Alias Command
This is useful. Save time.
```
git config --global alias.st status
git config --global alias.ci commit
```

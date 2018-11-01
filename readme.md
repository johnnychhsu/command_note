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

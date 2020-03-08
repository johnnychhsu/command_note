### SSH key to server
1. Generate ssh key on local machine by 
```
ssh-keygen -t rsa -b 4096 -C "user@mail"
```
Then add this key to local ssh-agent
```
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa
```
Then copy the id_rsa.pub onto the server authorized_key file.
```
cat id_rsa.pub >> authorized_key
```

### Terminal shorcut
`ctrl+E` moves cursor to the end of the line.
`ctrl+A` moves cursor to the begining of the line.
`ctrl+U` clear the lines before the cursor.
`ctrl+R` search the previous command.
`option+arrow` moves cursor to the next/previous word.

### check open file
1. List open file
```
lsof
```
2. List specific user's open file
```
lsof -u user
```

### Check open port
**list open port**
```command
sudo lsof -i
```

**Kill TCP connection**
```command
# Kill all ftp connection
tcpkill -i eth0 port 21

# Kill all packets from designated address
tcpkill hot 192.168.1.2
```

# Change locale environment variable
First check current setting
```
locale
```
Then add what we want as a file contain following as example to `/var/lib/locales/supported.d/locale`
```
zh_TW.UTF-8 UTF-8
en_US.UTF-8 UTF-8
```
We can use `sudo update-locale LC_ALL="zh_TW.UTF-8"` to update.

#### Command 
1. [40 useful commands](https://vitux.com/40-most-used-ubuntu-commands/)

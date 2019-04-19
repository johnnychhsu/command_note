### Git
#### Alias
This is useful. Save time.
```
git config --global alias.st status
git config --global alias.ci commit
```
We can modify these settings in `~/.gitconfig`:
```command
[alias]
    lg = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
    co = checkout
```

#### Branch
1. Delete branch
`git branch -d branch_name`
# Git多账号设置
## SSH config File
在.ssh下新建一个config file
```
`# 配置github.com
Host github.com
    HostName github.com
    IdentityFile ~/.ssh/id_rsa_github
    PreferredAuthentications publickey
    User [xxxx]

# 配置gitlab.xxx.com
Host git.xxx.net
    HostName git.xxx.net
    IdentityFile ~/.ssh/id_rsa_xxx
    PreferredAuthentications publickey
    User [xxxx]
```

## Add new ssh private key to SSH cache
```
ssh-add ~/.ssh/id_rsa_xxx
```

## Upload new SSH public key to Account

## Test Connection
```
ssh -T git@gitlab
```

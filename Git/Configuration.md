# Git

## Setting your username & email 
```
$ git config --global user.name "John Doe"
$ git config --global user.email "johndoe@example.com"
```

## Setting Credential

Store your password in a open-text file (without any encryption)
```
$ git config --global credential.helper store
```

Store your password in memory for some time:
```
$ git config --global credential.helper cache
```

By default, Git will cache your password for 15 minutes.

To change the default password cache timeout, enter the following:

Set the cache to timeout after 1 hour (setting is in seconds)
```
$ git config --global credential.helper 'cache --timeout=3600'
```

## Checking all configuration variables.
```
$ git config --list
```

## Generating a new SSH key
```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

## Adding a new SSH key to your GitHub account
```
$ cat .ssh/id_rsa.pub
```

# Reference

- [Authenticating to github](https://help.github.com/en/github/authenticating-to-github)
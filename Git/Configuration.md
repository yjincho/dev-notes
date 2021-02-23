# Git

## Setting your username & email 
```
$ git config --global user.name "John Doe"
$ git config --global user.email "johndoe@example.com"
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
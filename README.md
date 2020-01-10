# PPA

Debian repository for my packages

## Installation

Add the PPA's key and source list

```bash
curl -s --compressed "https://addisonklinke.github.io/ppa/KEY.gpg" | sudo apt-key add -
sudo curl -s --compressed -o /etc/apt/sources.list.d/addisonklinke.list "https://addisonklinke.github.io/ppa/addisonklinke.list"
sudo apt update
```

Select your desired packages

```bash
sudo apt install package1 package2 package3
```

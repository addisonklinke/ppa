# PPA

Debian repository for my packages

## Packages

* **[bash-utils](https://github.com/addisonklinke/bash-utilities):** Custom bash commands for added shell functionality

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

## Adding Packages

Place the deb file inside the repository's root directory, and then run 

```bash
EMAIL=abc@me.com
dpkg-scanpackages --multiversion . > Packages
gzip -k -f Packages
apt-ftparchive release . > Release
gpg --default-key "${EMAIL}" -abs -o - Release > Release.gpg
gpg --default-key "${EMAIL}" --clearsign -o - Release > InRelease
```

## Licensing

Please review the license policy in the linked repository for each package

## Acknowledgements

Based on the [tutorial](https://assafmo.github.io/2019/05/02/ppa-repo-hosted-on-github.html) by Assaf Morami

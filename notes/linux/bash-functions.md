Bash Functions
==============

```bash

## Alias functions ##
lm() {
  find . -mmin -$1 -printf '%T+\t%s\t%p\n' 2>/dev/null | sort -r | more
}

take() {
  mkdir $1 && cd $1
}

publish() {
  git add -A &&
  git commit -m "$1" &&
  git push origin master
}

s() {
  eval `ssh-agent -s` &&
  ssh-add ~/.ssh/$1
}


del() {
 find . -name "*.$1" -type f -delete
}

fixit() {
 sudo mkdir /var/log/apache2/ && sudo touch /var/log/apache2/{access,error,other_vhosts_access,suexec}.log && sudo chown -R root:adm /var/log/apache2/ && sudo chmod -R 750 /var/log/apache2 && sudo mkdir /var/log/mysql && sudo chown mysql:mysql /var/log/mysql && mrestart && arestart
}

## PHP ##

run() {
 portNumber=$1
 if [ -z "$portNumber" ]; then
  portNumber=8000
 fi
 php -S localhost:$portNumber
}

phpv() {
 version=$1
 sudo update-alternatives --set php /usr/bin/php$version
}


## Git ##
gnf () {
  git checkout -b feature/"${1}"
}

gnb () {
  git checkout -b bug/"${1}"
}

deploy () {
  dt=$(date '+%d/%m/%Y %H:%M:%S');
  server=$1
  if [ -z "$server" ]; then
   server=staging
  fi
  git add -A && git commit -m "$dt" && phploy -s $server
}
```

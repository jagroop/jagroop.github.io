# Bash aliases

```bash
## NODE ##
alias y='yarn'

## PHP ##
alias c='composer'
alias cr='composer require'
alias cda='composer dump-autoload -o'

## LARAVEL ##
alias laravel='composer create-project --prefer-dist laravel/laravel'
alias a="php artisan"
alias fresh="a migrate:fresh --seed"
alias tinker="a tinker"
alias cclear='a cache:clear'
alias mc='a make:controller'
alias mm='a make:model'
alias routes='a route:list'
alias vc='a view:clear'
alias lc='truncate -s 0 storage/logs/laravel.log'
alias migrate='a migrate'
alias refresh='a migrate:refresh --seed'

## Git ##
alias push='git push -u origin master'
alias pull='git pull origin master'
alias log="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
alias gdh="git checkout --orphan latest_branch && git add -A && git commit -am "first commit" && git branch -D master && git branch -m master && git push -f origin master" #Delete Git History

## Change Dir ##
alias html='cd /var/www/html/'
alias dev='cd /var/www/html/dev/'

## Jigsaw ##
alias jigsaw='./vendor/bin/jigsaw'
alias deploy='jigsaw build production && git add build_production && git commit -m "Build for deploy" && git subtree push --prefix build_production origin master'
```

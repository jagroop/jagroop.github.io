# Bash aliases

```bash
## Editing ##
alias al="sudo subl ~/aliases/"
alias src="sudo source ~/.bashrc"

## Permissions ##
alias ax="sudo chmod a+x"
alias own="sudo chown -R jagroop"
alias ownit="own app/ && own routes/ && own resources/ && own routes/ && own database/"

## NODE ##
alias y='yarn'

## PHP ##
alias c='composer'
alias cr='composer require'
alias cda='composer dump-autoload -o'
alias pb='php bin/console'

## LARAVEL ##
alias laravel='composer create-project --prefer-dist laravel/laravel'
alias a="php artisan"
alias fresh="a migrate:fresh --seed"
alias tinker="a tinker"
alias cclear='a config:clear; a cache:clear'
alias mc='a make:controller'
alias mm='a make:model'
alias routes='a route:list'
alias vc='a view:clear'
alias lc='truncate -s 0 storage/logs/laravel.log'
alias migrate='a migrate'
alias allfresh='cclear && fresh'

## Git ##
alias gs='git status'
alias gi='git check-ignore *'
alias ga='git add -A'
alias push='git push -u origin master'
alias pull='git pull origin master'
alias log="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
alias ul="git push origin -u HEAD"
alias nah="git reset --hard; git clean -df;"
alias wip="git add . && git commit -m 'WIP'"

## Change Dir ##
alias html='cd $htmlPath'
alias dev='cd $htmlPath/dev/'
alias pro='cd $htmlPath/projects/'
alias ..='cd ..'
alias ...='cd ..; cd ..'
alias bs='pro; cd b2b-auto-parts'
alias bc='pro; cd b2b-ap-client'

## OS ##
alias rr='rm -rf'

## Services ##
alias mstatus='sudo systemctl status mysql.service'
alias mrestart='sudo systemctl restart mysql.service'
alias astatus='sudo systemctl status apache2.service'
alias arestart='sudo systemctl restart apache2.service'


## Apps ##
alias skype='sudo skypeforlinux --secondary'
```

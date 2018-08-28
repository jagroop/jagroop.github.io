Project work-flow Guidelines
============================

# Git Work-flow

- Whenever you start working on a new feature or bug. Please create a separate branch for your work don't work on dev or master branch

- New features will be namespaced under feature branch. i.e.

- Bugs resolving will be namespaced under bug namespace. i.e.

```bash

## Set these aliases in your dev machine

gnf () {
  git checkout -b feature/"${1}"
}

gnb () {
  git checkout -b bug/"${1}"
}

## How to use these aliases

gnf contact-us-page # New feature branch
gnb user-auth-error # New bug branch
```
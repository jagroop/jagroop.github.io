# Working with ssh keys in git

## How to create a ssh key

- Open Terminal

```bash
cd ~/.ssh
ssh-keygen -t rsa -C "your.email@example.com" -b 4096
```
- Enter the name of key (for e.g. ssh-test)
- Leave Passphrase blank

Check my below terminal for better understanding

```bash
root@jagroop:~/.ssh# ssh-keygen -t rsa -C "geek.jagroop@gmail.com" -b 4096
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa): ssh-test
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in ssh-test.
Your public key has been saved in ssh-test.pub.
The key fingerprint is:
SHA256:chXi/UDHYHvzASQ2tjZruka+7BQK36ZLM0BsrELAQvQ geek.jagroop@gmail.com
The key's randomart image is:
+---[RSA 4096]----+
|=o      . X++    |
|o..o   . B B..   |
|.. E=   . O o .  |
|.  +     o * o . |
|. . o . S o . .  |
| .   + =.+       |
|      *o=        |
|     . Bo.       |
|      o+=.       |
+----[SHA256]-----+
root@jagroop:~/.ssh# ll
total 16
drwxr-xr-x  2 root    root    4096 Mar 24 15:41 ./
drwxr-xr-x 25 jagroop jagroop 4096 Mar 24 14:39 ../
-rw-------  1 root    root    3247 Mar 24 15:41 ssh-test
-rw-r--r--  1 root    root     748 Mar 24 15:41 ssh-test.pub
```
- Copy you public key content ```ssh-test.pub```

- Goto ```https://github.com/settings/keys```
- Click on **SSH keys and GPG Keys**
- Click on **New SSH Key Button**

- Enter title name and paste paste copied key and click **Add SSH Key** Button.

- And we are done with adding ssh key !

## How to use SSH key to access the repositories.

- Add your private ssh key to you ssh-agent

```bash
ssh-add ~/.ssh/ssh-test
```

And you are all done !!

## Problems Troubleshooting.

If you are facing problem with adding private ssh-key to your OpenSSH client or __git__ asking you to enter password while __pushing__ or __pulling__ the code.

Try restarting you **OpenSSH client** and try adding ssh key again after that.

```bash
eval $(ssh-agent -s)
ssh-add ~/.ssh/ssh-test
```

## Retain settings

To retain these settings you'll need to save them to a configuration file. For OpenSSH clients this is configured in the ~/.ssh/config file for some operating systems. Below is an example host configuration using their own SSH key:

```bash
# Github.com server
Host github.com
RSAAuthentication yes
IdentityFile ~/.ssh/ssh-test
```

Easy Way :

Permanently Add SSH key ssh-add

Open ```.bashrc``` file

```bash
nano ~/.bashrc
```

Add this command at the very end of ```.bashrc``` file

```bash
ssh-add ~/.ssh/ssh-test > /dev/null 2>&1
```
The last part of the command is to route the output of the command to dev null so I don’t see it when I open up terminal.

```bash
> /dev/null 2>&1
```

Thanks !!

# tf-sample-ruby
RubyをインストールするためのPlaybook

# tasks
- update yum packages
- set lang ja_JP.UTF-8
- installed git
- deployed .bash_profile flagment .bash.d
- made dir .bash.d
- installed rbenv
- registered rbenv path
- installed ruby-build


# Requirement
ansible

# Installation
## ec2 ansible install
```
$ sudo amazon-linux-extras install ansible2 -y
$ ansible --version
$ sudo yum install git -y
```

## deploy secret key
From local pc
```
$ scp -i <secretkey> <secretkey> ec2-user@<IP ADDRESS>:~/.ssh
```

## git clone

```zsh
$ git clone https://github.com/hito-kotaro/an-sample-http.git
$ cd an-sample-http
```

## edit hosts
```
$ vim hosts
```

### hosts sample
```
[server]
<YOUR SERVER IP ADDRESSS>

[server:vars]
ansible_ssh_port=22
ansible_ssh_user=ec2-user
ansible_ssh_private_key_file=<YOUR SECRET KEY>
__working_user=ec2-user

```

## execute commands

### syntax check

```
$ ansible-playbook site.yml --syntax-check
```

### execute playbook
```
$ ansible-playbook -i hosts site.yml
```

## ruby install 

```
$ rbenv install <VERSION>
$ rbenv global <VERSION>
```
# Control node configuration

My control node is a standard Arch linux installation. 
Aside from other

## Ansible basic requirement

Python with pip

```
$ pacman -Syu python python-pip
```
 
## Ansible and paramiko

paramiko seems to be a standard requirement for many modules and plugin

``` 
$ pip install ansible 
$ pip install paramiko 
```

## Virtual machines capabilities 

Allow Arch machine to run virtual machines via VirtualBox and Vagrant as provisioning tool.

```
$ pacman -S vagrant virtualbox virtualbox-host-modules-arch
```


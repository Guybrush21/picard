# Control node configuration

My control node is a standard Arch linux installation.
Aside from other

## Ansible basic requirement

Python with pip

```
$ pacman -Syu python python-pip
```

## Ansible and paramiko

paramiko seems to be a standard requirement for many modules and plugin.
jmespath is required by the [docker-swarm role](https://galaxy.ansible.com/atosatto/docker-swarm).

```
$ pip install ansible
$ pip install paramiko
$ pip install jmespath
```

## Ansible galaxy

Before running ansible we need to install
the roles dependencies from ansible galaxy

```
$ ansible-galaxy install -r requirements.yml
```

## Virtual machines capabilities

Allow Arch machine to run virtual machines via VirtualBox and Vagrant as provisioning tool.

```
$ pacman -S vagrant virtualbox virtualbox-host-modules-arch
```

## Linting and CI

There is a Travis CI which test linting rules defined in yamlint.
To automaticlly fix those you can use [yamlfixer](https://github.com/opt-nc/yamlfixer).

```
$ pip install yamllint yamlfixer-opt-nc
```

and then

```
$ yamlfixer -c .yamlint -r -1 .
```

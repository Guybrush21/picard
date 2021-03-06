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
pip install ansible
pip install paramiko
pip install jmespath
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

### Vagrant setup

As per [this useful link](https://max.engineer/six-ansible-practices#separate-your-setup-and-deploy-playbooks) we need to apply two step on our machine.

This is the first Vagrant plugin needed

```
vagrant plugin install vagrant-hostsupdater
```

Then we want our `~/.ssh/config` to look like this:

```
# For vagrant virtual machines
Host 192.168.56.* *.uss
  StrictHostKeyChecking no
  UserKnownHostsFile=/dev/null
  User vagrant
  LogLevel ERROR
```

## Linting and CI

There is a Travis CI which test linting rules defined in yamlint.
To automatically fix those you can use [yamlfixer](https://github.com/opt-nc/yamlfixer).

```
$ pip install yamllint yamlfixer-opt-nc
```

and then

```
$ yamlfixer -c .yamllint -r -1 .
```

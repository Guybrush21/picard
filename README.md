# picard

Ansible playbook for playtesting.

## Status

[![Build Status](https://app.travis-ci.com/Guybrush21/picard.svg?branch=main)](https://app.travis-ci.com/Guybrush21/picard)

## Get started

You need a valid control node capable of running Ansible and Vagrant. Check [control node prerequisites](./docs/CONTROL-NODE-PREREQUISITES.md)

Everything should be provisioned with a simple:

```
export VAGRANT_EXPERIMENTAL="disks"
vagrant up
```

VAGRANT_EXPERIMENTAL is needed to create a bigger inital disk (80GB instead of 40GB) to complete ex. 2.

For subsequent playbook edits use ansible directly with the inventory parameter.

```
ansible-playbook playbook.yml -i host.ini
```

## Ansible exercise

Using an **ansible playbook**:

1. [x] Provisioning of two CentOS VM, cloud or locally.
2. [x] Setting VM: Ensure partition used by Docker is at least 40GB.
3. [x] Install Docker on the VMs
4. Setting up Docker:
   1. [ ] Securely expose Docker Daemon REST API
   2. [x] Ensure Docker Daemon is configured as a service that starts on boot.
5. [x] Configure a Docker Swarm on the two VMs, securely accessible. Ensure you can deploy services on the swarm.
6. [ ] _Optionally:_ Test one of the task above using Molecule.

Describe each activity with appropriate Ansible roles and related tasks. The reuse of Ansible roles and playbooks made available in the open-source community is highly recommended (some of which are already linked in the text as an example and below for useful references). In case of code reuse it is important to motivate the role selection criteria, to know its features and contents, and to be able to describe any customizations carried out for the purpose of carrying out the above activities.

Code Versioning:

1. [x] Versioning the code on a public repository on Github.com, so that there is a clear description of the work done in the history of the repository;

Continuous Integration:

1. [x] Configure a Continuous Integration pipeline on a tool of your choice (tip: Travis, for simple integration with GitHub, Ansible Docker)
2. Pipeline should:
   1. [x] Linting the code and failing in case of errors, which must be suitably corrected.
   2. [ ] _Optionally:_ Execute the test carried out in point 6 automatically at each code push on the repository

References:

- Ansible User Guide: https://docs.ansible.com/ansible/latest/user_guide/index.html
- Ansible Galaxy: https://galaxy.ansible.com/
- Best Practices: http://hakunin.com/six-ansible-practices
- Testing Ansible provisioning locally: https://www.hamvocke.com/blog/local-ansible-testing/
- Testing Ansible roles and playbooks: https://www.digitalocean.com/community/tutorials/how-to-implement-continuous-testing-of-ansible-roles-using-molecule-and-travis-ci-on-ubuntu-18-04
- Version pinning: [as general rule](https://medium.com/the-guild/how-should-you-pin-your-npm-dependencies-and-why-2b8d545c7312), and [Docker specific](https://www.tjohearn.com/2018/03/01/the-case-for-pinning-versions-of-docker-dependencies/)
- Playbook nice example from HPE: https://github.com/HewlettPackard/Docker-SimpliVity

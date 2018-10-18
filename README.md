# Ansible : Playbook SSH

The aim of this project is to easily manage users, groups, SSH and shell prompt on Vagrant instances.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to run this Ansible playbook :

*   [Vagrant](https://www.vagrantup.com/docs/installation/) must be installed on your computer
*   Update the Vagrant file based on your computer (CPU, memory), if needed
*   You must have download the ubuntu Xenial64 vagrant box :

```bash
$ vagrant box add https://app.vagrantup.com/ubuntu/boxes/xenial64
```
*   sYou should configure the role with your SSH keys to be able to connect on each instances

### Usage

A good point with Vagrant is that you can create, update and destroy all architecture easily with some commands.

Be aware that you need to be in the Vagrant directory to be able to run the commands.

#### Build Environment

Vagrant needs to init the project to run and build it :

```bash
$ vagrant up
```

After build, you can check which virtual machine Vagrant has created :

```bash
$ vagrant status
```

If all run like it is expected, you should see something like this :

```bash
$ vagrant status

Current machine states:

ssh01.prd                   running (virtualbox)
ssh01.stg                   running (virtualbox)
ssh01.dev                   running (virtualbox)
```

#### Deployment

To deploy this role, you just have to run the Ansible playbook ssh.yml with this command :

```bash
$ ansible-playbook ssh.yml
```

If everything run as expected, you should access any Vagrant instances and see two users : foo and bar

Connect on each user to see the specific prompt and SSH keys associated.

#### Destroy

To destroy the Vagrant resources created, just run this command :

```bash
$ vagrant destroy
```

## Author

Member of Wikitops : https://www.wikitops.io/

## Licence

This project is licensed under MIT license. For the full text of the license, see the LICENSE file.

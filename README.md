# usershub-ansible

A simple [ansible](http://docs.ansible.com) playbook to deploy a standealone [Usershub](https://github.com/PnX-SI/UsersHub) web app.

This will deploy a working Usershub web app from the **master** branch.

This will follow the main [usershub documentation](https://usershub.readthedocs.io/fr/latest/).

## Prerequisite

* Debian Bullseye (11.x) VM
* GitHub account to get usershub sources
* Ansible
* SSH VM access (mandatory to execute Ansible) with root user

## Setup

* Clone source

```
git clone https://github.com/jdev-org/usershub-ansible.git
```

* Setup variables for your own instance in ```playbooks/main.yml``` **vars** section

* Open `ansible/hosts` file

* Replace `IP_OF_YOUR_MACHINE` by the IP of a host where you have `ssh-with-passphrase` root access (ideally, an lxc container, a vm, or whatever suits you) to get something like :

    `mygeorchestra ansible_ssh_host=192.xxx.xx.x`

* Replace `USER_OF_YOUR_MACHINE` by the user sudo (Ansible will execute playbook with this user)

* Replace `USER_PASSWORD` by the sudo user password

... and run command :

```
ansible-playbook playbooks/main.yml
```
👉 If you don't run the playbook with a remote access (ssh) you maybe need to replace the ansible/hosts file content by :

```
myusershub ansible_ssh_host=192.168.1.158
```

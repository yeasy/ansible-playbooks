# ansible-playbooks
Some useful playbooks for ansible.

## Usage

### Define the host

Hosts can be defined inside `/etc/ansible/hosts`, e.g.,
```sh
[local]
localhost
```

Otherwise, you can use the `-i hosts` option to take the local `hosts` file.

### Apply role
Run ansible-playbook with given yaml file name, by default, will apply the
stack on all host.

e.g.,

```sh
$ ansible-playbook web-server.yml
```

```sh
$ ansible-playbook site.yml --limit webserver
```

This will apply the role in yml file to all hosts. `site.yml` will apply the
whole stack.

If you wanna run at localhost without ssh, then just add `-c local`, e.g.,
```sh
$ ansible-playbook -c local  common.yml
```

You can also modify the playbook to change the default role.

For instance.
```sh
- hosts: servers
  roles:
     - { role: web-server }
```

## common
Some common tasks like
* Update system cache
* Install/Config ntp
* Install tmux.

## docker
Install docker to the system.

## web-server
Will apply on the `webserver` type host.

* make sure Nginx is installed
* make sure Nginx is running


## Acknowledgement
The project is highly inspired by the [ansible-examples](https://github.com/ansible/ansible-examples).

# ansible-playbooks
Some useful playbooks for ansible.

## Usage
Run ansible-playbook with given yaml file name.

e.g.,

```sh
$ ansible-playbook site.yml --limit webserver
```

```sh
$ ansible--playbook web-server.yml
```

You can also create your own playbook using the role.

For instance.
```sh
- hosts: servers
  roles:
     - { role: web-server }
```

## common
Some common tasks like update system packages.

## docker
Install docker to the system.

## web-server
Will apply on the `webserver` type host.

* make sure nginx is installed
* make sure nginx is running

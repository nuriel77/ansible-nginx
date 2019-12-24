Role Name
=========

Ansible NGINX Role

Requirements
------------

This role is used by Ansible playbooks such as [IRI-Playbook](https://github.com/nuriel77/iri-playbook), [GoShimmer-Playbook](https://github.com/nuriel77/goshimmer-playb
ook) and [Hornet-Playbook](https://github.com/nuriel77/hornet-playbook).

It installs HAProxy in Docker and provides a configuration specific for an IOTA node (IRI or Hornet).

Role Variables
--------------

`nginx_vhost_files`: a list of maps with "src" and "dest" files (or jinja2 templates) to configure nginx with. `dest` is optional. If not supplied, will default to basename of the source file (will truncate `.j2` if template).

Example:
```yaml
nginx_vhost_files:
  - src: 'templates/example.com.j2
    dest: 'example.com.conf'
  - src: 'templates/testing.io.j2'
  - src: 'files/static.ssl.conf'
    dest: 'ssl.conf'
```

The rest of the variables can be found in [defaults](defaults/)

Dependencies
------------

[Ansible-Docker](https://github.com/nuriel77/ansible-docker)

Specific files, e.g. shared-files from [Hornet-Playbook](https://github.com/nuriel77/hornet-playbook/tree/master/roles/shared-files)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-nginx, x: 42 }

License
-------

MIT

Author Information
------------------

[Nuriel Shem-Tov](https://github.com/nuriel77)

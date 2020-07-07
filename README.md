packages
========

Install software from the repositories through the distribution's package manager

Requirements
------------

When installing packages for users on Red Hat or CentOS from the Software Collections (SCL), make sure there is a shell file in `files/etc/profile.d/` that properly enables the package by setting the user's path and such. See the `scl-enable-rh-git218.sh` file as an example.

Role Variables
--------------

```yaml
additional_packages:          # a list of packages to install
additional_packages_scl:      # a list of packages to install from the Software Collections repository
```

When using a file repository on a Red Hat Satellite server, the client needs a certificate to download packages from it
```yaml
satellite_client_cert:        # location of the Satellite client certificate on the client
local_satellite_client_cert:  # location of the Satellite client certificate on the Ansible server
```

Dependencies
------------

None

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - { role: packages, additional_packages: vim }
```

License
-------

BSD

Author Information
------------------

Ruud Bleeker <rbleeker@gmail.com>

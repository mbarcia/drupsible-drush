# drupsible-drush
Drupsible role for managing Drush

Requirements
------------

Requires composer to be available as a system-wide command.
Needs escalation (become: yes)

This role can be used indepedently and does NOT require Drupsible to run.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows

    # Drush minimum version
    drush_min_version: "8.1.0"

    # Contributed modules destination
    drush_contrib_modules_destination: 'sites/all/modules'

Example Playbook
----------------

```
- role: drupsible.composer
  composer_installer_url: "https://getcomposer.org/installer"
  composer_installer_checksum_enabled: no
  become: yes
  tags: [ 'role::composer' ]
- role: drupsible.drush
  become: yes
  tags: [ 'role::drush' ]
```

License
-------

GNU General Public License v3

Author Information
------------------

Mariano Barcia - [https://github.com/mbarcia](https://github.com/mbarcia)

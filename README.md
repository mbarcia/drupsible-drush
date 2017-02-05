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

    # Drupal major version (currently, 7 or 8)
	drush_drupal_version: '8'
	
    # Drush minimum version
    drush_min_version: "8.1.9"

    # Contributed modules destination
    drush_contrib_modules_destination: 'modules' if drush_drupal_version == '8'
    drush_contrib_modules_destination: 'sites/all/modules' if drush_drupal_version == '7'

    # Your application user
	drush_app_user: 'myapp'

    # Your application user group
	drush_app_group: 'www-data'

    # Your application user home dir
	drush_app_user_home: '/home/myapp' if drush_app_user != root
	drush_app_user_home: '/root' if drush_app_user == root


Example Playbook
----------------

```
- role: drupsible.composer
  composer_installer_url: "https://getcomposer.org/installer"
  composer_installer_checksum_enabled: no
  become: yes
  tags: [ 'role::composer' ]
- role: drupsible.drush
  drush_app_user: 'myapp'
  become: yes
  tags: [ 'role::drush' ]
```

License
-------

GNU General Public License v3

Author Information
------------------

Mariano Barcia - [https://github.com/mbarcia](https://github.com/mbarcia)

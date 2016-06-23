# Ansible Role: Chrony

[![Build Status](https://travis-ci.org/devops/ansible-role-chrony.svg?branch=master)](https://travis-ci.org/devops/ansible-role-chrony)

Installs and configures chrony.

## Requirements

None.

## Role Variables

### `defaults/main.yml`

* `chrony_packages:`
    ```
      - chrony
    ```

* `chrony_config_server:`
    ```
      - ntp.api.bz
    ```

* `chrony_config_allow: []`

* `chrony_config_logdir: '/var/log/chrony'`

### `vars/RedHat.yml`

* `chrony_service_name: chronyd`
* `chrony_config_location: /etc/chrony.conf`

## Dependencies

None.

## Example Playbook

1) Install chrony and use the default settings.

	- hosts: all
	  roles:
	    - ansible-role-chrony

2) Install chrony and use custom servers.

	- hosts: all
	  roles:
	    - role: ansible-role-chrony
          chrony_config_server:
            - ntp.pi.bz
          chrony_config_allow:
            - 192.168.1/24

## License

MIT / BSD

## Author Information

z.

# Ansible Role: XNAT 1.7.4

An Ansible Role that installs XNAT 1.7.4 on RedHat/CentOS (and Debian/Ubuntu in the future) Linux servers.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    xnat_version: 1.7.4.1

Xnat version to be installed.

    pipeline_version: 1.7.4

Xnat pipe line engine version to be installed.

    xnat_data_dir: /data/xnat
    xnat_home: "{{ xnat_data_dir }}/home"
    xnat_home_subdirs:
      - config
      - logs
      - plugins
      - work
    xnat_data_subdirs:
      - archive
      - build
      - cache
      - ftp
      - pipeline
      - prearchive

A bunch of directories will be created for xnat.

    xnat_user: xnat
    xnat_group: xnat

Xnat user and group to be created at OS level.

    xnat_db_user: "{{ xnat_user }}"
    xnat_db_name: "{{ xnat_user }}_db"
    #xnat_db_password: should be stored in vault.

Xnat database user, db and password to be created in PosgreSQL DB.

    xnat_db_server: "{{ ansible_hostname }}"

Database server hostname or IP. By default, it's on same server with xnat.

    admin_email: 'xnat@xnat.org'

Xnat admin user's email address, which is used in pipeline engine tasks.   

    use_proxy: False
    proxy_addr: ''
    proxy_port: ''
    proxy_opts: ''

A bunch of proxy related variables.

## Dependencies

  - java ( version 1.7 ).
  - tomcat ( version 7 ).
  - PosgreSQL ( version 9.x )

## Example Playbook

    test.yml

## License

MIT / BSD

## Author Information

This role was created in 2017 by Wally Chu @ Macquarie University

[![build-test](https://github.com/darkwizard242/ansible-role-awsvault/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-awsvault/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-awsvault/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-awsvault/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/47488?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/47488?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/47488?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-awsvault&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-awsvault) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-awsvault&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-awsvault) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-awsvault&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-awsvault) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-awsvault&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-awsvault) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-awsvault?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-awsvault?color=orange&style=flat-square)

# Ansible Role: aws-vault

Role to install (_by default_) [aws-vault](https://github.com/99designs/aws-vault) on **Debian/Ubuntu** and **EL** systems.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
awsvault_app: aws-vault
awsvault_version: 6.6.1
awsvault_os: linux
awsvault_arch: amd64
awsvault_dl_url: https://github.com/99designs/{{ awsvault_app }}/releases/download/v{{ awsvault_version }}/{{ awsvault_app }}-{{ awsvault_arch }}-{{ awsvault_arch }}
awsvault_bin_path: /usr/local/bin
awsvault_file_owner: root
awsvault_file_group: root
awsvault_file_mode: '0755'
```

### Variables table:

Variable            | Description
------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------
awsvault_app        | Defines the app to install i.e. **aws-vault**
awsvault_version    | Defined to dynamically fetch the desired version to install. Defaults to: **6.6.1**
awsvault_os         | Defines os type. Used for obtaining the correct type of binaries based on OS type. Defaults to: **linux**
awsvault_arch       | Defines os architecture. Used to set the correct type of binaries based on OS System Architecture. Defaults to: **amd64**
awsvault_dl_url     | Defines URL to download the aws-vault binary from.
awsvault_bin_path   | Defined to dynamically set the appropriate path to store awsvault binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
awsvault_file_owner | Owner for the binary file of aws-vault.
awsvault_file_group | Group for the binary file of aws-vault.
awsvault_file_mode  | Mode for the binary file of aws-vault.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **awsvault**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.awsvault
```

For customizing behavior of role (i.e. specifying the desired **awsvault** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.awsvault
  vars:
    awsvault_version: 5.4.0
```

For customizing behavior of role (i.e. placing binary of **awsvault** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.awsvault
  vars:
    awsvault_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-awsvault/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.linkedin.com/in/ali-muhammad-759791130/).

# Ansible Hoodie

```
.d$b.  .d$b.  .d$$$$$$b.    .d$$$$$$b.  .d$$$$$$b.  .d$b..d$$$$$$$$b.
$$$$$..$$$$$.$$$$$$$$$$$b .$$$$$$$$$$$b $$$$$$$$$$b $$$$$$$$$$$$$$$P'
$$$$$$$$$$$$d$$$$$$$$$$$$bd$$$$$$$$$$$$b$$$$$$$$$$$b$$$$$$$$$$$$$$$b.
$$$$$$$$$$$$Q$$$$$$$$$$$$PQ$$$$$$$$$$$$P$$$$$$$$$$$P$$$$$$$$$$$$$$$P'
$$$$$´`$$$$$'$$$$$$$$$$$$''$$$$$$$$$$$$'$$$$$$$$$$P $$$$$$$$$$$$$$$b.
'Q$P'  'Q$P'  'Q$$$$$$P'    'Q$$$$$$P'  'Q$$$$$$$P  'Q$P''Q$$$$$$$$P'
```

This is an [Ansible](http://www.ansible.com/) role for
[Hoodie](http://hood.ie/), the wonderful offline-first web application
development environment.

**IN PROGRESS** This role is based on the
[Hoodie Deployment Guide](https://github.com/hoodiehq/my-first-hoodie/blob/master/deployment.md)
and still requires some work around support for HTTPS and more.

## Requirements

This Hoodie role requires a Debian based Linux host and has been tested to
function on Ubuntu with the following specific software versions:

* Ansible: 1.7.2
* Hoodie: 0.6.3
* Node.js: 0.10.33
* Debian: 7.7

## Role Variables

All variables are specified in `defaults/main.yml` and `vars/main.yml`.

### Defaults

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| hoodie_node_version | 0.10.33 | Preferred Node.js version |

The following OS dependency packages are defined in `hoodie_os_packages` and
installed by default:

* curl
* git
* couchdb
* monit
* nginx

### Variables

| Name            | Default Value | Description                        |
| --------------  | ------------- | -----------------------------------|
| hoodie_admin    | hoodie        | Hoodie user account; for Vagrants, this should be 'vagrant'.
| hoodie_app_name | None          |Name of the Hoodie app
| hoodie_app_domain | None       | Fully Qualified Domain Name (FQDN) of the Hoodie app
| hoodie_soft_nofile | 768 | Soft open files limit for the hoodie user
| hoodie_hard_nofile | 1024 | Hard open files limit for the hoodie user
| hoodie_node_packages | List | Node.js dependencies
| hoodie_os_packages | List | OS dependencies

## Configuration

At a minimum, modify the variables defined in the following files as
necessary:

* `defaults/main.yml`
* `vars/main.yml`

Copy `hosts.example` to `hosts` and edit it to update the values for your
Hoodie host. Be sure to change the following values:

* `0.0.0.0`
* `hoodie`
* `~/.ssh/hoodie_id`

## Example Playbook

After configuration a basic Hoodie installation and activation is possible
using the included `site.yml` playbook:

```
ansible-playbook -i hosts site.yml
```

## Dependencies

None

## License

Apache 2

## Author Information

[Brian Shumate](http://brianshumate.com)

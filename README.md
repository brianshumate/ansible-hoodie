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

This role is based on the
[Hoodie Deployment Guide](https://github.com/hoodiehq/my-first-hoodie/blob/master/deployment.md).

## Requirements

This Hoodie role requires a Debian based Linux host and has been tested to
function on Ubuntu with the following specific software versions:

* Ansible: 1.7.2
* Hoodie: 0.6.3
* Node.js: 0.10.33
* Ubuntu: 14.04

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
| hoodie_app_name | myhoodie | Name of the Hoodie app
| hoodie_app_domain | example.com | Fully Qualified Domain Name of the Hoodie app
| hoodie_soft_nofile | 768 | Soft open files limit for the hoodie user
| hoodie_hard_nofile | 1024 | Hard open files limit for the hoodie user
| hoodie_node_packages | List | Node.js dependencies
| hoodie_os_packages | List | OS dependencies

## Configuration

Modify the variables defined in the following files as necessary:

* `defaults/main.yml`
* `vars/main.yml`

At a minimum, you should change the value of the following variables:

* hoodie_app_name
* hoodie_app_domain
* hoodie_couchdb_admin_passwd

Copy the `examples/hosts.example` inventory to `hosts` and edit it to update
the values for your Hoodie host. Be sure to change the following values:

* `0.0.0.0`
* `hoodie`
* `~/.ssh/hoodie_id`

You'll then need to provide an SSL chained certificate and corresponding
private key, by copying them into this role's `files` directory; the filename
for the source certificate and key should be in the format of the following
examples:

* `_myhoodie.example.com.chained.crt`
* `_myhoodie.example.com.key`

Replace *myhoodie.example.com* in the above examples with the actual
fully qualified domain name of your hoodie application in your filenames.

Note that the underscore (_) preceding the filenames is required.

## Example Playbook

After configuration, a basic Hoodie installation and activation is possible
using the included `site.yml` playbook:

```
ansible-playbook -i hosts site.yml
```

### Getting Started

After the successful execution of this role, your Hoodie application will be
ready to run.

You can log into your Hoodie host, and use the following commands to bootstrap
and run your Hoodie application:

```
sudo su - hoodie
./bin/hoodie-bootstrap.sh
```

You should now be able to access your application at the FQDN you specified in
the `hoodie_app_domain` variable, e.g.:

```
https://www.example.com/
```

**NOTE**: Given that the automatic starting of your example Hoodie app is
for testing only, please examine the `hoodie-daemon.sh` script in the `bin`
directory under hoodie user's home directory for an alternative means of
executing a Hoodie instance in production.

## Dependencies

None

## License

Apache 2

## Author Information

[Brian Shumate](https://github.com/brianshumate)

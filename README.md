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

## Requirements

This Hoodie role requires a Debian based Linux host and has been tested to
function on Ubuntu with the following specific software versions:

* Ansible: 1.7.2
* VirtualBox: 4.3.16
* Vagrant: 1.6.5
* Hoodie: 0.6.3
* Node.js: 0.10.33
* Debian: 7.7

## Role Variables

All variables are specified in `defaults/main.yml` and `vars/main.yml`.

### Defaults

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| hoodie_admin    | vagrant       | OS username of Hoodie owner/admin |
| hoodie_dir      | `/home/<hoodie_admin>/hoodie` | The Hoodie base directory |
| hoodie_os_packages   | List | List of OS dependency packages to install |
| hoodie_node_version | 0.10.25 | Preferred Node.js version |
| hoodie_node_packages | List | List of Node.js dependency packages to install |
| hoodie_nvm_dir  | /home/{{ hoodie_admin }}/nvm | Directory for Node Version Manager (nvm) installation |
| hoodie_node_dir | {{ hoodie_nvm_dir }}/v{{ hoodie_node_version }}/bin | Directory for Node.js installation
| hoodie_src_dir | /home/{{ hoodie_admin }}/src/hoodie | Directory for Hoodie source code

The following OS dependency packages are defined in `hoodie_os_packages` and
installed by default:

* build-essential
* curl
* git
* couchdb
* nginx


### Variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|

## Configuration

At a minimum, modify the variables defined in the following files as
necessary:

* `defaults/main.yml`
* `vars/main.yml`

Then, copy `templates/hoodie.env.j2` to `templates/_hoodie.env.j2` and update
as necessary with the particular environment variables you need for your
Hoodie instance.

Copy `hosts.example` to `hosts` and edit it to update the values for your
Hoodie host. Be sure to change the following values:

* `0.0.0.0`
* `ubuntu`
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

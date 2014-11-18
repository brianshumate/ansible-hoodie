# Ansible Hoodie with Vagrant

This is a role for [Hoodie](http://hood.ie/), the wonderful offline-first
web application development environment

These instructions will help you to launch a Hoodie installation on Mac OS X
under Vagrant and VirtualBox.

## Requirements

This Hoodie role requires a Debian based Linux host and has been tested to
function on Ubuntu with the following specific software versions:

* Ansible: 1.7.2
* VirtualBox: 4.3.16
* Vagrant: 1.6.5
* Hoodie: 0.6.3
* Node.js: 0.10.33
* Debian: 7.7

## Prerequisites

Follow these directions for a Hoodie development deployment on Mac OS X
to an Ubuntu virtual machine on VirtualBox with Vagrant.

Install the following on the Mac that will be used for Hub development,
testing, or trying to take over the world:

* [VirtualBox](https://www.virtualbox.org/)
* [Vagrant](http://www.vagrantup.com/)
* [Ansible](http://www.ansibleworks.com/docs/intro_installation.html)

These tools are optional, but highly recommended:

* [Virtualenv](http://www.virtualenv.org/)
* [Virtualenv Wrapper](https://bitbucket.org/dhellmann/virtualenvwrapper/)

### Configuration

At a minimum, visit the variables defined in the following files:

* `defaults/main.yml`
* `vars/main.yml`

There is more information in the main project
[README](README.md) about these variables.

Then, copy `templates/hoodie.env.j2` to `templates/_hoodie.env.j2` and update
as necessary with the particular environment variables you need for your
Hoodie instance.

### Launch

After configuring your Hoodie instance environment variables, you should be
able to start using Hoodie in a virtualenv with commands like following:

```
mkvirtualenv ansible
pip install ansible
vagrant up
```

# Ansible Hoodie with Vagrant

This is a role for [Hoodie](http://hood.ie/), the wonderful offline-first
web application development environment

These instructions will help you to launch a Hoodie installation on Mac OS X
under Vagrant and VirtualBox.

## Requirements

This Hoodie role requires a Debian based Linux host and has been tested to
function on Ubuntu with the following specific software versions:

* Ansible: 1.9.1
* VirtualBox: 4.3.26
* Vagrant: 1.7.2
* Hoodie: 0.6.3
* Node.js: 0.12.2
* Ubuntu 14.04

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

### Launch

After configuring your Hoodie instance environment variables, you should be
able to start using Hoodie in a virtualenv with commands like following:

```
mkvirtualenv ansible
pip install ansible
vagrant up
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

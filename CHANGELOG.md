## v1.0.0

- Initial release

## v1.0.1

- Fixed broken tasks
- Refactor defaults and variables

## v1.0.2

- Task ordering update

## v1.03

- Change tasks to use sudo since hoodie user is not ssh user
- Correct permissions at end of tasks

## v1.0.4

- Actually install hoodie-cli now

## v1.0.5

- Remove extraneous Debian packages

## v1.0.6

- Remove nonsensical backports

## v1.0.7

- Task fixes

## v1.0.8

- Streamline installed OS packages
- Add log rotation configuration
- Add Monit configuration
- Add Nginx configuration
- Update Vagrantfile
- Update variables
- Update docs
- Nginx SSL task

## v1.0.9

- Update hoodie_home

## v1.0.10

- Updated Nginx configuration
- Fixed SSL bits

## v1.0.11

- Add Hoodie CouchDB settings

## v1.0.12

- Refactor variables
- Update docs

## v1.0.13

- Remove default Nginx host so that Nginx will start

## v1.0.14

- sudo Configuration

## v1.0.15

- Refactor variables
- Update documentation

## v1.1.0

- First working out of the box version
- Documentation updated

## v1.1.1

- Configure the CouchDB admin and admin password
- Install `hoodie-bootstrap.sh` to bootstrap the Hoodie application
- Install `hoodie-daemon.sh` script for running Hoodie in production
- Update documentation

## v1.1.2

- Fix tasks

## v1.1.3

- Meta update

## v1.1.4

- Update supported versions
- Update vagrant_hosts inventory for new private key location
- More aggressive ownership/permissions updates after certain tasks
- Update documentation

## v1.1.5

- Rename some tasks
- Conditionally use the store and account tutorial bootstrap script
- Update documentation

## v1.1.6

- Correct tutorial handling
- Update bootstrap scripts
- Update Vagrantfile
- Update documentation

## v1.1.7

- Update documentation

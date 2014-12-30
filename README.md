## Vagrant Nodejs Dev Box
Vagrant dev box with chef solo provisioning
* Ubuntu Server 14.04
* Nodejs
* MongoDB
* ElasticSearch

## Installation
* Install [VirtualBox - 4.3.18](http://download.virtualbox.org/virtualbox/4.3.18/VirtualBox-4.3.18-96516-OSX.dmg "VirtualBox Downloads Page").
* Install [Vagrant - 1.6.5](https://dl.bintray.com/mitchellh/vagrant/vagrant_1.6.5.dmg "Vagrant Downloads Page").

Run:

```bash
$ vagrant plugin install vagrant-omnibus
$ vagrant plugin install vagrant-librarian-chef
$ vagrant up
```
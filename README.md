simple-magento-vagrant
======================

A VERY simple Magento environment provisioner for [Vagrant](http://www.vagrantup.com/).

![Magento & Vagrant](https://cookieflow.files.wordpress.com/2013/07/magento_vagrant.jpg?w=525&h=225)

* Creates a running Magento development environment with a few simple commands.
* Runs on Ubuntu (Precise 12.04 64 Bit) \w PHP 5.3, MySQL 5.5, Apache 2.2
* Uses [Magento CE 1.9.0.1](http://www.magentocommerce.com/download) or [provide your own](#provide-your-own-magento)
* Automatically runs Magento's installer and creates CMS admin account.
* Automatically runs [n98-magerun](https://github.com/netz98/n98-magerun) installer. 
* Perfect for rapid development or extension testing with an unopionionated, bare-bones and easily tweaked configuration.
* Goes from naught-to-Magento in a couple of minutes.

## Getting Started

**Prerequisites**

* Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* Install [Vagrant](http://www.vagrantup.com/)
* Clone or [download](https://github.com/r-baker/simple-magento-vagrant/archive/master.zip) this repository to the root of your project directory `git clone https://github.com/r-baker/simple-magento-vagrant.git`
* In your project directory, run `vagrant up`

The first time you run this, Vagrant will download the bare Ubuntu box image. This can take a little while as the image is a few-hundred Mb. This is only performed once.

Vagrant will configure the base system before downloading Magento and running the installer.

## Usage

* In your browser, head to `127.0.0.1:8080`
* Magento CMS is accessed at `127.0.0.1:8080/admin`
* User: `admin` Password: `password123123`
* Access the virtual machine directly using `vagrant ssh`
* When you're done `vagrant halt`

### Provide Your Own Magento

If you put a file in the vagrant shared directory named 'magento.tar', the provisioner will use it instead of downloading Magento CE 1.9.0.1. For example, if you have an Enterprise Edition or other Magento you want to use, drop it in the directory before building and symlink it to magento.tar.

[Full Vagrant command documentation](http://docs.vagrantup.com/v2/cli/index.html)

## Todo
* Expose MySQL port for access using Workbench or your preferred MySQL admin tool.
* Install Modman.
* Optionally install sample store inventory

**Why no Puppet/Chef?**
Admittedly, Puppet and Chef are excellent solutions for predictable and documented system configurations. The emphasis for this provisioner is on unopinionated simplicity. There are some excellent Puppet / Chef Magento configurations on Github with far more bells and whistles.

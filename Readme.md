CloudStack-Template
===================

## Ansible Playbook for creating CloudStack templates

These plays have been tested and work against:
* Red Hat Enterprise Linux (and derivatives [Scientific/Centos/Oracle])
  * 5
  * 6
* Debian Linux
  * 6
  * 7
* Ubuntu Linux
  * 10.04 LTS
  * 12.04 LTS
  * 14.04 LTS

To execute the Playbook, you need to have Ansible installed on the local workstation. Instructions for installing Ansible are available [here](http://docs.ansible.com/intro_installation.html).

Once Ansible is installed, you will need to modify the hosts file to reflect the IP addresses, passwords, and possibly SSH ports needed to connect to the instance and perform the configuration.

The Playbook is executed by having this directory as your current working directory and executing: ansible-playbook -i ./hosts ./Template.yml

### What this Playbook provides

This playbook:
* installs a suite of standard packages across all distributions, including curl, wget, lynx, screen, and tmux.
* sets up new init scripts (which work under init and upstart. systemd support is coming soon.) for SSH keys, passwords, and user data execution.
* sets up a new Firstboot script to set up networking, hostsfile, and set the hostname according to DHCP
* cleans out old log files
* cleans out old ssh host keys
* sets a MOTD splash

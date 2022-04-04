Ansible Role: Splunk Universal Forwarder Agent
=========

Ansible role to install Splunk Universal Forwarder Agent on Linux Servers.

Requirements
------------

The role does not require anything to run on RHEL and its derivatives.

Role Variables
--------------

Available variables are listed below, along with default values (see ```defaults/main.yml```):

``` yaml
software_url: "http://www.example.org"
package_name: "splunkforwarder_8.2.1_x86_64.rpm"
```

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_name``` **(Required)** The Installer package name.

Role variables can be stored with the ```hosts.yaml``` file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

``` yaml
    - hosts: servers
      roles:
         - role: mikepruett3.splunk
```

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3/ansible-role-splunk)

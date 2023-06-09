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
proxy: False
proxy_host: "myproxyserver.example.com:3128"
proxy_protocol: "http"

software_url: "http://www.example.org"
package_name: "splunkforwarder_8.2.1_x86_64.rpm"
package_version: "8.2.1"

heavy_forwarder: "forwarder.example.org:8089"

splunk_account: "myuser"
splunk_group: "myuser"
splunk_password: "mypass"
splunk_service: "SplunkForwarder.service"
```

```proxy``` **(Required)** Controls if the client install will be used with a HTTP/HTTPS Proxy Server. This should be either **True** or **False** (Default is **False**).

```proxy_host, proxy_protocol``` **(Optional)** Settings only required when ```proxy``` is set to **True**.

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_name``` **(Required)** The Installer package name.

```package_version``` **(Required)** The version of the Installer package. Used in determination if Upgrading existing install.

```heavy_forwarder``` **(Required)** The Hostname & Port for the specific Heavy Forwarder to communicate with.


```splunk_account, splunk_group``` **(Required)** User & Group names to be used/created for the client to run as. (Default is **splunk** for both)

```splunk_password``` **(Required)** Credentials to be used for the client to run as.

```splunk_service``` **(Required)** The name of the systemd service for the client. (Default is **SplunkForwarder.service**)

Role variables can be stored with the ```hosts.yaml``` file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

``` yaml
    - hosts: servers
      roles:
         - role: ansible-role-splunk
```

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3/ansible-role-splunk)

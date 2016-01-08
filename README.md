Ansible-Role-SABnzbd
=======
This role deploys [SABnzbd](http://sabnzbd.org), an open source binary newsreader.

Requirements
------------
This role has been written to be used with [Ubuntu](http://www.ubuntu.com), I will be adding more OS support in later releases

Role Variables
--------------
All variables have sensible defaults, which can be found in `defaults/main.yml`.
The current version includes the following variables:

| Name               | Default Value | Description                  |
|--------------------|---------------|------------------------------|
| sabnzbd_user_name  | sabnzbd | username to run the SABnzbd service |
| sabnzbd_group_name | sabnzbd | groupname to run the SABnzbd service |
| sabnzbd_data_location| /var/sabnzbd | Default location where sabnzbd will store data|
| sabnzbd_ip_addr | 0.0.0.0 | IP address the SABnzbd service will listen on |
| sabnzbd_port_no | 8080 | tcp port the SABnzbd web interface will bind to |

Example Playbook
----------------
Below is a playbook example where you can override the default values:

```yaml
    - hosts: sabnzbd_servers

      vars:
        sabnzbd_user_name: username
        sabnzbd_group_name: groupname

      roles:
        - role: ansible-role-sabnzbd
```

Or, passing parameter values:

```yaml
	- hosts: sabnzbd_servers
	  roles:
	    - { role: ansible-role-sabnzdb, sabnzbd_user_name: downld, sabnzbd_group_name: downld }
```
License
-------
MIT

Author Information
------------------
Original Playbook Created by [Calum MacRae](http://cmacr.ae)
Refactored by [Kyle.Hartigan](https://github.com/setswei)

Feel free to:  
[Raise an issue](https://github.com/setswei/ansible-sabnzbd/issues)  

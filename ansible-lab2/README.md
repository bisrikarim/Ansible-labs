# Ansible Lab 2 - Ad HOC tasks and Modules

1. Use APT module to install services
2. Use service module to manage services
3. Use ansible to reboot webstack

# Install Services using APT module
### https://docs.ansible.com/ansible/latest/modules/apt_module.html

### Update repositories cache
``` shell
ansible all -i hosts --become -m apt -a "update_cache=yes"
```
### Install apache httpd  (state=present is optional)
``` shell
ansible webservers -i hosts --become -m apt -a "name=apache2 state=present"
```
### Install mysql (state=present is optional)
``` shell
ansible database -i hosts --become -m apt -a "name=mysql-server state=present"
```

# Restart Services using Service module
### https://docs.ansible.com/ansible/latest/modules/service_module.html

### Start service mysql, if not started
``` shell
ansible database -i hosts -m service -a "name=mysql state=started"
 ```
### Restart service mysql, in all cases
``` shell
ansible database --become -i hosts -m service -a "name=mysql state=restarted"
 ```
### Use Ansible to reboot the webstack
``` shell
ansible webstack -i hosts --become -a "reboot --reboot"
 ```

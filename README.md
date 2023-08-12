# Ansible Labs

## How to use these Labs
1. Install Oracle Virtual Box:  https://www.virtualbox.org/

2. Install Vagrant: https://www.vagrantup.com/downloads.html

3. In a new Directory copy this respository:
``` shell
https://github.com/bisrikarim/Ansible-labs.git
```

4. Start the vagrant instance.
``` shell
vagrant up
```

5. It depends on your ip addresses, add those line in /etc/hosts file in all servers
``` shell
$ nano /etc/hosts
192.168.30.231  ansible-control
192.168.30.232  db01
192.168.30.233  web01
192.168.30.234  web02
192.168.30.235  loadbalancer
```

6. SSH into the ansible-control virtual machine.
``` shell
vagrant ssh ansible-control
```

7. Install Ansible in control-ansible server
``` shell
$ sudo apt install ansible -y
```

8. Install Python in all machines
``` shell
$ sudo apt install python -y
```

9. Generate an SSH key pair in ansible-control server
``` shell
$ ssh-keygen
```

10. Copy the SSH key pair in all other servers
``` shell
$ ssh-copy-id db01 && ssh-copy-id web01 && ssh-copy-id web02 && ssh-copy-id loadbalancer
```

11. Test ssh connection to all other servers
``` shell
$ ssh vagrant@db01
$ ssh vagrant@web01
$ ssh vagrant@web02
$ ssh vagrant@loadbalancer
```




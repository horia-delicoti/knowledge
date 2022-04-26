# [Ansible](https://www.ansible.com/)

Ansible is an open source automation platform that can help with config management, deployment and task automation

## Resources

- [Documentation](https://docs.ansible.com/ansible/latest/index.html)
- [Ansible for DevOps by Jeff Geerling](https://cloud.delicoti.com/d/f/o444VDABw5cbJMBcs9u7BKLgymDjkFGy)
- [Ansible 101 with Jeff Gerrling](https://www.youtube.com/playlist?list=PL2_OBreMn7FqZkvMYt6ATmgC0KAGGJNAN)
- [An Ansible2 Tutorial](https://serversforhackers.com/c/an-ansible2-tutorial)
- [Awesome Ansible](https://github.com/KeyboardInterrupt/awesome-ansible)
- [Ansible Molecule](https://molecule.readthedocs.io/en/latest/)

## Ad-Hoc Commands
Access the ansible box with

```
# ping all nodes (default inventory /etc/ansible/hosts)
ansible all -m ping

# ping all nodes (specify inventory)
ansible all -i "/vagrant/data/hosts" -m ping

# [gathering facts](https://docs.ansible.com/ansible/latest/user_guide/playbooks_vars_facts.html)
ansible -i iventory <hostname (or) hostgroup> -m setup

# specify host and user
ansible ip-192-168-100-11.local -m ping -u vagrant

# execute command
ansible all -a "/bin/echo hello"
ansible all -a "uptime"

# do NOT reboot vagrant through ansible (use vagrant reload)
ansible cluster -a "/sbin/reboot" --become

# shell module
ansible all -m shell -a "pwd"

# be carefull to quotes
ansible all -m shell -a 'echo $HOME'

# update && upgrade
ansible all -m apt -a "update_cache=yes upgrade=dist" --become

# restart after upgrade
vagrant reload

# install package
ansible all -m apt -a "name=tree state=present" --become
```
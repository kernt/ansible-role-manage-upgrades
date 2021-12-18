Role Name
=========

Manage Upgrades on small company step by step.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

To make a secure upgrade check /var/run/reboot-required on Debian like Os or /usr/bin/needs-restarting on RedHat like OS.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      any_errors_fatal: true # stop if anything is wrong
      serial: 1              # one server at a time
      roles:
         - { role: ansible-role-manage-upgrades }
         
Do tests
-----------
You can tests on localhost in /tests.

`ansible-playbook -i inventory test.yml`

also is a good solution with [ansible-pull](https://docs.ansible.com/ansible/latest/cli/ansible-pull.html), too.


Do Upgrades
-----------

## Upgrade all the Ubuntu servers.
ansible ubuntu -m apt -a "upgrade=yes update_cache=yes" -b

## Upgrade all the Debian servers.
ansible debian -m apt -a "upgrade=yes update_cache=yes" -b

## Upgrade all the CentOS servers.
ansible centos -m yum -a "name=* state=latest" -b

## Upgrade all the Fedora servers.
ansible fedora -m dnf -a "name=* state=latest" -b

## Reboot all servers
ansible all -a "reboot" -s

monitor the progress with wait_for and connection: local

Sources
-------

* [rundum-updaten-mit-ansible](https://www.netways.de/blog/2018/05/04/rundum-updaten-mit-ansible/)
* [ansible-apt-update-all-packages-on-ubuntu-debian-linux](https://www.cyberciti.biz/faq/ansible-apt-update-all-packages-on-ubuntu-debian-linux/)
* [ansible-role-unattended-upgrades](https://github.com/jnv/ansible-role-unattended-upgrades)
* [list-of-ansible-os-family-distributions-facts](https://techviewleo.com/list-of-ansible-os-family-distributions-facts/)
* [ansible-role-dnf-automatic](http://github.com.https.443.262d333a6b.a.proxy1.ipv6.xiangtan.gov.cn/D4N/ansible-role-dnf-automatic)
* [ansible-role-dnf-automatic 2](https://github.com/centinel/ansible-role-dnf-automatic)
* [Ansible dnf module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)
* [upgrade-reboot-linux-systems-using-ansible](https://techviewleo.com/upgrade-reboot-linux-systems-using-ansible/)
* [ansible role update ubuntu](Ahttps://github.com/itnok/ansible-role-update-ubuntu)
* [yum_update_reboot.yml](https://thenathan.net/wp-content/uploads/2020/07/yum_update_reboot.yml_.txt)
* [ansible-role-upgrade](https://github.com/thorian93/ansible-role-upgrade)
* [reboot-and-wait-reboot-complete-ansible-playbook](https://www.jeffgeerling.com/blog/2018/reboot-and-wait-reboot-complete-ansible-playbook)
* [ansible-rolling-reboot](https://github.com/dareko/ansible-rolling-reboot)
* [ansible-rolling-update-or-deployment](https://danasmera.com/ansible-rolling-update-or-deployment)
* [Ansible-and-rolling-upgrades](https://gquintana.github.io/2017/07/15/Ansible-and-rolling-upgrades.html)
* [how-to-find-out-if-my-ubuntudebian-linux-server-needs-a-reboot](https://www.cyberciti.biz/faq/how-to-find-out-if-my-ubuntudebian-linux-server-needs-a-reboot/)
* [reboot-is-required-on-rhel-or-centos](https://serverfault.com/questions/122178/how-can-i-check-from-the-command-line-if-a-reboot-is-required-on-rhel-or-centos)
* [how-to-check-if-centos-rhel-needs-a-full-reboot](https://www.cyberciti.biz/faq/how-to-check-if-centos-rhel-needs-a-full-reboot/)

License
-------

BSD

Author Information
------------------

Tobias Kern linux system administrator

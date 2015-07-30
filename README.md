Role Name
=========

Installs keepalived http://www.keepalived.org/

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

````
config_keepalived: false
keepalived_router_id: 55  #defines router id...must be unique per subnet
keepalived_router_pri: 101  #defines router priority....each node must be different....best to define in host_vars
keepalived_vip_int: '{{ ansible_default_ipv4.interface }}'  #defines interface to use for VIP
notify_backup_script: backup.sh
notify_fault_script: fault.sh
notify_master_script: master.sh
````

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: mrlesmithjr.keepalived }

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

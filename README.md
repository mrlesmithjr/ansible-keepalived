Role Name
=========

Installs keepalived http://www.keepalived.org/

Requirements
------------

None...unless using GlusterFS

Role Variables
--------------

````
---
# defaults file for ansible-keepalived
config_keepalived: false
keepalived_router_id: 55  #defines router id...must be unique per subnet
keepalived_router_pri: 101  #defines router priority....each node must be different....best to define in host_vars
keepalived_scripts_mnt: ''  #define if using GlusterFS
keepalived_vip: 192.168.1.200  #defines the VIP to use
keepalived_vip_int: '{{ ansible_default_ipv4.interface }}'  #defines interface to use for VIP
notify_backup_script: backup.sh
notify_fault_script: fault.sh
notify_master_script: master.sh
primary_gfs_server: ''  #define if using GlusterFS
scripts_home: ''  #define if using GlusterFS
secondary_gfs_server: ''  #define if using GlusterFS
sync_keepalived: false  #defines if keepalived should be synced when using with GlusterFS
````

Dependencies
------------

None...unless using GlusterFS


Example Playbook
----------------
#### GitHub
````
- hosts: all
  remote_user: remote
  become: true
  vars:
  roles:
    - role: ansible-keepalived
  tasks:
````
#### Galaxy
````
- hosts: all
  remote_user: remote
  become: true
  vars:
  roles:
    - role: mrlesmithjr.keepalived
  tasks:
````

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

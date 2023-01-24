coffeesprout.nfs
===================

Set's up NFS client for FreeBSD and Linux

Requirements
------------

FreeBSD 11 Base; Some packages are installed on Linux

Role Variables
--------------

    nfs_server

The IP or hostname for the server

    nfs_mounts:
    - destination: /mnt/local/path
      nfs_path: share1 

A list of nfs\_mounts and their local destinations

Dependencies
------------


Example Playbook
----------------
    - hosts: servers
      vars:
      roles:
      - role: coffeesprout.nfs
        nfs_server: 192.168.1.1
        nfs_mounts:
        - destination: "/mnt/shared"
          nfs_path: "volume_name/share"  

License
-------

BSD

Author Information
------------------

Just reach out on Github

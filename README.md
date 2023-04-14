coffeesprout.nfs
===================

Sets up NFS client for FreeBSD and Linux

Overview
--------

This role sets up an NFS client for both FreeBSD and Linux systems, allowing seamless file sharing between these operating systems. It takes care of the necessary package installations, configuration, and mounting of NFS shares.

Requirements
------------

- FreeBSD 11 Base
- Some packages are installed on Linux

Ensure that the necessary ports are open for NFS communication. The standard ports for NFS include:

- 111 (TCP and UDP) for the portmapper service
- 2049 (TCP and UDP) for the NFS server
- 892 (TCP and UDP) for the mountd service
- 662 (TCP and UDP) for the rpc.statd service

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

None

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

If you have any questions, suggestions, or issues, please feel free to reach out on Github.


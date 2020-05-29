# NFS
Bringing machine 'server' up with 'virtualbox' provider...
Bringing machine 'client' up with 'virtualbox' provider...
==> server: You assigned a static IP ending in ".1" to this machine.
==> server: This is very often used by the router and can cause the
==> server: network to not work properly. If the network doesn't work
==> server: properly, try changing this IP.
==> server: Importing base box 'centos/7'...
==> server: Matching MAC address for NAT networking...
==> server: You assigned a static IP ending in ".1" to this machine.
==> server: This is very often used by the router and can cause the
==> server: network to not work properly. If the network doesn't work
==> server: properly, try changing this IP.
==> server: Setting the name of the VM: NFS_server_1590752849706_66763
==> server: Clearing any previously set network interfaces...
==> server: Preparing network interfaces based on configuration...
    server: Adapter 1: nat
    server: Adapter 2: hostonly
==> server: Forwarding ports...
    server: 22 (guest) => 2222 (host) (adapter 1)
==> server: Booting VM...
==> server: Waiting for machine to boot. This may take a few minutes...
    server: SSH address: 127.0.0.1:2222
    server: SSH username: vagrant
    server: SSH auth method: private key
    server:
    server: Vagrant insecure key detected. Vagrant will automatically replace
    server: this with a newly generated keypair for better security.
    server:
    server: Inserting generated public key within guest...
    server: Removing insecure key from the guest if it's present...
    server: Key inserted! Disconnecting and reconnecting using new SSH key...
==> server: Machine booted and ready!
==> server: Checking for guest additions in VM...
    server: No guest additions were detected on the base box for this VM! Guest
    server: additions are required for forwarded ports, shared folders, host only
    server: networking, and more. If SSH fails on this machine, please install
    server: the guest additions and repackage the box to continue.
    server:
    server: This is not an error message; everything may continue to work properly,
    server: in which case you may ignore this message.
==> server: Setting hostname...
==> server: Configuring and enabling network interfaces...
==> server: Rsyncing folder: /home/sur/nfs/NFS/ => /vagrant
==> server: Running provisioner: ansible...
    server: Running ansible-playbook...

PLAY [Add records to /etc/hosts] ***********************************************

PLAY [Configure nfs server] ****************************************************

TASK [nfs-server : Creates directory to share] *********************************
changed: [server]

TASK [nfs-server : config export dir] ******************************************
changed: [server]

TASK [nfs-server : start firewalld] ********************************************
changed: [server]

TASK [nfs-server : add eth1 to internal zone] **********************************
changed: [server]

TASK [nfs-server : enable nfs server] ******************************************
changed: [server]

TASK [nfs-server : enable rpc-bind] ********************************************
changed: [server]

TASK [nfs-server : enable mountd] **********************************************
changed: [server]

RUNNING HANDLER [nfs-server : restart nfs] *************************************
changed: [server]
 [WARNING]: Could not match supplied host pattern, ignoring: client


PLAY [Configure nfs client] ****************************************************
skipping: no hosts matched

PLAY RECAP *********************************************************************
server                     : ok=8    changed=8    unreachable=0    failed=0

==> client: Importing base box 'centos/7'...
==> client: Matching MAC address for NAT networking...
==> client: Setting the name of the VM: NFS_client_1590752897322_90828
==> client: Fixed port collision for 22 => 2222. Now on port 2200.
==> client: Clearing any previously set network interfaces...
==> client: Preparing network interfaces based on configuration...
    client: Adapter 1: nat
    client: Adapter 2: hostonly
==> client: Forwarding ports...
    client: 22 (guest) => 2200 (host) (adapter 1)
==> client: Booting VM...
==> client: Waiting for machine to boot. This may take a few minutes...
    client: SSH address: 127.0.0.1:2200
    client: SSH username: vagrant
    client: SSH auth method: private key
    client:
    client: Vagrant insecure key detected. Vagrant will automatically replace
    client: this with a newly generated keypair for better security.
    client:
    client: Inserting generated public key within guest...
    client: Removing insecure key from the guest if it's present...
    client: Key inserted! Disconnecting and reconnecting using new SSH key...
==> client: Machine booted and ready!
==> client: Checking for guest additions in VM...
    client: No guest additions were detected on the base box for this VM! Guest
    client: additions are required for forwarded ports, shared folders, host only
    client: networking, and more. If SSH fails on this machine, please install
    client: the guest additions and repackage the box to continue.
    client:
    client: This is not an error message; everything may continue to work properly,
    client: in which case you may ignore this message.
==> client: Setting hostname...
==> client: Configuring and enabling network interfaces...
==> client: Rsyncing folder: /home/sur/nfs/NFS/ => /vagrant
==> client: Running provisioner: ansible...
    client: Running ansible-playbook...

PLAY [Add records to /etc/hosts] ***********************************************

PLAY [Configure nfs server] ****************************************************
skipping: no hosts matched

PLAY [Configure nfs client] ****************************************************

TASK [nfs-client : Creates directory to mount] *********************************
changed: [client]

TASK [nfs-client : install autofs] *********************************************
changed: [client]

TASK [nfs-client : copy autofs share config] ***********************************
changed: [client]

TASK [nfs-client : copy autofs map for share folder] ***************************
changed: [client]

RUNNING HANDLER [nfs-client : restart autofs] **********************************
changed: [client]

PLAY RECAP *********************************************************************
client                     : ok=5    changed=5    unreachable=0    failed=0


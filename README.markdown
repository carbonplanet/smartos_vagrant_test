# smartos_vagrant_test

Purposes of this repo is to demonstrate:
- SmartOS global zone running in Vagrant
- OS zone (container) running within it
- Provide a foundation with which to attempt importing SmartOS containers from other servers

## Running

```
vagrant plugin install vagrant-smartos-zones
vagrant up
```

You should then be able to ssh in to the global zone using `vagrant global-zone ssh` eg:

```
jesse@SoMuchFSubtlety smartos_vagrant_test $ vagrant global-zone ssh
Last login: Wed Aug 19 02:45:52 2015 from 10.0.2.2
- SmartOS Live Image v0.147+ build: 20150806T063417Z
vagrant@08-00-27-ac-b1-65:~$ sudo su -
- SmartOS Live Image v0.147+ build: 20150806T063417Z
You have new mail.
[root@08-00-27-ac-b1-65 ~]# uname -a
SunOS 08-00-27-ac-b1-65 5.11 joyent_20150806T063417Z i86pc i386 i86pc
[root@08-00-27-ac-b1-65 ~]#

# inspect the running containers:

[root@08-00-27-ac-b1-65 ~]# vmadm list
UUID                                  TYPE  RAM      STATE             ALIAS
09306c91-f497-43a5-bced-5f4c8d064ff2  OS    1536     running           base64

# exit back to your host OS:

[root@08-00-27-ac-b1-65 ~]# exit
logout
vagrant@08-00-27-ac-b1-65:~$ exit
logout
Connection to 127.0.0.1 closed.
```

Or into the local zone (container) using `vagrant ssh` eg:

```
jesse@SoMuchFSubtlety smartos_vagrant_test $ vagrant ssh
Last login: Wed Aug 19 02:44:35 2015 from 10.0.2.2
   __        .                   .
 _|  |_      | .-. .  . .-. :--. |-
|_    _|     ;|   ||  |(.-' |  | |
  |__|   `--'  `-' `;-| `-' '  ' `-'
                   /  ; Instance (base64 14.2.0)
                   `-'  http://wiki.joyent.com/jpc2/SmartMachine+Base

[vagrant@09306c91-f497-43a5-bced-5f4c8d064ff2 ~]$ uname -a
SunOS 09306c91-f497-43a5-bced-5f4c8d064ff2 5.11 joyent_20150806T063417Z i86pc i386 i86pc Solaris
```




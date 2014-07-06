EpsFS
=====
##Kind of docs (also a very good example of how you sholudn't write a documentation)


* Mounting the fs

run:
``$groups <usename>``

if you don't see fuse there, add it using:

``$sudo addgroup <username> fuse``

To remove a user from a group use:

``sudo deluser tim fuse``

restart your session ``$ cinnamon-session-exit``

* Dont forget to show off how secure the mount operation is:

not even the root user can access the filesystem mounted by my user even
though the root has files inside my filesystem on which he has permissions
(ubeer cool, right ?!?! )
i.e. any other user trying to access my mount point will see the following
permission set:
``d????????? ? ?    ?       ?            ?``



* Connecting to my custom ssh server:
    ``ssh user@127.0.0.1 -p 8022 #localhost - not really cool``

    ``ssh user@192.168.1.x -p 8022 #cooler but you have to setup port fwd on the router``

* When generatin' ssh keys use ``-b 1024`` argument


* USER MANAGEMENT - posix standard way
``sudo useradd <uname>``

``sudo passwd <uname>``

the user wil also have a ``/home/<username>/media`` directory
this will act like the global /media directory


use ``awk`` to get the available sys users and uids
``awk -F":" '{ print $1 ";" $3 }' /etc/passwd``

*if your system ever crashes, unmount the mountpoint using:
    ``fusermount -u <mount_dir>``

*i linked the bash_history file to /dev/null just to make user's history more secure
    ``ln /dev/null .bash_history -sf``


netstat -atpn|grep ssh

# linuxmuster-linbo-postsync
This repository offers a universal postsync-script for linuxmuster.net v7.2.
A postsync-script patches a linux client having synced with linbo according to different hostnames, rooms or special configurations necessities.

The universal postsync script is located in the directory 
<code>
/srv/linbo/images/<LinuxImageVerzeichnis>/<LinuxImageName>.postsync
</code>

The script looks for patch classes to search for files or directories to be altered on the linux client by the postsync script. 

Patch classes are located in the directory 
<code>
/srv/linbo/linuxmuster-client/
</code>

e.g.
<code>
/srv/linbo/linuxmuster-client/focalfossa/  # focalfossa is a patch class
/srv/linbo/linuxmuster-client/popos2204/   # popos2204 is a patch class
</code>
For each patch class there has to be a subdirectory for files for all clients in this image class and a subdirectory for script to be executed on each linux client in the patch class.

patch class **focalfossa**:
<p>
<code>
/srv/linbo/linuxmuster-client/focalfossa/common/                       # directory for files patched for all linux clients in the patch class focalfossa
/srv/linbo/linuxmuster-client/focalfossa/common/etc/cups/cups.conf     # cups file to be written to all linux clients in the patch class focalfossa
/srv/linbo/linuxmuster-client/focalfossa/r100/                         # directory for patches for all linux clients in room r100 which are in patch class focalfoss
/srv/linbo/linuxmuster-client/focalfossa/r100-pc01/                    # directory for patches for linux client pc01 in room r100
/srv/linbo/linuxmuster-client/focalfossa/r100-pc01/etc/apache/sites-available/000-default.conf # apache config file for the default site only patched on pc01 in room r100 being part of patchclass focalfossa
/srv/linbo/linuxmuster-client/focalfossa/postsync.d/                   # directory for scripts to be executed for all linux clients in the patch class focalfossa
/srv/linbo/linuxmuster-client/focalfossa/postsync.d/00-lcst-fix-initrd          #  fixing initrd links
/srv/linbo/linuxmuster-client/focalfossa/postsync.d/01-lcst-setlocalpasswords   #  patching password hashes
/srv/linbo/linuxmuster-client/focalfossa/postsync.d/02-lcst-patch-sshd-config   #  patching sshd_config for server root
/srv/linbo/linuxmuster-client/focalfossa/postsync.d/03-lcst-fix-fstab           #  fixing fstab
/srv/linbo/linuxmuster-client/focalfossa/postsync.d/04-lcst-generate-hosts      #  fixing hosts, network settings
</code>
</p>

patchclass **popos2204**:
<code>
/srv/linbo/linuxmuster-client/popos2204/common/                        # directory for files patched for all linux clients in the patch class popos2204
/srv/linbo/linuxmuster-client/popos2204/common/etc/cups/cups.conf      # cups file to be written to all linux clients in the patch class popos2204
/srv/linbo/linuxmuster-client/popos2204/r100/                          # directory for patches for all linux clients in room r100 which are in patch class popos2204
/srv/linbo/linuxmuster-client/popos2204/r100-pc01/                     # directory for patches for linux client pc01 in room r100
/srv/linbo/linuxmuster-client/popos2204/r100-pc01/etc/apache/sites-available/000-default.conf # apache config file for the default site only patched on pc01 in room r100 being part of patchclass popos2204
/srv/linbo/linuxmuster-client/popos2204/postsync.d/                    # directory for scripts to be executed for all linux clients in the patch class popos2204
/srv/linbo/linuxmuster-client/popos2204/postsync.d/00-lcst-fix-initrd          #  fixing initrd links
/srv/linbo/linuxmuster-client/popos2204/postsync.d/01-lcst-setlocalpasswords   #  patching password hashes
/srv/linbo/linuxmuster-client/popos2204/postsync.d/02-lcst-patch-sshd-config   #  patching sshd_config for server root
/srv/linbo/linuxmuster-client/popos2204/postsync.d/03-lcst-fix-fstab           #  fixing fstab
/srv/linbo/linuxmuster-client/popos2204/postsync.d/04-lcst-generate-hosts      #  fixing hosts, network settings
</code>



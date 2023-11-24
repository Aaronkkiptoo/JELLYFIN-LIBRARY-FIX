# JELLYFIN-LIBRARY-FIX
If you encounter the common library error on jellyfin then maybe your problem might be related to mine.This should fix it!

THE PROBLEM:
I run Jellyfin in a docker container of a debian vm running in proxmox. I therefore need to mount my truenas share drive which 
has all my libraries. Sadly debian does not auto mount for you after each startup and with no libraries , Jellyfin wont work 

FIX:
This is a simple bash script I have made and thought some of you might need!
All it does is:
-clears the terminal
-mounts the drive(you will need to edit your fstab file)
-restarts jellyfin(docker restart jellyfin)
-clears the terminal 

YOU WILL NEED TO RUN THIS AS SUPER USER

STEPS:
1.Edit your fstab to mount your truenas share folder
(#truenas
//192.168.x.x/xxxx /mnt/truenas/ cifs credentials=/etc/.truenas_creds,iocharset=utf8,uid=1000,gid=1000,noperm 0 0)
)*should look like this*

2.Make the truenas directory 
  (mkdir /mnt/truenas)
  
3.Download the .sh file

4.Make it executable
  (chmod +x jellyfin.sh)

5.Run as super user
 (su)


ENJOY!!
 
 

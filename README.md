# DevOps

System administration: **CentOS** and **REHL**

Files

###1) Local to remote file transfer
sudo scp -i (.pem file location of dest. host) (concerned file name)  (remote username)@(remote IP):(remote directory)
Ex: sudo scp -i /var/www/test/akbmigration.pem akibuki.tar.gz  ubuntu@18.142.122.236:/var/www/akibuki.co.uk

###2) Making tar/zip file 
sudo tar -czvf akibuki.tar.gz /var/www/akibuki.co.uk
Ex:sudo tar -czvf akibuki.tar.gz /var/www/akibuki.co.uk
 
###3) Untar/Unzip files to new directory
sudo tar -xzvf [filename.tar.gz] -C [new path]

###System Info on starting
step 1: Create a file nano /etc/profile.d/motd.sh

#!/bin/bash
#
echo -e "
──────────────────────────────────────────────────────────────────────
               • Welcome To `hostname` •                    						 
            (Web1.Com and web2.com is running here)               					       	 
──────────────────────────────────────────────────────────────────────
✔  This System is running on `egrep '^(VERSION|NAME)=' /etc/*release`
──────────────────────────────────────────────────────────────────────
✔  You are logged in as: `whoami`
──────────────────────────────────────────────────────────────────────
✔  CPU and RAM Uses:                
`top | head -10`    
──────────────────────────────────────────────────────────────────────          
✔   Disk Information:              
`df -h | head -4`   
──────────────────────────────────────────────────────────────────────                      
"
step 2: Restart SSHd: systemctl restart sshd.service


#Nwtworking

Check public IP
curl ifconfig.me

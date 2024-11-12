┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo apt update
Get:1 http://kali.download/kali kali-rolling InRelease [41.5 kB]
Get:2 http://kali.download/kali kali-rolling/main arm64 Packages [20.1 MB]
Get:3 http://kali.download/kali kali-rolling/main arm64 Contents (deb) [47.3 MB]
Get:4 http://kali.download/kali kali-rolling/contrib arm64 Packages [96.3 kB]
Get:5 http://kali.download/kali kali-rolling/contrib arm64 Contents (deb) [191 kB]
Get:6 http://kali.download/kali kali-rolling/non-free arm64 Packages [155 kB]
Get:7 http://kali.download/kali kali-rolling/non-free arm64 Contents (deb) [829 kB]
Get:8 http://kali.download/kali kali-rolling/non-free-firmware arm64 Packages [9704 B]
Get:9 http://kali.download/kali kali-rolling/non-free-firmware arm64 Contents (deb) [22.3 kB]
Fetched 68.7 MB in 26s (2633 kB/s)                                          
1916 packages can be upgraded. Run 'apt list --upgradable' to see them.
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo apt install apache2 -y
Upgrading:                      
  apache2  apache2-bin  apache2-data  apache2-utils
                                                                             
Summary:
  Upgrading: 4, Installing: 0, Removing: 0, Not Upgrading: 1912
  Download size: 1871 kB
  Freed space: 62.5 kB

Get:1 http://kali.download/kali kali-rolling/main arm64 apache2 arm64 2.4.62-3 [217 kB]
Get:2 http://kali.download/kali kali-rolling/main arm64 apache2-bin arm64 2.4.62-3 [1287 kB]
Get:4 http://mirror.telepoint.bg/kali kali-rolling/main arm64 apache2-utils arm64 2.4.62-3 [208 kB]
Get:3 http://kali.download/kali kali-rolling/main arm64 apache2-data all 2.4.62-3 [160 kB]
Fetched 1871 kB in 1s (2430 kB/s)                                         
(Reading database ... 407648 files and directories currently installed.)
Preparing to unpack .../apache2_2.4.62-3_arm64.deb ...
Unpacking apache2 (2.4.62-3) over (2.4.62-1) ...
Preparing to unpack .../apache2-bin_2.4.62-3_arm64.deb ...
Unpacking apache2-bin (2.4.62-3) over (2.4.62-1) ...
Preparing to unpack .../apache2-data_2.4.62-3_all.deb ...
Unpacking apache2-data (2.4.62-3) over (2.4.62-1) ...
Preparing to unpack .../apache2-utils_2.4.62-3_arm64.deb ...
Unpacking apache2-utils (2.4.62-3) over (2.4.62-1) ...
Setting up apache2-bin (2.4.62-3) ...
Setting up apache2-data (2.4.62-3) ...
Setting up apache2-utils (2.4.62-3) ...
Setting up apache2 (2.4.62-3) ...
apache2.service is a disabled or a static unit not running, not starting it.
apache-htcacheclean.service is a disabled or a static unit not running, not starting it.
Processing triggers for kali-menu (2024.3.1) ...
Processing triggers for man-db (2.12.1-2) ...
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo systemctl start apache2
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo systemctl enable  apache2
Synchronizing state of apache2.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable apache2
Created symlink '/etc/systemd/system/multi-user.target.wants/apache2.service' → '/usr/lib/systemd/system/apache2.service'.
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo apt install ufw -y       
Installing:                     
  ufw
                                                                             
Suggested packages:
  rsyslog

Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1912
  Download size: 169 kB
  Space needed: 880 kB / 49.5 GB available

Get:1 http://kali.download/kali kali-rolling/main arm64 ufw all 0.36.2-8 [169 kB]
Fetched 169 kB in 1s (320 kB/s)
Preconfiguring packages ...
Selecting previously unselected package ufw.
(Reading database ... 407648 files and directories currently installed.)
Preparing to unpack .../archives/ufw_0.36.2-8_all.deb ...
Unpacking ufw (0.36.2-8) ...
Setting up ufw (0.36.2-8) ...

Creating config file /etc/ufw/before.rules with new version

Creating config file /etc/ufw/before6.rules with new version

Creating config file /etc/ufw/after.rules with new version

Creating config file /etc/ufw/after6.rules with new version
update-rc.d: We have no instructions for the ufw init script.
update-rc.d: It looks like a non-network service, we enable it.
Created symlink '/etc/systemd/system/multi-user.target.wants/ufw.service' → '/usr/lib/systemd/system/ufw.service'.
Processing triggers for kali-menu (2024.3.1) ...
Processing triggers for man-db (2.12.1-2) ...
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo ufw enable        
Firewall is active and enabled on system startup
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo ufw allow 80/tcp
Rule added
Rule added (v6)
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo ufw allow from 1.1.1.1 to any port 3306
Rule added
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo ufw allow 143/tcp                      
Rule added
Rule added (v6)
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo ufw allow 993/tcp
Rule added
Rule added (v6)
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo ufw allow from 8.8.8.8 to any          
Rule added
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo ufw status verbose           
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
80/tcp                     ALLOW IN    Anywhere                  
3306                       ALLOW IN    1.1.1.1                   
143/tcp                    ALLOW IN    Anywhere                  
993/tcp                    ALLOW IN    Anywhere                  
Anywhere                   ALLOW IN    8.8.8.8                   
80/tcp (v6)                ALLOW IN    Anywhere (v6)             
143/tcp (v6)               ALLOW IN    Anywhere (v6)             
993/tcp (v6)               ALLOW IN    Anywhere (v6)             

                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# sudo systemctl status  apache2
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/usr/lib/systemd/system/apache2.service; enabled; prese>
     Active: active (running) since Wed 2024-11-13 01:04:05 +03; 7min ago
 Invocation: d77dd37d515040afad921d540da921e7
       Docs: https://httpd.apache.org/docs/2.4/
   Main PID: 46604 (apache2)
      Tasks: 6 (limit: 2205)
     Memory: 22.2M (peak: 22.6M)
        CPU: 93ms
     CGroup: /system.slice/apache2.service
             ├─46604 /usr/sbin/apache2 -k start
             ├─46607 /usr/sbin/apache2 -k start
             ├─46608 /usr/sbin/apache2 -k start
             ├─46609 /usr/sbin/apache2 -k start
             ├─46610 /usr/sbin/apache2 -k start
             └─46611 /usr/sbin/apache2 -k start

Nov 13 01:04:05 kali-linux-2024-2 systemd[1]: Starting apache2.service - The>
Nov 13 01:04:05 kali-linux-2024-2 systemd[1]: Started apache2.service - The >

                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# exit

Script done on 2024-11-13 01:12:02+03:00 [COMMAND_EXIT_CODE="130"]
                                                                             
┌──(root㉿kali-linux-2024-2)-[~]
└─# 

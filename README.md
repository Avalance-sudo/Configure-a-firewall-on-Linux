# Configure-a-firewall-on-Linux
Firewalled is an open source that seeks to prevent unauthorized access to your computer. 



ufw status 
sudo ufw status {satus inactive}
sudo ufw enable (firewall is active and enabled on system statup)
sudo ufw status {Status: active}
sudo ufw status verbose {Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip}
sudo ufw default deny outgoing {Default outgoing policy changed to 'deny'
(be sure to update your rules accordingly)}

sudo ufw status verbose {Status: active
Logging: on (low)
Default: deny (incoming), deny (outgoing), disabled (routed)
New profiles: skip}

sudo ufw default allow incoming 
Default incoming policy changed to 'allow'
(be sure to update your rules accordingly)

sudo ufw default allow outgoing 
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)

sudo ufw default dny outgoing 
Default outgoing policy changed to 'deny'
(be sure to update your rules accordingly)

sudo ufw status verbose
Status: active
Logging: on (low)
Default: allow (incoming), deny (outgoing), disabled (routed)
New profiles: skip


sudo ufw default allow incoming 
Default incoming policy changed to 'allow'
(be sure to update your rules accordingly)

sudo ufw status verbose 
Status: active
Logging: on (low)
Default: allow (incoming), deny (outgoing), disabled (routed)
New profiles: skip

clear

sudo ufw default deny incoming 
Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)

sudo ufw default deny outgoing 
Default outgoing policy changed to 'deny'
(be sure to update your rules accordingly)

sudo ufw status verbose 
Status: active
Logging: on (low)
Default: deny (incoming), deny (outgoing), disabled (routed)
New profiles: skip

ip a

sudo ufw allow in on ens33 from 8.8.8.8
Rule added

sudo ufw status verbose 


sudo ufw allow from 8.8.8.8
sudo ufw status numbered 
sudo ufw delete 1 

sudo ufw status verbose 
sudo ufw allow from 8.8.8.8 proto tcp to any port 22 
sudo ufw status verbose 
ping 8.8.8.8
sudo udw disable 
sudo ufw status 
ping 8.8.8.8
sudo ufw enable 
sudo ufw default allow outgoing 
sudo apt install vim 







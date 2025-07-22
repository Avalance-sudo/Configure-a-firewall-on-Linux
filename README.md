# Configure-a-firewall-on-Linux

# Summary 
This project demonstrates how configure a basic firewall on Linux system useing ```ufw``` a user friendly interface for managing iptables rules.The goal was to create a secure environment by defining strict incoming and outgoing traffic rules. Then allowing only trusted IP addresses and specific ports. 

# Key Features:
- Enabled and verified ufw firewall status

- Customized default policies (e.g., deny all incoming/outgoing traffic)

- Allowed specific IP addresses and ports (e.g., Google DNS and SSH)

- Updated and tested rules using ufw status, numbered, and delete

- Verified network accessibility with ping and network commands

- Demonstrated how to temporarily disable and re-enable the firewall

- Installed essential tools (like vim) after reallowing outbound traffic


# Objective: 
Set up and manage a secure firwall using UFW (Uncomplicated Firewall) to control incoming and outgoing network traffic on your Linux system. 

# What is UFW?
UFW stands for Uncomplicated Firewall. It's a user friendly command -line for managing iptables firewall rules.It simplifies thr process of configuring a firewall and is commonly used on Ubuntu.


# Step by Step:

# Step 1: Check UFW Status 
```sudo ufw status```
-This shows wheather the firewall is active or inactive.
Output:
```sudo ufw status {satus inactive}```

# Step 2: Enable the Firewall 
```sudo ufw enable``` (firewall is active and enabled on system statup)

- Activates the firewall and enables it at startup
- You should now see:
      Firewall is active and enabled on system startup

# Step 3: Check Detailed Status:

-Gives a deeper view of settings: 

```Logging: on (low)```

```Default: deny (incoming), allow (outgoing), disabled (routed)```

# Step 4: Set Default Policies 

Deny All outgoign Connections
```sudo ufw default deny outgoing ```

-This chages the default to block all outgoing traffic it can casue you to lose internet if you don't allow specific traffic
  
Allow All Outgoing Connections (reset):

``` sudo  ufw default allow outgoing```

-Allows all apps to send data out by default 

Deny All Incoming Connections:

``` sudo default deny incoming ```
- Best for security-blocks all inbound connections unless explicity allowed.

  Allow All Incoming Connections (less secure)

  ```sudo ufw default allow incoming ```

  # Step 5: Allow Specific Connections

  Example: Allow a trusted Ip (like Google DNS 8.8.8.8) to access your system:

  ```sudo ufw allow from 8.8.8.8```
  -Allow all traffic from that IP.
  Example: Only allow SSH (port 22) from a trusted IP:
  
  ```sudo ufw allow from 8.8.8.8 proto tcp to any port 22```

  # Step 6: Allow By Network Interface:
  
  ```sudo ufw allow in on ens33 from 8.8.8.8```
  -en33 is your network adapter-you can find yours useing:

  ```ip a```

  # STEP 7: Deleting Rules:
  
  ```sudo ufw status numbered```
  
  -List rules with numbers
  
  ```sudo ufw delete 1```
  
  -Deleted the rule at posititon 1

  # Step 8: Disable the Firewall

  ```sudo ufw disable```
  
  -Temporarily stops the firewall.

  ```sudo ufw enable```
  
  -Turns it back on

  # Step 9: Useful Commands
-Clear ll rules: 

```sudo ufw reset```

-Install Vim (or any package) after enabling outgoing: 

```sudo apt install vim```

-Ping a website to check access:

```ping 8.8.8.8```

#  Secure setup:
Block all incoming and outgoing traffic:

```sudo ufw default deny incoming```
```sudo ufw default deny outgoing```
Allow only SSH from a trusted IP:

```sudo ufw allow from 8.8.8.8 proto tcp to any port 22```

Enable firewall:

```sudo ufw enable```

Check status:

```sudo ufw status verbose```

# Conclusion 
This setup provides a foundational approach to securing a Linux machine using a firewall. By understanding and customizing ```ufw``` rules, so you can control who gets access to your system and what terms. 

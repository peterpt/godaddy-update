# Godaddy-Update

This is a simple script to those who have servers on a dynamic ip and
dont want to worry about changing their new ip at their domain in godaddy .

This script is based on the work of https://github.com/michaudg/godaddy-ddns
i wrote it for my server .
This script automatically verifies your ip every 10 minutes and check if your
godaddy needs to be updated or not .
This script creates a logfile with the output in /var/log/godaddy.log

# Requirements

- Curl
- touch
- jq

# Install Dependencies
apt-get install curl touch jq

# How to make it work .
Edit the file godaddy-update and paste there : 
- Your godaddy production API
- Your API Secret
- Your Domain name

- Save your changes

- Move the file godaddy-update to /usr/local/sbin folder

- Move godaddy-startup to /etc/network/if-up.d/

- Give execution permissions : chmod +x /usr/local/sbin/godaddy-update && chmod +x /etc/network/if-up.d/godaddy-startup

When you startup your server you will see in your init system 
the startup of the script .

# Notes
This script will run in background without disturbing your terminal , do not execute the script without 
changing first the domain config data .
if you need to stop the script then write in your terminal "pkill godaddy-update"


# Note 2
if you dont want to restart your server then after configuring all data in godaddy-update file write in your terminal

cd /usr/local/sbin

./godaddy-update &

- Godaddy script will run in a background process


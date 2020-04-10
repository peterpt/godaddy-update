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

Then move the file godaddy-update to /usr/local/sbin folder

Move also godaddy-startup to /etc/network/if-up.d/

When you startup your server you will see in your init system 
the startup of the script .


# checkmk
Installation of Checkmk using Ubuntu 22.04 ( Jammy )

Installation of Checkmk on UBUNTU 22.04 ( Jammy )

# 1. System Update and Upgrade and Installation of additional functions.

'''script
  sudo apt update && sudo apt upgrade -y
  sudo apt install wget curl gnupg2 -y

# 2. Download Checkmk Repository

wget https://download.checkmk.com/checkmk/2.4.0p8/check-mk-raw-2.4.0p8_0.jammy_amd64.deb

# 3. Installation of Checkmk

sudo apt install ./check-mk-raw-2.4.0p8_0.jammy_amd64.deb

# 4. Monitoring Site Creation

sudo omd create mysite

Note : You can replace mysite by any name you prefer all small caps letter no space

# 5. Start the site

sudo omd start mysite

# 6. Access the web interface

http://your-server-ip/site-name/

Note : You can check it on your VM running Ubuntu where you install the checkmk on ubuntu 22.04 you can open the firefox browser and type in the local IP which is http://127.0.0.1/mysite/ since the name of the site for this example is mysite.

# 7. Changing the password
Note : the default username is cmkadmin
to set the password

sudo su - mysite

Note : you will see something like this [ OMD[mysite]:~$ ]

Then input this command to change password

htpasswd etc/htpasswd cmkadmin

Then input your preferred password

then restart the checkmk by typing this command

omd restart

Note : if this command does not change its password try this instead.

sudo su - mysite

then this command

cmk-passwd cmkadmin

then restart [ odm restart ]

Then access again your checkmk and Login.

# Check IP address of UBUNTU

ip addr show

#Linux commands

#Basic commands
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install virtualbox-guest-dkms
sudo apt-get install virtualbox-guest-x11

#Add user rights to shared folder
sudo adduser %username% vboxsf

#Run python scripts
!/usr/bin/env python *.py
chmod 0755 *.py

#Forensic and analytics books
Forensics and Incident Response by Gerard Johansen
Network Intrusion Analysis by Steven Bolt, Joe Fichera

#SELKS
Usage and logon credentials (OS and web management user)
user: selks-user
password: selks-user (password in Live mode is live)
The default root password is StamusNetworks

#Debian credentials
Username: osboxes
Password: osboxes.org
Root Account Password: osboxes.org

#Debian repos
deb http://httpredir.debian.org/debian jessie main contrib
deb-src http://httpredir.debian.org/debian jessie main contrib

deb http://httpredir.debian.org/debian jessie-updates main contrib
deb-src http://httpredir.debian.org/debian jessie-updates main contrib

deb http://security.debian.org/ jessie/updates main contrib
deb-src http://security.debian.org/ jessie/updates main contrib 

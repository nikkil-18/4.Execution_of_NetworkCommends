# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## PROGRAM
~~~
CLIENT:
import socket

from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5)
c,addr=s.accept()

while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
~~~
~~~
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
~~~
## OUTPUT
CLIENT
<img width="615" height="131" alt="506375473-89219f0a-f10e-4d8f-971b-f31ac65de1b6" src="https://github.com/user-attachments/assets/576c1fbf-596d-44c3-9197-3a3c181b6f22" />

SERVER
<img width="720" height="332" alt="506375677-877263f1-81e9-4285-a12a-8af3e67c1355" src="https://github.com/user-attachments/assets/b156ede3-7e01-4136-9988-27a9b2316bf5" />

## Result
Thus Execution of Network commands Performed 

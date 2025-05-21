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

### PROGRAM:
### CLIENT:
```python
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
```

### SERVER:
```python
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRACE:
```python
from scapy.all import*     
target = ["www.google.com"]     
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output:
## ping:
![Screenshot 2025-05-20 175320](https://github.com/user-attachments/assets/3de2cbac-4b6d-44e8-b585-4b649c4575ca)
## tracert:
![Screenshot 2025-05-21 064906](https://github.com/user-attachments/assets/e3ffad13-1925-42aa-9b5f-2ecacf5a67ae)
## ipconfig:
![Screenshot 2025-05-21 064849](https://github.com/user-attachments/assets/242402e9-bfff-443a-807d-e2adfed18909)
## nbtstat:
![image](https://github.com/user-attachments/assets/f2456aae-63b2-41e1-99e8-b85839f478f3)
## nslookup:
![Screenshot 2025-05-21 064834](https://github.com/user-attachments/assets/46f7ad63-be16-4593-b3a1-84db11dcca6a)
## hostname and netstat:
![Screenshot 2025-05-21 064821](https://github.com/user-attachments/assets/20dd3817-7510-4dc8-ab12-9ed5ce91241d)
## getmac:
![Screenshot 2025-05-21 064759](https://github.com/user-attachments/assets/ad3cd728-e547-4f2c-bc6b-4eea6acebc9f)

## Result
Thus Execution of Network commands Performed 

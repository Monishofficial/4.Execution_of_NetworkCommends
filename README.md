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

## PROGRAM:

### CLIENT:
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
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
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

### TRACEOUT COMMAND:

```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
### PING ADDRESS
## CLIENT:
![Screenshot 2024-04-26 131109](https://github.com/Monishofficial/4.Execution_of_NetworkCommends/assets/149455421/6f1492e1-82d0-430c-bd4a-a9eb6749898c)

## SERVER:
![Screenshot 2024-04-26 131128](https://github.com/Monishofficial/4.Execution_of_NetworkCommends/assets/149455421/047a714b-2627-4ebb-8d86-e269382a95a2)

### TRACEOUT COMMAND:
![image](https://github.com/Monishofficial/4.Execution_of_NetworkCommends/assets/149455421/3f877dce-b5c2-4525-8f67-ad9a15a3241c)


## Result
Thus Execution of Network commands Performed 

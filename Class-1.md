
Programming Language(Need to learn)
----------------------------------------
Python
Java/ Java Script
C#

System Admin(Should Learn)
----------------------------------------
Programming(Java Script, Python)

IAC       >> Infrastructure as code, 
Terraform >> is an open-source infrastructure as code software tool. 
Jenkins   >> is a free and open source automation server. It helps automate the parts of software development 
	     related to building, testing, and deploying, facilitating continuous integration and continuous delivery. 
CI/CD     >> Continuous integration/continuous delivery 
Gitlab    >> GitLab is a web-based DevOps lifecycle tool that provides a Git-repository manager providing wiki, 
	     issue-tracking and continuous integration and deployment pipeline features 

Topics:
----------------------------------------
1. CI/CD
2. Docker/Kubernetes
3. AWS/ Azure
4. Networking 
5. Cloud Networking 
6. Software Engineering
7. Socket Binding
8. React
9. Vueis
10.Angular

Spaces:
----------------------------------------
User Space
Kernel Space
NameSpace 
Hostname space
Network Name space
Physical Address Space


Network namespaces (or netns): are a Linux networking primitive that provide isolation between network devices
ARP:
Route Table:
NIC Card>Interface>Kernel:
Payload:  When data is sent over the Internet, each unit transmitted includes both header information and the actual
	data being sent. The header identifies the source and destination of the packet, while the actual data is
 	referred to as the payload. Because header information, or overhead data, is only used in the transmission
 	process, it is stripped from the packet when it reaches its destination. Therefore, the payload is the only
 	data received by the destination system.
       
CIDR:
IP: Logical Address
tcpdump:
payload transport:

[root@dns1 ~]# tcpdump -i ens192

03:16:45.199343 IP 192.168.10.1.59659 > dns1.example.com.ssh: Flags [.], ack 8169489, win 4104, length 0
03:16:45.199348 IP dns1.example.com.ssh > 192.168.10.1.59659: Flags [P.], seq 8169297:8169489, ack 82640, win 1432, length 192
^C
51423 packets captured
51423 packets received by filter
0 packets dropped by kernel

NIC> Interface(eth0)> Socket Binding> Process

DNS Query: 

DIG(Domain Information Groper):

dig facebook.com 
nslookup goole.com

TTL(Time to live):

[root@dns1 ~]# nc -l 8090

[root@dns1 ~]# curl localhost:8090
[root@dns1 ~]# tcpdump -i lo
dropped privs to tcpdump
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on lo, link-type EN10MB (Ethernet), capture size 262144 bytes
02:18:58.636646 IP6 localhost.38674 > localhost.opsmessaging: Flags [F.], seq 34                                                                                                30938343, ack 72383242, win 342, options [nop,nop,TS val 1290663675 ecr 1290631922], length 0

[root@dns1 ~]# telnet localhost 8090
Trying ::1...
Connected to localhost.
Escape character is '^]'.
sujit

[root@dns1 ~]# tcpdump -i lo
02:26:08.015751 IP6 localhost.opsmessaging > localhost.38678: Flags [.], ack 17,                                                                                                                                                   win 342, options [nop,nop,TS val 1291093053 ecr 1291093053], length 0

For Specific Port:
---------------------------------------------
[root@dns1 ~]# tcpdump -i lo port 8090

Destination and port:
----------------------------------------------
[root@dns1 ~]# tcpdump -i ens192  dst facebook.com and port 443
02:34:03.174301 IP dns1.example.com.42674 > edge-star-mini-shv-01-sin6.facebook.                                                                                                                                                  com.https: Flags [S], seq 2968318325, win 29200, options [mss 1460,sackOK,TS val                                                                                                                                                   2906777749 ecr 0,nop,wscale 7], length 0
5 packets captured
9 packets received by filter
0 packets dropped by kernel

Ex:2[Check random port for every request, it is changing]
---------------------------------------------------------
[root@dns1 ~]# telnet google.com 8090

[root@dns1 ~]# tcpdump -i ens192  dst facebook.com and port 443
02:41:00.552012 IP dns1.example.com.51726 > 142.250.4.102.https: Flags [F.], seq                                                                                  																				 
02:41:03.778937 IP dns1.example.com.51728 > 142.250.4.102.https: Flags [S], seq                                                                                                                                                   700684565, win 29200, options [mss 1460,sackOK,TS val 1674793431 ecr 0,nop,wscal e 7], length 0

**Port:** A port number is a 16-bit unsigned integer, thus ranging from 0 to 65535. port number is always associated with an IP address 
		of a host and the type of transport protocol used for communication.
		
**NAT Gateway: **A NAT gateway uses ports 1024–65535. This is the limit actually 65536 connections for each Remote Host.

-------------------------------

**User Space** - It is set of locations where normal user processes run. These processes can't access kernal space directly. Some part of kernal space can be accessed 
			via system calls.These system calls acts as software interrupts in kernal space.

**Kernel Space -** kernal runs in the dedicated part of memory. Role of kernal space is to manage applications/ processes running in user space. It can access 
			all the memory. If a process perform a system call, a software interrupt is sent to kernal which then dispatches an appropriate interrupt handler.


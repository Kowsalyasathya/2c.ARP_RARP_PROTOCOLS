# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM FOR ARP:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
### Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
### Client:
![307230852-b58b8c77-a937-4957-8272-008fbb6ba8da](https://github.com/Kowsalyasathya/2c.ARP_RARP_PROTOCOLS/assets/118671457/4e7ecadc-8398-4abb-97f1-0fce75279c31)
### Server:
![307230858-9036605f-01af-4e34-8483-49126ae2bce2](https://github.com/Kowsalyasathya/2c.ARP_RARP_PROTOCOLS/assets/118671457/1096f6c8-74af-4e1a-998b-45f4f436ac0f)
## ALGORITHM FOR RARP:
### Client:
1.Start the programUsing datagram sockets UDP function is established.
2.Get the MAC address to be converted into IP address.
3.Send this MAC address to server.
4.Server returns the IP address to client.
### Server:
1.Start the program.
2.Server maintains the table in which IP and corresponding MAC addresses are stored.
3.Read the MAC address which is send by the client.
4.Map the IP address with its MAC address and return the IP address to client.
## PROGRAM - RARP
### Client:
```
import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())
```
### Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
    ip=input("Enter MAC Address : ") 
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
### Client:
![307232520-fbef2bb0-a6cc-463d-bb76-89f75f4a92ef](https://github.com/Kowsalyasathya/2c.ARP_RARP_PROTOCOLS/assets/118671457/33779c31-3041-4ce7-96be-80c5e783a180)
### Server:
![307232521-5f6a0540-a321-4d6c-a163-f6df66e44c69](https://github.com/Kowsalyasathya/2c.ARP_RARP_PROTOCOLS/assets/118671457/1df8ab13-db1a-482c-9829-5c224b153782)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.

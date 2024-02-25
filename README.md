# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
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
   
## PROGRAM - ARP
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
## OUPUT - ARP
![307267520-0df7780b-36a1-4a4f-a230-d0bbe1038992](https://github.com/suchitranath/2c.ARP_RARP_PROTOCOLS/assets/145742631/24ad466d-bcf5-49bf-b1ff-2d97f1ea07fe)

## PROGRAM - RARP
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT -RARP
![2nd](https://github.com/suchitranath/2c.ARP_RARP_PROTOCOLS/assets/145742631/587d3ceb-759e-4c24-a2e8-ab772ae1f204)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.

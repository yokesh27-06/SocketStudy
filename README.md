# Ex.No:1a  			Study of Socket Programming
## NAME: YOKESH H
## REG NO : 212224230312


## Aim: 
To write a python program to perform sliding window protocol
## ALGORITHM:
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
PROGRAM:

SERVER

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())

CLIENT

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 continue
 else:
 c.close()
 break

## OUTPUT:

## server.py

<img width="742" height="237" alt="Screenshot 2025-10-09 055155" src="https://github.com/user-attachments/assets/89a5772d-43bb-43f5-b87a-eb66b0f25391" />

## client.py

<img width="875" height="223" alt="Screenshot 2025-10-09 055143" src="https://github.com/user-attachments/assets/8b85d0ec-c753-4451-83c0-a6b4f162625c" />

 
## Result:
Thus the study of Socket Programming Completed Successfully

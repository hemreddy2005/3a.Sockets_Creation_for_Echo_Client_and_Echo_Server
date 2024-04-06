![Client](https://github.com/hemreddy2005/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/145633111/8a7afafc-163d-490a-b70f-4569414efb41)# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
CLIENT
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))
```
Server
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## OUPUT
![Client](https://github.com/hemreddy2005/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/145633111/48cc42b4-41ec-4a61-ae80-44aed73614e8)
![Server](https://github.com/hemreddy2005/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/145633111/3f84f0fa-076c-4837-9f7c-01147dfc27b7)
## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

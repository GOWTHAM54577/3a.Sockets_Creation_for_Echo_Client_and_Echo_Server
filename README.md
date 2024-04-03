# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
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
### SERVER

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

### CLIENT

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

## OUPUT
### SERVER
![WhatsApp Image 2024-04-03 at 11 02 49_74e0ec33](https://github.com/GOWTHAM54577/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/144589420/14c7605e-9797-4c6c-bed3-b4e72733963e)

### CLIENT
![WhatsApp Image 2024-04-03 at 11 02 50_1693ebd5](https://github.com/GOWTHAM54577/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/144589420/0abbf272-78b9-4747-a4d1-1fa678010cf7)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

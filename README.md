# -Ex.-3a-Echo-Client-and-Server-using-TCP-Sockets
## Developed by : LATHIKA .K
## Reg no : 212224230140

## AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM

## server:

import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as server_socket:
    server_socket.bind((HOST, PORT))
    server_socket.listen()

    print(f"Server is listening on {HOST}:{PORT}")
    while True:
        conn, addr = server_socket.accept()
        with conn:
            print(f"Connected by {addr}")
            while True:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)
                print(f"Echoed: {data.decode('utf-8')}")


## client:


import socket

HOST = '127.0.0.1'  
PORT = 65432  

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client_socket:
    client_socket.connect((HOST, PORT))

    message = 'Hello, Server!'
    client_socket.sendall(message.encode('utf-8'))

    data = client_socket.recv(1024)
    print(f"Received echo: {data.decode('utf-8')}")

    
## OUPUT

## server:

![image](https://github.com/user-attachments/assets/40edee19-2821-46cd-9e7b-dee2ace5bbfb)

## client:

![image-1](https://github.com/user-attachments/assets/9be41b43-8b7c-4f41-b7fa-b4443a75526b)


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

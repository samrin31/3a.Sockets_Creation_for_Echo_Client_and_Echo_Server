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
echo_server.py

import socket

# Create socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind IP address and port
server_socket.bind(("localhost", 5000))

# Listen for client connection
server_socket.listen(1)

print("Server is waiting for connection...")

# Accept connection
conn, addr = server_socket.accept()

print("Connected by:", addr)

# Receive message from client
message = conn.recv(1024).decode()

print("Message from client:", message)

# Send echo message back to client
conn.send(message.encode())

 echo_client.py

import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to server
client_socket.connect(("localhost", 5000))

# Input message
msg = input("Enter message: ")

# Send message to server
client_socket.send(msg.encode())

# Receive echo message
echo_msg = client_socket.recv(1024).decode()

print("Echo from server:", echo_msg)

# Close socket
client_socket.close()

# Close connection
conn.close()
server_socket.close()
## OUPUT
<img width="1900" height="185" alt="Screenshot 2026-05-20 101656" src="https://github.com/user-attachments/assets/1bb75188-290c-4dc8-9177-0795b46fbbed" />
<img width="1862" height="337" alt="Screenshot 2026-05-20 101709" src="https://github.com/user-attachments/assets/b2032da9-fb16-43f3-b725-2441bdecb345" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
## NAME: Ritika S
## REGNO:212225220086
# AIM:
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM:
echo_server.py
```
import socket
# Create socket
server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# Bind IP address and port
server.bind(('localhost', 5000))
# Start listening
server.listen(1)
print("Server is waiting for connection...")
# Accept client connection
conn, addr = server.accept()
print("Connected by:", addr)
while True:
    # Receive data from client
    data = conn.recv(1024).decode()
    if not data:
        break
    print("Client:", data)
    # Send same data back to client
    conn.send(data.encode())
# Close connection
conn.close()
server.close()
```
echo_client.py
```
# echo_client.py
import socket
# Create socket
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
# Connect to server
client.connect(('localhost', 5000))
while True:
    # Input message
    msg = input("Enter message: ")
    # Send message to server
    client.send(msg.encode())
    # Receive echoed message
    data = client.recv(1024).decode()
    print("Server replied:", data)
    if msg.lower() == "exit":
        break
# Close connection
client.close()
```
## OUPUT:
# echo_server.py
<img width="473" height="307" alt="Screenshot 2026-05-19 083611" src="https://github.com/user-attachments/assets/4f252b17-00e8-4b34-84ff-057708be2796" />
# echo_client.py
<img width="465" height="311" alt="Screenshot 2026-05-19 083623" src="https://github.com/user-attachments/assets/e2c72416-01f7-4b6a-b949-340828606fd7" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.

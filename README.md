# 2a_Stop_and_Wait_Protocol
##Name:Nivetha N
##Ref.no:212225040290
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
server
~~~
import socket

s = socket.socket()
s.bind(('localhost',8000))
s.listen(1)

print("Server is listening...")

conn, addr = s.accept()
print("Connected with", addr)

while True:
    data = conn.recv(1024).decode()
    print("Client:", data)

    conn.send("Acknowledgement Received".encode())

    if data.lower() == "exit":
        break

conn.close()
client
import socket

s = socket.socket()
s.connect(('localhost',8000))

while True:
    msg = input("Enter message: ")
    s.send(msg.encode())

    print("Server:", s.recv(1024).decode())

    if msg.lower() == "exit":
        break

s.close()

~~~
## OUTPUT
server
<img width="620" height="197" alt="Screenshot 2026-03-10 163317" src="https://github.com/user-attachments/assets/9b06fa92-63d0-4a6d-98dd-d22d41c9014b" />
client

<img width="637" height="223" alt="Screenshot 2026-03-10 163342" src="https://github.com/user-attachments/assets/f8056695-9a27-4f5d-8470-20b3869004d1" />



## RESULT

 python program to perform stop and wait protocol was successfully executed.

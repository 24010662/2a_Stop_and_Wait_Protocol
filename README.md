# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol

name : vutukuri sai kumar Reddy

ref no:212224230307
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
### Client:
```import socket
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
```
### server:

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT:
### Client:
![image](https://github.com/user-attachments/assets/dcc7a2e8-a644-4c63-9d17-34e81d1d0e62)


### Server:
![image](https://github.com/user-attachments/assets/5358afab-6ea1-4c0a-ae46-5b749e4e0e16)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

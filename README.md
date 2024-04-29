# 2a_Stop_and_Wait_Protocol
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
client
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()

while True:
    i = input("Enter a data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    
    if ack:
        print(ack)
    else:
        c.close()
        break


```

sever
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgment Received".encode())
```
## OUTPUT
## client
![Screenshot 2024-04-29 143707](https://github.com/prasanna2006I/2a_Stop_and_Wait_Protocol/assets/150161282/ca1a6e43-453d-4af6-af1b-cda7961648f9)

## server
![Screenshot 2024-04-29 143714](https://github.com/prasanna2006I/2a_Stop_and_Wait_Protocol/assets/150161282/d0be11a1-5343-465c-b384-734438f34a5f)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

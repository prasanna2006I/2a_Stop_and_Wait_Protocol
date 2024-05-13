# 2a_Stop_and_Wait_Protocol
# NAME:PRASANNA I
# REG NO:212223220079
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
![image](https://github.com/prasanna2006I/2a_Stop_and_Wait_Protocol/assets/150161282/314052e1-5cf0-4991-884d-9791aa848811)


## server


![image](https://github.com/prasanna2006I/2a_Stop_and_Wait_Protocol/assets/150161282/830232b6-6864-4253-998a-0f45ae8dd2d6)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

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

## CLIENT
```
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
```
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## CLIENT
![309804126-f371374b-fc43-431a-887d-4b3cf8dab819](https://github.com/Aswinth21/2a_Stop_and_Wait_Protocol/assets/120236638/0d8ba450-c728-4347-962e-75a7663d005d)
## SERVER:
![309804307-01a44022-ecf6-446e-8a2c-f92f12d87249](https://github.com/Aswinth21/2a_Stop_and_Wait_Protocol/assets/120236638/d7b05994-a6e3-4ad1-bc55-3b00a397bb78)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

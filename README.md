# 2a_Stop_and_Wait_Protocol

### Name: VISHAL M.A
### Reg.NO: 212222230177
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
### CLIENT
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
### SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### CLIENT
![client 1 out](https://github.com/vishal21004/2a_Stop_and_Wait_Protocol/assets/119560110/7fc98006-38bd-48d1-a418-9320456ca1dc)


### SERVER
![server out](https://github.com/vishal21004/2a_Stop_and_Wait_Protocol/assets/119560110/68c9d1fe-d82c-4669-8e1b-57a6e0ce9eb3)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

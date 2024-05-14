# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### Register no: 212222100024
### Name: LOKESH RAHUL V V
## AIM:
To implent the program for the implementationof sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### server:
```python
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
### client:
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### server
![Screenshot 2024-05-14 140149](https://github.com/lokeshrahulv/2b_SLIDING_WINDOW_PROTOCOL/assets/118423842/3bc4f405-fe6c-42b6-b01b-edd4fb1aa0e1)

### client
![Screenshot 2024-05-14 140219](https://github.com/lokeshrahulv/2b_SLIDING_WINDOW_PROTOCOL/assets/118423842/98a86ebf-a6ce-4aa3-a615-b9121cfbb376)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed

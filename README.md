# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
Developed by:G.Mithik jain
Reg no:212224240087
```

## Client:
```
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


## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

```
## OUTPUT
## Client:
<img width="840" height="228" alt="image" src="https://github.com/user-attachments/assets/711b1e8b-6a2f-4c99-81bb-7a77f8460c67" />

## Server:
<img width="825" height="183" alt="image" src="https://github.com/user-attachments/assets/25fc59a6-9ae1-4190-98ab-3667734b5dca" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed

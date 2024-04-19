# 2a_Stop_and_Wait_Protocol

Name: Alan Samuel Vedanayagam
Reg. no: 212223040012

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

Client:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter Data : ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

Server:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgemet recieved".encode())


## OUTPUT
![image](https://github.com/Alan-samuel/2a_Stop_and_Wait_Protocol/assets/147091803/be66e37f-b320-41c1-9269-cc600d99375d)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

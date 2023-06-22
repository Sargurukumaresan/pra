https://github.com/balar2004/19CS406-EX-1
https://github.com/balar2004/19CS406-EX-2
https://github.com/balar2004/19CS406-EX-3
https://github.com/balar2004/19CN406-EX-4
https://github.com/balar2004/19CN406-EX-5
https://github.com/balar2004/19CS406-EX-6
https://github.com/balar2004/19CN406-EX-7
https://github.com/balar2004/19CN406-EX-8
https://github.com/balar2004/19CN406-EX-9
https://github.com/balar2004/19CN406-EX-10

# Newton-Raphson method

Question:
Find a positive real root of 𝒙𝟑 − 𝒙 − 𝟐 = 𝟎 using Newton-Raphson method.
##Program:
```
def f(x):
return x**3-x-2
def f1(x):
return 3*x**2-1
xo=float (input ("Enter the initial approximation: "))
for i in range (1,10):
xn=xo-f(xo)/f1(xo)
xo=xn
print ("The approximate root using Newton-Raphson method is %.4f"%xn)
```


# Gauss-Seidel method
Question:
Solve the system of equations 𝟒𝒙 + 𝒚 + 𝒛 = 𝟏; 𝒙 + 𝟑𝒚 + 𝒛 = 𝟐; 𝒙 + 𝒚 + 𝟓𝒛 = 𝟑, using
Gauss-Seidel method.
##Program:
```
x0=0; y0=0; z0=0
for i in range (1,10):
x=1/4*(1-y0-z0)
x0=x
y=1/3*(2-x0-z0)
y0=y
z=1/5*(3-x0-y0)
z0=z
print ("The approximate solution of x = %.4f, y= %.4f, z=%.4f"%(x, y,z))
```



# Lagrange’s Interpolation method
Question:
Using Lagrange interpolation formula, find the value corresponding to 𝒙 = 𝟏𝟎 from the
following table
##Program:
```
x= [0,1,2,4,5,6]
y= [1,14,15,5,6,19]
s=float (input ("Enter the value of x to be in: "))
sum=0
for i in range (0,6):
prod=1
 for j in range (0,6):
 if i!=j:
prod=prod*(s-x[j])/(x[i]-x[j])
 sum=sum+prod*y[i]
print ("The functional value is %.4f"%sum)
```


# Trapezoidal rule
Question:
Evaluate ∫
𝟏
𝒅𝒙 using trapezoidal rule with 𝒉 = 𝟎. 𝟐.
##Program:
```
def f(x):
return 1/(1+x**2)
a=float (input ("Enter the lower limit: "))
b=float (input ("Enter the upper limit: "))
h=float (input ("Enter the step size: "))
n=int((b-a)/h)
sum=0
for i in range (1, n):
sum=sum+f(a+i*h)
trap=h/2*(f(a)+f(b)+2*sum)
print ("The Integral value is %.5f"%trap)
```


# Runge-Kutta method of fourth order
Question:
Find 𝒚(𝟎. 𝟐), given that 𝒅𝒚 = 𝒙 + 𝒚𝟐, 𝒚(𝟎) = 𝟏 using Runge-Kutta fourth order method.
##Program:
```
def f (x, y):
return x+y**2
x0=float (input ("Enter initial point of x: "))
y0=float (input ("Enter initial point of y: "))
h=float (input ("Enter step value h: "))
k1=h*f (x0, y0)
k2=h*f (x0+h/2,y0+k1/2)
k3=h*f (x0+h/2,y0+k2/2)
k4=h*f (x0+h,y0+k3)
y=y0+(k1+2*k2+2*k3+k4)/6
print ("The value of y using RK method is %.4f"%y)
```

# Adam’s predictor and corrector method
Question:
Evaluate (𝟏. 𝟒) , given that 𝒅𝒚 = 𝒙𝟐(𝟏 + 𝒚), 𝒚(𝟏) = 𝟏, 𝒚(𝟏. 𝟏) = 𝟏. 𝟐𝟑𝟑, 𝒚(𝟏. 𝟐) = 𝟏. 𝟓𝟒𝟖
𝒅𝒙
and 𝒚(𝟏. 𝟑) = 𝟏. 𝟗𝟕𝟗 using Adam’s predictor and corrector method.
##Program:
```
def f (x, y):
return x**2*(1+y)
x0=float (input ("Enter x0: "))
y0=float (input ("Enter y0: "))
x1=float (input ("Enter x1: "))
y1=float (input ("Enter y1: "))
x2=float (input ("Enter x2: "))
y2=float (input ("Enter y2: "))
x3=float (input ("Enter x3: "))
y3=float (input ("Enter y3: "))
h =0.1
y4p=y3+(h/24) *(55*f(x3,y3)-59*f(x2,y2)+37*f(x1,y1)-9*f(x0,y0))
x4=x3+h
y4c=y3+(h/24) *(9*f(x4,y4p) +19*f(x3,y3)-5*f(x2,y2)+f(x1,y1))
print ("Approximate soln is %0.4f"%y4c)
```

# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL
~~~
DATE : 09-03-2023
~~~
### AIM :
To implement socket programming date and time display from client to server using TCPSockets.
### ALGORITHM :
#### Server:
```
1.Create a server socket and bind it to port.
2.Listen for new connection and when a connection arrives, accept it.
3.Send server‟s date and time to the client.
4.Read client‟s IP address sent by the client.
5.Display the client details.
6.Repeat steps 2-5 until the server is terminated.
7.Close all streams.
8.Close the server socket.
9.Stop.
```
#### Client:
```
1.Create a client socket and connect it to the server‟s port number.
2.Retrieve its own IP address using built-in function.
3.Send its address to the server.
4.Display the date & time sent by the server.
5.Close the input and output streams.
6.Close the client socket.
7.Stop.
```
### PROGRAM :
#### Client:
```
Developed By: SARGURU K
Reg No: 21222230134
```
```
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
    print(ack)
    c.close()
```
#### Server:
```
Developed By: SARGURU K
Reg No: 21222230134
```
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
### OUTPUT:
#### Client:
![E1](https://github.com/Pavan-Gv/19CS406-EX-1/assets/94827772/8d8eb110-1497-475f-beec-86c17530d95e)
#### Server:
![E2](https://github.com/Pavan-Gv/19CS406-EX-1/assets/94827772/63d1233f-326e-4313-956e-ee08d098658d)
### RESULT:
Thus, the program to implement socket programming date and time display from client to server using TCP Sockets was successfully executed.



# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL
```
DATE: 16-03-2023
```
### AIM :
To write a python program to perform stop and wait protocol.

### ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK 
   signal to client.
6. Stop the program
```

### PROGRAM :
```
Developed By:SARGURU K
Reg. No.: 212222230134
```
#### Client:
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
#### Server:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
~~~
### OUTPUT :
#### Client Side:
![image](https://github.com/Pavan-Gv/EX-2/assets/94827772/110f94e7-88ba-4975-8a1f-bea44b922ea2)
#### Server Side:
![image](https://github.com/Pavan-Gv/EX-2/assets/94827772/550ea1fe-fbc6-4b22-a4d6-4ad13e97d529)
### RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.



# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
```
DATE : 23-03-2023
```
### AIM :
To write a python program to perform sliding window protocol.
### ALGORITHM :
```
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will 
  send NACKsignal to client.
6.Stop the program
```
### PROGRAM :
```
Developed by: SARGURU K
Reg. No: 212222230134
```
#### Client Side:
```
import socket
s=socket.socket()
s.bind(('localhost',8080))
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
#### Server Side:
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
### OUTPUT :
#### Client Side:
![image](https://github.com/Pavan-Gv/EX-3/assets/94827772/d19669fc-ae54-480a-8d17-194dabd529e8)


#### Server Side:
![image](https://github.com/Pavan-Gv/EX-3/assets/94827772/80a65f3e-021b-44d4-af2e-a6ddbfebc3ed)

### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.


# EX-4 IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL (ARP)
```
DATE : 30-03-2023
```
### AIM :
To write a python program for simulating ARP protocols using TCP

### ALGORITHM :
#### Client Side:
```
1.Start the program
2.Using socket connection is established between client and server.
3.Get the IP address to be converted into MAC address.
4.Send this IP address to server.
5.Server returns the MAC address to client.
```
#### Server Side:
```
1.Start the program
2.Accept the socket which is created by the client.
3.Server maintains the table in which IP and corresponding MAC addresses are stored.
4.Read the IP address which is send by the client.
5.Map the IP address with its MAC address and return the MAC address to client.
```
### PROGRAM :
```
Developed By: SARGURU K
Reg. No.: 212222230134
```
#### Client Side:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
#### Server Side:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
### OUTPUT :
#### Client Side:
![image](https://github.com/Pavan-Gv/EX-4/assets/94827772/090a75b0-4ceb-4111-817d-c7f7c3ecf237)
#### Server Side:
![image](https://github.com/Pavan-Gv/EX-4/assets/94827772/a5cc2a0d-c1b1-4123-b90f-5bee7000a4e9)
### RESULT :
Thus, the python program for simulating ARP protocols using TCP was successfully executed.




# EX-5 IMPLEMENTATION OF REVERSE ADDRESS RESOLUTION PROTOCOL(RARP)
```
DATE : 06-04-2023
```
### AIM :
To write a python program for simulating RARP protocols using UDP.
### ALGORITHM :
#### Client Side:
```
1.Start the program
2.Using datagram sockets UDP function is established.
3.Get the MAC address to be converted into IP address.
4.Send this MAC address to server.
5.Server returns the IP address to client.
```
#### Server Side:
```
1.Start the program.
2.Server maintains the table in which IP and corresponding MAC addresses are stored.
3.Read the MAC address which is send by the client.
4.Map the IP address with its MAC address and return the IP address to client.
```
### PROGRAM :
```
Developed By:SARGURU K
Reg. No.: 212222230134
```
#### Client Side:
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
#### Server Side:
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
    ip=input("Enter MAC Address : ")
    s.send(ip.encode())
    print("Logical Address",s.recv(1024).decode())
```
### OUTPUT :
#### Client Side:
![image](https://github.com/Pavan-Gv/EX-5/assets/94827772/50bbbf75-fbb7-4eab-a625-458a64beffe2)
#### Server Side:
![image](https://github.com/Pavan-Gv/EX-5/assets/94827772/95bd1a73-46ca-41cf-ac18-1042717f7f6d)
### RESULT :
Thus, python program for simulating RARP protocols using UDP was successfully executed.



# EX-6 IMPLEMENTATION OF PING COMMAND
```
DATE : 13-04-2023
```
### AIM :
To write the python program for simulating ping command.
### ALGORITHM :
```
1. Start the program.
2. Include necessary package in java.
3. To create a process object p to implement the ping command.
4. Declare one Buffered Reader stream class object.
5. Get the details of the server
6. Length of the IP address.
7. Time required to get the details.
8. Send packets, receive packets and lost packets.
9. Minimum, maximum and average times.
10. Print the results.
11. Stop the program.
```
### PROGRAM :
```
Developed : SARGURU K
Reg.No. : 212222230134
```
#### Client Side:
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
#### Server Side:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
### OUTPUT :
#### Client Side:
![image](https://github.com/Pavan-Gv/EX-6/assets/94827772/4c043989-1ce8-4a79-a6b0-5b3d7b260c58)
#### Server Side:
![image](https://github.com/Pavan-Gv/EX-6/assets/94827772/10f5575f-6ecc-41e6-a9c9-e5a17e5ebee4)
### RESULT :
Thus, the python program for simulating ping command was successfully executed.


# EX-7 IMPLEMENTATION OF TRACEROUTE COMMAND
```
DATE : 20-04-2023
```
### AIM :
To write the python program for simulating Traceroute command.
### ALGORITHM :
```
1.Start the program.
2.Get the frame size from the user.
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server, it will send ACK signal to client otherwise it will 
  sendNACK signal to client.
6.Stop the program
```
### PROGRAM :
```
Developed by : SARGURU K
Register Number : 212222230134
```
from scapy.all import*
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)
```
### OUTPUT :
![image](https://github.com/Pavan-Gv/EX-7/assets/94827772/a1ac91f5-3f58-4160-844e-737ca0a10d92)
### RESULT :
Thus, the python program for simulating Traceroute command was successfully executed.



# EX-8 APPLICATION USING TCP SOCKETS - CREATING ECHO CLIENT-SERVER
```
DATE : 27-04-2023
```
### AIM :
To write a python program for creating Echo Client and Echo Server using TCP Sockets Links.
### ALGORITHM :
```
1.Import the necessary modules in python
2.Create a socket connection to using the socket module.
3.Send message to the client and receive the message from the client using the 
  Socket module in server.
4.Send and receive the message using the send function in socket.
```
### PROGRAM :
```
Developed by: SARGURU K
Register No: 212222230134
```
#### Client_Side:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    msg=input("Client > ")
    s.send(msg.encode())
    print("Server > ",s.recv(1024).decode())
```
#### Server_Side:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    ClientMessage=c.recv(1024).decode()
    c.send(ClientMessage.encode())
```
### OUTPUT :
#### Client_Side:
![image](https://github.com/Pavan-Gv/EX-8/assets/94827772/10472420-5845-4185-8f77-c9d7f20826ef)


#### Server_Side:
![image](https://github.com/Pavan-Gv/EX-8/assets/94827772/3b7ee27d-c191-43c4-8fd8-30f135c88c06)
### RESULT :
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.


# EX-9 APPLICATION USING TCP SOCKETS - CREATING FOR CHAT CLIENT-SERVER
```
DATE : 04-05-2023
```
### AIM :
To write a python program for creating Chat using TCP Sockets Links.

### ALGORITHM :
```
1.Import the necessary modules in python
2.Create a socket connection to using the socket module.
3.Send message to the client and receive the message from the client using the Socket module in server
4.Send and receive the message using the send function in socket.
```
### PROGRAM :
```
Developed By: SARGURU K
Reg. No: 212222230134
```
#### Clent_Side:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    msg=input("Client > ")
    s.send(msg.encode())
    print("Server > ",s.recv(1024).decode())
```
#### Server_side:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    ClientMessage=c.recv(1024).decode()
    print("Client > ",ClientMessage)
    msg=input("Server > ")
    c.send(msg.encode())
```
### OUTPUT :
#### Clent_Side:
![image](https://github.com/Pavan-Gv/EX-9/assets/94827772/c7e54cb6-b938-42ce-b78a-a139979125e6)
#### Server_side:
![image](https://github.com/Pavan-Gv/EX-9/assets/94827772/cd9cf58c-7e0a-4419-b7ef-4cba7515c806)
### RESULT :
Thus, the python program for creating Chat using TCP Sockets Links was successfully created and executed.





# EX-10 APPLICATION USING TCP SOCKETS - FILE TRANSFER PROGRAM
```
DATE : 11-05-2023
```
### AIM :
To write a python program for creating File Transfer using TCP Sockets Links.
### ALGORITHM :
```
1.Start the program.
2.Get the frame size from the user.
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server, it will send ACK signal to client otherwise 
  it will sendNACK signal to client.
6.Stop the program
```
### PROGRAM :
```
Developed By : SARGURU K
Register Number : 212222230134
```
#### Client_Side:
```
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello server!".encode())
with open('received_file', 'wb') as f:
    while True:
        print('receiving data...')
        data = s.recv(1024)
        print('data=%s', (data))
        if not data:
            break
        f.write(data)
f.close()
print('Successfully get the file')
s.close()
print('connection closed')

```

#### Server_Side:
```
import socket
port = 60000
s = socket.socket()
host = socket.gethostname()
s.bind((host, port))
s.listen(5)
while True:
    conn, addr = s.accept()
    data = conn.recv(1024)
    print('Server received', repr(data))
    filename='mytext.txt'
    f = open(filename,'rb')
    l = f.read(1024)
    while (l):
        conn.send(l)
        print('Sent ',repr(l))
        l = f.read(1024)
    f.close()
    print('Done sending')
    conn.send('Thank you for connecting'.encode())
    conn.close()
```
### OUTPUT :
#### Client_Side:
![image](https://github.com/Pavan-Gv/EX-10/assets/94827772/efdea677-4097-440a-86c8-a135d5136388)
#### Server_Side:
![image](https://github.com/Pavan-Gv/EX-10/assets/94827772/7aae54ab-5fa5-4c2b-bb55-c0343b0ab6b1)
### RESULT :
Thus, the python program for creating File Transfer using TCP Sockets Links was successfully created and executed.



# Ex. No. 1.-SIMULATION ANALYSIS ON FOUR BAR CHAIN MECHANISM

## DATE: 

## AIM:

###   To determine & simulate the displacement & velocity analysis for the given four bar chain mechanism. 

###   In a four bar chain ABCD, AD is fixed and is 120 mm long. The crank AB is 30 mm long and rotates at 100 rpm clockwise, while the link CD = 60mm oscillates about D. BC and AD are of equal lengths. ∟BAD = 600.

![image](https://github.com/Sellakumar1987/Ex.-No.-1.-SIMULATION-ANALYSIS-ON-FOUR-BAR-CHAIN-MECHANISM/assets/113594316/03952954-387e-4fd3-a1a0-a8dd4b82ae07)

## REQUIREMENTS:
###  ●	Mech Analyzer software.
###  ●	Processor: Minimum 1.5 GHz
###  ●	RAM: Minimum 512 MB
###  ●	Operating System: Windows XP, Windows Vista, Windows 7, Windows 8 or higher.
###  ●	Dependencies: Microsoft .Net 2.0 framework
###  ●	Mini Drafter.
###  ●	Geometry instruments.

## PROCEDURE:
###   1. Draw a horizontal line AD of length 120 mm. 
###   2. At A, Draw a line AB of length 30 mm at an angle of 600 
###   3. With B as centre, BC = AD = 120mm draw an arc 
###   4. With D as centre, CD = 60 mm draw another arc 
###   5. Join BC and DC 

![image](https://github.com/Sellakumar1987/Ex.-No.-1.-SIMULATION-ANALYSIS-ON-FOUR-BAR-CHAIN-MECHANISM/assets/113594316/a99fb530-e8df-49bf-9b2c-d537ff992534)

###   This value of VBA is used to decide the scale for the velocity diagram 
###   Let us construct the velocity diagram taking a scale: 
###   0.3141 m/s = 60 mm (say) 
###   1. The fixed link AD, appears as a point in the velocity diagram 
###   2. From a, draw ab = 60mm, perpendicular to AB in configuration diagram and in the direction of velocity (downward direction) 
###   3. From b, draw vector bc perpendicular to BC
###   4. From (a,d), draw vector cd perpendicular to CD. This will intersect the previous vector at c.  

![image](https://github.com/Sellakumar1987/Ex.-No.-1.-SIMULATION-ANALYSIS-ON-FOUR-BAR-CHAIN-MECHANISM/assets/113594316/76094ae8-a8af-48f3-b2c4-472ab800cc8e)

![image](https://github.com/Sellakumar1987/Ex.-No.-1.-SIMULATION-ANALYSIS-ON-FOUR-BAR-CHAIN-MECHANISM/assets/113594316/cb44fabe-6e16-4550-a2ec-4ee0f4cb6774)

###   1. First measure cd from velocity diagram  
###   2. Now, Calculate VCd using the scale of the diagram 
###   3. Finally, calculate ωcd from the relation v = rω 
###   Thus, link CD revolves with ωcd = 4 rad/s (clockwise about D) 





## Output:
![Screenshot 2023-06-13 181523](https://github.com/BaskaranV15/Ex.-No.-1.-SIMULATION-ANALYSIS-ON-FOUR-BAR-CHAIN-MECHANISM/assets/118703522/9560186c-96ca-4b41-9e36-4f538edcd6bf)
![Screenshot 2023-06-13 181453](https://github.com/BaskaranV15/Ex.-No.-1.-SIMULATION-ANALYSIS-ON-FOUR-BAR-CHAIN-MECHANISM/assets/118703522/78c713c9-ba2b-4b33-abb8-27747694faa9)


#### Name:SARGURU K
#### Register Number: 212222230134

## RESULT:
Thus the displacement & velocity analysis for the given four bar chain mechanism is simulated.



# Ex. No.2 - SIMULATION ANALYSIS ON SLIDER CRANK MECHANISM

## DATE: 

## AIM:
###   To determine & simulate the displacement & velocity analysis for the given slider crank mechanism. 
###   An engine mechanism is shown. The Crank CB = 200mm and the connecting rod BA = 600mm. In the position shown, the crankshaft has a speed of 50 rad/s and an angular acceleration of 800 rad/s2


## REQUIREMENTS:
###   ●	Mech Analyzer software.
###   ●	Processor: Minimum 1.5 GHz
###   ●	RAM: Minimum 512 MB
###   ●	Operating System: Windows XP, Windows Vista, Windows 7, Windows 8 or higher.
###   ●	Dependencies: Microsoft .Net 2.0 framework
###   ●	Mini Drafter.
###   ●	Geometry instruments.

## PROCEDURE:
###  Configuration diagram
###  Assume scale 1:10
###  1. Draw a horizontal line and locate C 
###  2. At C, draw CB of length 20 mm inclined at 1200 
###  3. With B as centre, BA 60mm, draw an arc to cut the horizontal at A. Join BA to complete the configuration diagram 

![image](https://github.com/Sellakumar1987/Ex.-No.2---SIMULATION-ANALYSIS-ON-SLIDER-CRANK-MECHANISM/assets/113594316/0e905314-0fc5-4e13-a513-67c95aced702)

![image](https://github.com/Sellakumar1987/Ex.-No.2---SIMULATION-ANALYSIS-ON-SLIDER-CRANK-MECHANISM/assets/113594316/590ca17d-5a31-427c-816d-975478542bcd)


## Velocity diagram
###  Scale: 10 m/s = 100 mm (say) 
###  1. The fixed point C appears as a stationary point in the velocity diagram 
###  2. Draw the vector bc of length 100 mm, perpendicular to the crank CB from the configuration diagram 
###  3. At b, draw a projection line perpendicular to AB from the configuration diagram 
###  4. Draw a horizontal at c, meeting the projection from b at a. join ca to complete the velocity diagram.


## Output
![Screenshot 2023-06-14 181054](https://github.com/BaskaranV15/Ex.-No.2---SIMULATION-ANALYSIS-ON-SLIDER-CRANK-MECHANISM/assets/118703522/e15f154f-9f55-4c01-993f-b0aa1fd8d1e3)

![Screenshot 2023-06-14 181633](https://github.com/BaskaranV15/Ex.-No.2---SIMULATION-ANALYSIS-ON-SLIDER-CRANK-MECHANISM/assets/118703522/f96e2667-3cd9-46e4-8190-44d393eb57f8)


### Name:SARGURU K
### Register Number: 212222230134

## RESULT:
### Thus the displacement & velocity analysis for the given four bar chain mechanism is simulated.


# Ex. No.3 - SIMULATION-OF-CARTESIAN-3D-PRINTER-MACHINE
#### Date: 18-05-2023
## AIM:
### To simulate the construction of cartesian 3D printer and to get in-depth knowledge of mechatronics of cartesian 3D printers.

![image](https://github.com/Sellakumar1987/Ex.-No.-3---SIMULATION-OF-CARTESIAN-3D-PRINTER-MACHINE/assets/113594316/69572917-1257-45d7-bf57-ff48a6e5a711)

## REQUIREMENTS:
### ●	System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:
### For X-Axis Assembly
###   1.	Select X-Axis Assembly from the visible list.
###   2.	All the parts related to X-Axis will be shown on the screen.
###   3.	Select the parts in sequence in which they are shown.
###   4.	When the first part is selected then it will open in the blank space in the left side of the screen.
###   5.	Further, when the correct part will be selected then it will get assembled with the previously selected part/parts.
###   6.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## For Y-Axis Assembly
###   1.	Select Y-Axis Assembly from the visible list.
###   2.	All the parts related to Y-Axis will be shown on the screen.
###   3.	Select the parts in sequence in which they are shown.
###   4.	When the first part is selected then it will open in the blank space in the left side of the screen.
###   5.	Further, when the correct part will be selected then it will get assembled with the previously selected part/parts.
###   6.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## For Z-Axis Assembly
###   1.	Select Z-Axis Assembly from the visible list.
###   2.	All the parts related to Z-Axis will be shown on the screen.
###   3.	Select the parts in sequence in which they are shown.
###   4.	When the first part is selected then it will open in the blank space in the left side of the screen.
###   5.	Further, when the correct part will be selected then it will get assembled with the previously selected part/parts.
###   6.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## For Complete-Axis Assembly
###   1.	Select Complete-Axis Assembly from the visible list.
###   2.	All the parts related to Complete-Axis will be shown on the screen.
###   3.	Select the parts in sequence in which they are shown.
###   4.	When the first part is selected then it will open in the blank space in the left side of the screen.
###   5.	Further, when the correct part will be selected then it will get assembled with the previously selected part/parts.
###   6.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## Playing with Axes
###   1.	Move the x-axis slider or enter the value (within the given range) in the given text box and press/select ENTER. Now observe the movement of the x-axis assembly.
###   2.	Move the y-axis slider or enter the value (within the given range) in the given text box and press/select ENTER. Now observe the movement of the y-axis assembly.
###   3.	Move the z-axis slider or enter the value (within the given range) in the given text box and press/select ENTER. Now observe the movement of the z-axis assembly.

## Cartesian 3D printing:-

### X-axis assembly:-



![xaxis](https://github.com/A-Thiyagarajan/Ex.-No.-3---SIMULATION-OF-CARTESIAN-3D-PRINTER-MACHINE/assets/118707693/843f8aba-dd50-42e2-a76f-095a6ccbc126)

#### Smooth Rod: 
In Cartesian 3D printing, a smooth rod refers to a cylindrical rod with a smooth and polished surface. It is typically made of hardened steel or aluminum. Smooth rods are used as linear motion guides within the printer's framework. They provide a smooth and low-friction surface for components such as the print head or extruder to move along a specific axis, such as the X, Y, or Z-axis.

#### Bearing: 
A bearing is a component used to reduce friction between moving parts and facilitate smooth motion. In Cartesian 3D printing, linear bearings are commonly used. These bearings allow the smooth rod or shaft to slide or roll along the bearing surface, reducing friction and enabling precise movement. Linear bearings ensure stable and accurate motion of the print head or other moving components within the printer.

#### Idler: 
An idler, in the context of Cartesian 3D printing, is a component that helps guide and control the movement of a flexible belt or filament. It is often used in belt-driven systems, such as those used for the movement of the print head or bed. The idler typically features a smooth surface and a bearing, providing a point of contact for the belt or filament to change direction while minimizing friction.

#### Extruder: 
The extruder is a key component in a 3D printer responsible for feeding filament material, typically plastic, into the hot end or nozzle. It consists of a motor, a filament drive mechanism (such as a gear or wheel), and a heating element. The motor drives the filament forward, pushing it into the hot end where it is melted and deposited layer by layer to create the 3D printed object.

#### Motor: 
In Cartesian 3D printing, motors are used to drive the movement of various components. Stepper motors are commonly employed due to their precise control and ability to move in discrete steps. These motors are typically used to control the motion of the print head along the X, Y, and Z axes, as well as other movements such as filament feeding or bed leveling. The motors receive commands from the printer's controller to move the components accurately and achieve the desired 3D printed output.
### Y-axis assembly:-



![yaxis](https://github.com/A-Thiyagarajan/Ex.-No.-3---SIMULATION-OF-CARTESIAN-3D-PRINTER-MACHINE/assets/118707693/aab1eb47-bb94-47b8-92c1-ed9ed23576f4)

#### Y-Axis Supporter: 
The Y-axis supporter refers to a structural component in a Cartesian 3D printer that provides support and stability to the Y-axis assembly. It is typically a rigid frame or structure that holds the components of the Y-axis, such as the smooth rods, bearings, and the print bed.

#### Horizontal and Vertical Threaded Rod: 
In Cartesian 3D printing, horizontal and vertical threaded rods are used to provide linear motion and adjustment in the Y-axis direction. The horizontal threaded rod is oriented parallel to the Y-axis and is responsible for controlling the movement of the print bed. The vertical threaded rod is positioned perpendicular to the Y-axis and allows for fine-tuning the height of the print bed.

#### Smooth Rod:
A smooth rod, as mentioned earlier, is a cylindrical bar with a smooth and polished surface. In the context of Cartesian 3D printing, smooth rods are used as guides for linear motion. They are commonly used in the Y-axis assembly to provide a smooth and low-friction surface for the print bed to move along the Y-axis.

#### Pulley: 
A pulley is a wheel with a grooved rim that is used with a belt or cable to transmit motion. In Cartesian 3D printing, pulleys are often used in conjunction with belts to transfer rotational motion from a motor to linear motion. They are commonly used in the Y-axis assembly to drive the movement of the print bed along the Y-axis.

#### Motor: 
In Cartesian 3D printing, motors play a crucial role in controlling the movement of various components. Stepper motors are commonly used for their precise control and ability to move in discrete steps. In the Y-axis assembly, a motor is typically used to drive the motion of the print bed along the Y-axis. The motor receives commands from the printer's controller and rotates the pulley or threaded rod to move the print bed.

#### Y-Axis Frame: 
The Y-axis frame refers to the structural framework that supports and houses the components of the Y-axis assembly in a Cartesian 3D printer. It provides rigidity and stability to the Y-axis components, including the smooth rods, bearings, pulleys, and motor. The Y-axis frame ensures proper alignment and smooth operation of the Y-axis movement.

#### Y-Axis Base: 
The Y-axis base is the foundation or bottommost part of the Y-axis assembly in a Cartesian 3D printer. It serves as the mounting platform for the Y-axis frame, smooth rods, bearings, pulleys, and other components. The Y-axis base provides stability and structural support to the Y-axis assembly, ensuring accurate and stable movement of the print bed along the Y-axis.
### Z-axis assembly:-


![zaxis](https://github.com/A-Thiyagarajan/Ex.-No.-3---SIMULATION-OF-CARTESIAN-3D-PRINTER-MACHINE/assets/118707693/87a3f618-0d07-4e41-962b-36ed427fd1d8)



#### Z-Axis Rod: 
The Z-axis rod refers to a vertical cylindrical rod used in Cartesian 3D printers to provide linear motion along the Z-axis. It is typically a smooth or threaded rod, often made of hardened steel or aluminum. The Z-axis rod is responsible for raising and lowering the print head or the print bed, allowing for layer-by-layer construction of the 3D printed object.

#### Z-Axis Top Cover: 
The Z-axis top cover is a protective covering or enclosure that sits on top of the Z-axis assembly in a Cartesian 3D printer. It helps to shield and secure the components of the Z-axis, such as the motor, threaded rod, and guide mechanism, from dust, debris, and accidental contact.

#### Motor: 
In Cartesian 3D printing, a motor is an essential component used to drive the motion of various parts of the printer. Stepper motors are commonly used due to their precise control and ability to move in discrete steps. In the context of the Z-axis assembly, a motor is typically employed to rotate the threaded rod, which in turn raises or lowers the print head or print bed along the Z-axis. The motor receives commands from the printer's controller and provides the necessary torque and rotation to achieve the desired vertical movement.
### Completed assembly:-


![cartesian3d](https://github.com/A-Thiyagarajan/Ex.-No.-3---SIMULATION-OF-CARTESIAN-3D-PRINTER-MACHINE/assets/118707693/d1bf43ed-b150-4246-9d65-add65e0ffea0)



#### Frame: 
The frame in Cartesian 3D printing refers to the structural framework or chassis that provides the overall support and stability to the printer. It serves as the foundation and holds all the major components together, such as the Y-axis assembly, Z-axis assembly, X-axis assembly, print bed, and extruder. The frame ensures rigidity and proper alignment of the printer components, contributing to accurate and precise printing.

#### Y-Axis Assembly: 
The Y-axis assembly is the component of a Cartesian 3D printer responsible for the movement along the Y-axis. It typically includes the smooth rods, linear bearings, motor, belt or threaded rod, and the print bed. The Y-axis assembly enables the print bed to move back and forth horizontally, allowing for the creation of the object's width.

#### Z-Axis Assembly: 
The Z-axis assembly in Cartesian 3D printing controls the vertical movement of the print head or print bed. It consists of components such as the Z-axis rod, motor, threaded rod, linear bearings, and the print head or print bed. The Z-axis assembly allows for layer-by-layer deposition of the 3D printed object along the vertical height.

#### X-Axis Assembly: 
The X-axis assembly is responsible for the movement of the print head or extruder assembly in the Cartesian 3D printer. It typically includes the smooth rods, linear bearings, motor, belt or threaded rod, and the print head or extruder. The X-axis assembly enables the print head or extruder to move left and right, contributing to the object's length.

#### SMPS: 
SMPS stands for Switched Mode Power Supply. It is an electronic power supply unit used in Cartesian 3D printers to convert the input AC voltage from a power source into the appropriate DC voltage required for the printer's operation. The SMPS supplies power to various components of the printer, such as the motors, controller board, and heated bed.

#### LCD: 
LCD stands for Liquid Crystal Display. In the context of Cartesian 3D printing, an LCD is a display screen commonly found on 3D printers. It provides a visual interface for controlling the printer's settings, such as temperature, speed, and print progress. The LCD allows users to interact with the printer and navigate through menus using buttons or a rotary encoder.

#### Spool Holder: 
A spool holder is a component used to hold the filament spool in a Cartesian 3D printer. It is designed to securely mount the filament spool and ensure smooth filament feeding during the printing process. The spool holder can be attached to the printer's frame or placed externally.

#### Spool: 
A spool refers to a cylindrical object that holds the filament material used for 3D printing. Filament is wound around the spool, and it is typically made of plastic or metal. The spool is mounted on the spool holder, and the filament is fed from the spool into the extruder for printing.


## Output:
![image](https://github.com/Sellakumar1987/Ex.-No.-3---SIMULATION-OF-CARTESIAN-3D-PRINTER-MACHINE/assets/113594316/e00b82b4-9aff-400f-9c57-288254dc3cd2)

##### Name: SARGURU K
##### Register Number: 212222230134

## Result: 
Thus the simulation on construction of cartesian 3D printer is completed & movement of axis along X, Y, & Z has been studied.



# Ex. No.4 SIMULATION OF POLAR 3D PRINTER MACHINE

#### DATE: 18.05.2023

## AIM:
### To simulate the construction of polar 3D printer and to get in-depth knowledge of mechatronics of polar 3D printers.

![image](https://github.com/Sellakumar1987/Ex.-No.-4---SIMULATION-OF-POLAR-3D-PRINTER-MACHINE/assets/113594316/b551f195-9877-49a2-99bb-a9efcfb3381a)

## REQUIREMENTS:
### ●	System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:

## Assembly of Polar 3D Printer
### 1.	Select 'Assembly of Polar 3D Printer' from the visible list.
### 2.	All the parts related to Polar 3D Printer will be shown on the screen.
### 3.	Select the parts in sequence in which they are shown.
### 4.	When the first part is selected then it will open in the blank space in the left side of the screen.
### 5.	Further, when the correct part will be selected then it will get assembled with the previously selected part/parts.
### 6.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## Playing with Axes
### 1.	Move the r-axis slider and observe the movement of the r-axis assembly.
### 2.	Move the y-axis slider and observe the movement of the y-axis assembly.
### 3.	Move the z-axis slider and observe the movement of the z-axis assembly.

## OUTPUT:
### Polar 3d printer:-


![polar3d](https://github.com/A-Thiyagarajan/Ex.-No.-4---SIMULATION-OF-POLAR-3D-PRINTER-MACHINE/assets/118707693/fb830188-eadb-4af9-99b0-3d6c0ac9a8d5)


#### Y-Axis Base: 
The Y-axis base is the foundational component of the printer's Y-axis assembly. It serves as the mounting platform for other Y-axis components, such as smooth rods, bearings, motors, and the print bed. The Y-axis base provides stability and support to ensure accurate movement along the Y-axis.

#### Z-Axis Frame: 
The Z-axis frame is the structural framework that supports and houses the components involved in the Z-axis assembly. It typically includes the smooth rods, linear bearings, threaded rods, and the print head or extruder assembly. The Z-axis frame ensures stability and proper alignment for vertical movement.

#### Smooth Rods: 
Smooth rods are cylindrical bars with a smooth and polished surface. In the context of a Polar 3D printer assembly, smooth rods are used as guides for linear motion. They provide a low-friction surface for the print bed or extruder assembly to move smoothly along the designated axes.

#### Motors: 
Motors in a Polar 3D printer assembly are electrical devices that convert electrical energy into mechanical motion. They are typically stepper motors used to drive the movement of various printer components, such as the print bed, extruder assembly, or Z-axis mechanism. Motors play a crucial role in achieving precise and controlled movements during the printing process.

#### Extruder Supporter: 
The extruder supporter refers to a component in the printer assembly that provides support and stability to the extruder assembly. It is typically a structural element or bracket that holds the extruder securely in place, ensuring proper alignment and movement during the printing process.

#### Threaded Rod: 
A threaded rod is a cylindrical rod with a helical thread pattern along its length. In a Polar 3D printer assembly, threaded rods are commonly used in the Z-axis mechanism. They are rotated by the motor to raise or lower the print head or print bed along the Z-axis.

#### Y-Axis Frame: 
The Y-axis frame is a structural framework that supports the Y-axis assembly components, such as smooth rods, bearings, and the print bed. It provides rigidity and stability, ensuring accurate and controlled movement along the Y-axis.

#### Motor with Gear: 
A motor with gear refers to a stepper motor coupled with a gear mechanism. It is used to transmit rotational motion from the motor to other components in the printer assembly. The gear mechanism helps to increase torque or change the speed of the motor's output.

#### Motor-with-Pulley: 
Similar to the motor with gear, a motor with a pulley combines a stepper motor with a pulley mechanism. The motor rotates the pulley, which is connected to a belt or cable, enabling precise movement of components such as the print head or print bed.

#### Gears: 
Gears are toothed mechanical components used to transmit and control rotational motion between two shafts. In the context of a Polar 3D printer assembly, gears may be used in the motor system or other mechanisms to control movement and achieve proper gear ratios.

#### Plate: 
In a Polar 3D printer assembly, a plate refers to a flat and rigid component that serves as a structural element or mounting platform for various printer components. It provides stability, alignment, and support for the assembly.

#### Extruder: 
The extruder is a critical component in a Polar 3D printer assembly. It is responsible for feeding filament material, typically plastic, into the hot end or nozzle. The extruder consists of a motor, filament drive mechanism (such as a gear or wheel), and a heating element. It controls the precise deposition of molten filament to create the 3D printed object.

#### Filament: 
Filament is the material used in 3D printing, usually in the form of a long, thin strand. In a Polar 3D printer assembly, filament is typically made of plastic and is fed into the extruder. The extruder heats and melts the filament, allowing it to be deposited layer by layer to create the final 3D printed object.


## Output:
![image](https://github.com/Sellakumar1987/Ex.-No.-4---SIMULATION-OF-POLAR-3D-PRINTER-MACHINE/assets/113594316/88273b69-4e7d-4f42-9115-fb07ac22e4ec)

### Name:SARGURU K
### Register Number: 212222230134

## Result: 
### Thus the simulation on construction of polar 3D printer is completed & movement of axis along X, Y, & Z has been studied.



# Ex. No. 5 - SIMULATION-OF-DELTA-3D-PRINTER-MACHINE

### DATE: 18-05-2023
## AIM:
### To simulate the construction of delta 3D printer and to get in-depth knowledge of mechatronics of delta 3D printer.

![image](https://github.com/Sellakumar1987/Ex.-No.-5---SIMULATION-OF-DELTA-3D-PRINTER-MACHINE/assets/113594316/c784471e-098f-456d-9c1b-e9f0ce56cc9b)

## REQUIREMENTS:
### ●	System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:

## Assembly of Delta 3D Printer
### 1.	Select 'Assembly of Delta 3D Printer' from the visible list.
### 2.	All the parts related to Delta 3D Printer will be shown on the screen.
### 3.	Select the parts in sequence in which they are shown.
### 4.	When the first part is selected then it will open in the blank space in the left side of the screen.
### 5.	Further, when the correct part will be selected then it will get assembled with the previously selected part/parts.
### 6.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## Playing with Axes
### 1.	Move the z1-axis slider or enter the value (within the given range) in the given text box and press/select ENTER. Now observe the movement of the z1-axis assembly.
### 2.	Move the z2-axis slider or enter the value (within the given range) in the given text box and press/select ENTER. Now observe the movement of the z2-axis assembly.
### 3.	Move the z3-axis slider or enter the value (within the given range) in the given text box and press/select ENTER. Now observe the movement of the z3-axis assembly.

## Delta 3D Printer:-

![delta3d](https://github.com/A-Thiyagarajan/Ex.-No.-5---SIMULATION-OF-DELTA-3D-PRINTER-MACHINE/assets/118707693/b06eff16-49c8-45d3-bc07-4697846a87db)


### Base: 
The base refers to the bottommost part of the delta 3D printer assembly. It serves as the foundation and provides stability to the printer. The base is typically a solid structure that supports other components and ensures the printer's overall structural integrity.

### Holder: 
A holder is a component used to secure and hold various parts in place within the printer assembly. It can be a bracket, clamp, or similar device designed to maintain the position and stability of specific components.

### Rod: 
In the context of a delta 3D printer assembly, a rod refers to a long and slender cylindrical structure. Rods are often made of metal or other rigid materials and play a crucial role in the printer's construction and movement system. They are typically used as arms or supports in the delta mechanism to control the positioning of the print head.

### Top cover: 
The top cover is a protective covering or enclosure that is placed over the top part of the delta 3D printer assembly. It helps shield the internal components from dust, debris, and accidental contact. The top cover can be removable or integrated into the frame design.

### Top cover frame: 
The top cover frame refers to the structural framework that supports and holds the top cover in place. It provides stability and rigidity to the top cover and ensures proper alignment with the rest of the printer assembly.

### Linear rail: 
A linear rail is a guiding mechanism used to provide smooth and precise linear motion in a delta 3D printer. It consists of a rail and a carriage that moves along the rail. The linear rail system enables the smooth movement of the print head or other components along a specific axis.

### Motor: 
Motors in a delta 3D printer assembly are electrical devices that convert electrical energy into mechanical motion. They are typically stepper motors used to control the movement of the print head or other components in the printer. Motors play a critical role in achieving accurate positioning and controlled movement during the printing process.

### Bed: 
The bed, also known as the print bed or build plate, is the surface on which the object being printed is created. It can be a flat or heated platform that provides a stable and level surface for the print job. The bed moves or remains stationary while the print head deposits layers of material to build the object.

### Slide with connector: 
The slide with connector refers to a component in the delta 3D printer assembly that allows smooth and controlled sliding motion. It is often used in the arms or carriages of the delta mechanism to facilitate the movement of the print head.

### Connecting Rods: 
Connecting rods are rigid bars that connect different components in the delta 3D printer assembly. They are used to link the various moving parts and ensure coordinated and synchronized movement.

### Extruder: 
The extruder in a delta 3D printer assembly is responsible for feeding and controlling the flow of filament material during the printing process. It typically consists of a motor, filament drive mechanism, and a hot end or nozzle. The extruder melts the filament and deposits it layer by layer to create the 3D printed object.

### Pins: 
Pins are small cylindrical metal or plastic components used to secure or connect different parts of the printer assembly. They may act as axles, pivot points, or locking mechanisms in various joints and connections.

### Motor with gear: 
A motor with gear refers to a stepper motor coupled with a gear mechanism. This combination allows for increased torque or speed reduction, depending on the gear ratio. Motor with gears are commonly used in delta 3D printers to provide precise and controlled movement.

### LCD: 
LCD stands for Liquid Crystal Display. In the context of a delta 3D printer assembly, an LCD is a display screen integrated into the printer's control interface. It provides visual feedback and allows the user to interact with the printer by displaying menu options, settings, print progress, and other relevant information.


## OUTPUT:
![image](https://github.com/Sellakumar1987/Ex.-No.-5---SIMULATION-OF-DELTA-3D-PRINTER-MACHINE/assets/113594316/1f3e6b6d-0724-41dc-b7d2-15516060d066)


### Name: SARGURU K
### Register Number: 212222230134

## Result: 
Thus the simulation on construction of delta 3D printer is completed & movement of axis along X, Y, & Z has been studied.


# Ex. No. 6 - SIMULATION OF FUSED DEPOSITION MODELING PROCESS

## DATE: 25-05-2023
## AIM:
### To simulate the Fused Deposition Modeling (FDM) process.

## REQUIREMENTS:
### System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:
### STEP 1: Click on 'Base'. Base and Build Platform will be displayed on the left side of the screen.
### STEP 2: Click on 'Extruder' then extruder and extruder nozzle will be displayed.
### STEP 3: Click on 'Material Spool' then material spool will be shown.
### STEP 4: Click on 'Filament' then filament will be added.
### STEP 5: Click on 'Start Process' to begin the process.
### STEP 6: After the process is complete click on 'Stop Process' to view product generated using FDM process.

## OUTPUT:
![123_1](https://github.com/Sellakumar1987/Ex.-No---6.-SIMULATION-OF-FUSED-DEPOSITION-MODELING-PROCESS/assets/113594316/998a5e1b-4fea-4f03-a323-dd49973513a7)
![123_2](https://github.com/Sellakumar1987/Ex.-No---6.-SIMULATION-OF-FUSED-DEPOSITION-MODELING-PROCESS/assets/113594316/92d9d5de-1d13-43b2-a354-c3429e38d50b)
![123_3](https://github.com/Sellakumar1987/Ex.-No---6.-SIMULATION-OF-FUSED-DEPOSITION-MODELING-PROCESS/assets/113594316/e05c97f8-b035-4e4d-86e8-f91a73aa95a8)

https://github.com/Sellakumar1987/Ex.-No---6.-SIMULATION-OF-FUSED-DEPOSITION-MODELING-PROCESS
## Output:
![Output](Output_lab6_EMPD.png)
### Name:SARGURU K
### Register Number:212222230134

## Result:
### Thus the simulation on the FDM process is completed & prototyping process is studied.



# Ex. No. 7 - SIMULATION OF PRE PROCESSING IN ADDITIVE MANUFACTURING
### DATE: 30.05.2023
## AIM:
### To simulate the Pre Processing for 3D printing.

## REQUIREMENTS:
### System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:
### Pre-processing encompasses the steps between design and printing. Process of 3D printing starts with designing in CAD. Then printer software slices 3D CAD file into layers. For each slice, the software converts the data into machine code that determines tool paths for the machine to follow. The various steps in pre-processing from design to printing are as follows:

### 1)	CAD File
### 2)	Conversion to STL a. Orientation b. Support Structure c. Slicing d. Path Planning

### 1. CAD File
### Every manufacturing process starts with the process of designing and as in any type of manufacturing, there are certain limitations to the materials and manufacturing processes that dictate how the product should be designed, 3D printing is no different. In 3d printing, characteristics of hardware, software, temperature, filament and many other factors play an important role in how a digital model translates into a printed object. Some of them are designed with a strong base, grain direction, overhung, wall thickness, round corners and tolerances.

### 2. Conversion to STL
### In order to check the interface of the object and make it reliable to 3d printers, conversion to STL file is required. It also facilitates other features like quick error check, bridging the gap between CAD platforms, exhibition purposes and 3D digitizer extension.

### a. Orientation:
### Orientation plays a vital role in the final product of 3d printing as it affects the part accuracy, manufacturing time, strength and surface finish. There are various orientations by which we can print the object such as vertically upward, vertically downward and in horizontal plane.

### b. Support Structure:
### Support structures are required where the objects are unable to get printed directly. Support structures help to guarantee the printability of a section during the 3D printing measure and also it can assist with forestalling part twisting, secure a section to the printing bed and guarantee that parts are joined to the fundamental body of the printed part.

### c. Slicing:
### The motive behind slicing a 3D model is to transform the model into guidelines for the 3D printer. To play out this errand, the slicing software isolates the item into numerous layers. It's classified "slicing" since it "slices" the 3D model to make numerous layers. After the layers have been made, the slicing software applies different qualities to every one of them.

### d. Path Planning:
### Path planning helps to improve the printed surface quality, shape accuracy and infill distribution quality. There are various ways for path planning which can be used to print the objects which may affect the following factors in objects like raster path, grid path, spiral path and zigzag path.

![image](https://github.com/Sellakumar1987/Ex.-No.-7---SIMULATION-OF-PRE--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/113594316/baef8515-67d7-4c96-accc-4ee88035c9e7)

### ●	All the processes related to pre-processing will be shown on the screen.
### ●	Select CAD file preparation from the visible list.
### ●	When the first process is selected then it will open in the blank space in the left side of the screen.
### ●	Select the options of process of pre-processing in the sequence in which they are shown.
### ●	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the process to be selected.

## OUTPUT:

### Step 1:

![s1](https://github.com/A-Thiyagarajan/Ex.-No.-7---SIMULATION-OF-PRE--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/669cfe37-a827-4603-991b-c10aaaf49b41)



#### Strong Base: 
Adding suitable support structures during pre-processing ensures stability and prevents deformation or collapse during the additive manufacturing process.

#### Rounded Corner: 
Intentionally rounding corners reduces stress concentration, improving part strength and reducing the risk of failure during additive manufacturing.

#### Sharp-Edged Corner: 
Care must be taken with sharp-edged corners in additive manufacturing, as layer-by-layer printing processes can present challenges, requiring special attention and potentially post-processing techniques for desired sharpness.

#### Wall Thickness: 
Optimizing wall thickness is crucial for balancing structural integrity, printability, and efficiency in additive manufacturing, as excessively thin walls may lead to weakness while excessively thick walls can increase print time and cost.

### Step 2:

![s2](https://github.com/A-Thiyagarajan/Ex.-No.-7---SIMULATION-OF-PRE--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/32001e7c-2896-4c73-9fe7-30fd07aefb60)



The code snippet you provided outlines the structure of a triangle in an STL (STereoLithography) file, which is a common file format used for 3D printing. Each triangle represents a facet of the 3D model. Here's a breakdown of the code:

"Facet normal ni nj nk": This line specifies the normal vector of the facet, where "ni," "nj," and "nk" are the x, y, and z components of the normal vector, respectively. The normal vector defines the orientation of the triangle's surface.

"Outer loop": This line indicates the start of the loop that defines the vertices of the triangle.

"Vertex v1x v1y v1z": This line specifies the coordinates of the first vertex of the triangle, where "v1x," "v1y," and "v1z" are the x, y, and z coordinates, respectively.

"Vertex v2x v2y v2z": This line specifies the coordinates of the second vertex of the triangle, similar to the previous line.

"Vertex v3x v3y v3z": This line specifies the coordinates of the third vertex of the triangle, following the same pattern as the previous lines.

"End loop": This line marks the end of the loop that defines the vertices of the triangle.

"End facet": This line signifies the end of the triangle or facet definition.
### step 3:


![s3](https://github.com/A-Thiyagarajan/Ex.-No.-7---SIMULATION-OF-PRE--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/42667ff1-5ee8-433c-8d72-b29820b56011)


#### Printing a cylinder vertically upward in a 3D printer:

Printing a cylinder vertically upward in a 3D printer offers benefits such as increased strength along the vertical axis, smoother vertical surfaces, reduced need for support structures, suitability for tall cylinders, and enhanced performance in vertical load-bearing applications. This orientation aligns layers to maximize strength and achieve a better surface finish, while minimizing the requirement for additional supports.

#### Printing a cylinder horizontally in a 3D printer:

Printing a cylinder horizontally in a 3D printer allows for improved surface finish on horizontal surfaces, but may require support structures to maintain stability and prevent deformation. This orientation offers versatility for cylinders of varying heights and diameters, making it suitable for a range of applications. However, careful placement and removal of support structures are necessary to ensure print success and maintain the shape of the cylinder. Horizontal printing is beneficial for parts that require strength and durability in horizontal directions, such as tabletops or brackets.

### Step 4:


![s4](https://github.com/A-Thiyagarajan/Ex.-No.-7---SIMULATION-OF-PRE--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/f5513576-9740-448c-8361-d49ac76fbf9a)


Printing a part with support structures in 3D printing involves adding additional material to provide stability for overhanging or intricate features, preventing deformations or collapses during the printing process. These supports are designed to be easily removable after printing, but they may leave marks or require post-processing. Conversely, printing a part without support structures is suitable for simple designs or self-supporting geometries, saving time and minimizing the need for post-processing. However, it's crucial to consider print orientation and geometry to ensure successful printing and maintain the desired part quality.

### Step 5:


![s5](https://github.com/A-Thiyagarajan/Ex.-No.-7---SIMULATION-OF-PRE--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/e15ac3c9-7d46-43e1-89a9-d0e58f7e394a)


#### Uniform Slicing: 
In uniform slicing, the 3D model is divided into equally spaced layers of consistent thickness, resulting in a regular and predictable printing process.

#### Adaptive Slicing: 
Adaptive slicing adjusts the layer thickness dynamically based on the geometry of the model. It allows for variable layer thickness to capture fine details and reduce print time for less complex regions.

#### Curved Layer Slicing: 
Curved layer slicing introduces a curved or variable layer thickness, following the contours of the model. It aims to enhance the surface finish and accuracy by aligning the layer boundaries with the shape of the model.

Uniform slicing provides simplicity and consistency, while adaptive slicing offers better efficiency and detail reproduction. Curved layer slicing focuses on improving surface quality by adapting layer thickness to the model's curvature.

The choice of slicing method depends on the specific requirements of the printed part, such as surface finish, print time, and geometric complexity.


### Step 6:

![s6](https://github.com/A-Thiyagarajan/Ex.-No.-7---SIMULATION-OF-PRE--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/3c37595d-aec1-4605-b818-8f23e51be92d)



#### Fractonal: 
Fractonal slicing divides the layers into smaller sub-layers or fractional layers, allowing for enhanced surface quality and finer details in the printed part.

#### Zig-Zag: 
Zig-zag slicing involves printing each layer in a back-and-forth pattern, reducing the need for travel moves and optimizing print time. It is commonly used for infill patterns to maximize efficiency.

#### Contour Offset Path: 
Contour offset path slicing involves printing the outer boundary of a layer first and then moving inward, creating a smooth surface finish and minimizing the visibility of layer lines on the outer surface of the part.

#### Grid Path: 
Grid path slicing follows a grid-like pattern, where each layer is printed in a back-and-forth motion in one direction, followed by a shift in the perpendicular direction. This method is often used for infill patterns to provide strength and stability to the part.

The choice of slicing method depends on factors such as desired surface finish, print time, strength requirements, and the geometry of the part being printed.


## Output:

### Name:SARGURU K
### Register Number:212222230134

## Result: 
### Thus the simulation on the Preprocessing in additive manufacturing is completed.




# Ex. No. 8 - PROTOTYPE PART MODEL DESIGN IN 3D PRINTER

### DATE: 3/6/23
## AIM: 
### To prototype the given part model design in 3D Printer.

## REQUIREMENTS:
### ●	3D Printer machine.
### ●	CURA 4.0 Software.
### ●	Autodesk Fusion 360 Software.
### ●	System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:

### Step 1:- Check all Electrical connections.

### Step 2:- First we install the software related the 3D printer (idea maker, ultimaker etc.)In idea maker first open the software and click the open file option as shown in below figure.

![image](https://github.com/Sellakumar1987/Ex.-No.-8.-PROTOTYPE-PART-MODEL-DESIGN-IN-3D-PRINTER/assets/113594316/059ab4e7-f3fb-49a9-ba8e-12bdd082abef)

### Step 3:- select the Pan option and select the extruder (left of right) for printing the design and then after select the Repair option for auto correction of design of software parameter as shown in below figure.

![image](https://github.com/Sellakumar1987/Ex.-No.-8.-PROTOTYPE-PART-MODEL-DESIGN-IN-3D-PRINTER/assets/113594316/835c55fd-6195-4d73-9f5c-4af36f5a4cce)

### Step 4.:- select the Move option for design print position in build tack plate and then after select the Rotate option for rotate the design easily printed and used low print material as shown in below figure.

![image](https://github.com/Sellakumar1987/Ex.-No.-8.-PROTOTYPE-PART-MODEL-DESIGN-IN-3D-PRINTER/assets/113594316/8736080c-f421-4dd0-bae8-860df6f3583e)

### Step 5.:- select the Scale option for design scale according to build plate area and then after click the start option and select printing option standard as shown in below figure.

![image](https://github.com/Sellakumar1987/Ex.-No.-8.-PROTOTYPE-PART-MODEL-DESIGN-IN-3D-PRINTER/assets/113594316/98458892-2f68-4de0-bec7-24959ec598fa)

### Step 6.:- After completing all settings then click the Slice option and export the file in gcode format.

![image](https://github.com/Sellakumar1987/Ex.-No.-8.-PROTOTYPE-PART-MODEL-DESIGN-IN-3D-PRINTER/assets/113594316/f4b8b55e-6cb2-46a7-b42c-180bc5e68668)

![image](https://github.com/Sellakumar1987/Ex.-No.-8.-PROTOTYPE-PART-MODEL-DESIGN-IN-3D-PRINTER/assets/113594316/eafa933a-7e03-4f73-930d-75fb28d48716)

### Step 7.:- After generating the gcode format then follow the these instruction as shown in below figure.
###   1.	Switch on the 3d printer.
###   2.	Place your Pen drive in USB.
###   3.	Clean the surface bed plate.
###   4.	Load filament into the required extruder as per the requirement.
###   5.	Wait until the nozzle & bed plate comes into the required temperature.
###   6.	Close the doors of the 3d printer.
###   7.	Open the file from the USB storage and select the Print option.

## Output:

![keyboard ](https://github.com/A-Thiyagarajan/Ex.-No.-8.-PROTOTYPE-PART-MODEL-DESIGN-IN-3D-PRINTER/assets/118707693/2d9ee32a-8317-4a53-907c-146116ccd494)





### Name: SARGURU K
### Register Number: 212222230134

## RESULT:
###   Thus a prototype of the given part model is developed using 3D Printer.



# Ex.No.9 - SIMULATION OF POST PROCESSING IN ADDITIVE MANUFACTURING

### DATE: 2.6.23

## AIM: 
### To simulate the post processing of 3d printed parts via support Removal, UV Curing & Heat Treatment.

## REQUIREMENTS:
### System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:

## Procedure for support removal
### 1.	Select support removal from the list.
### 2.	All the parts related to support removal are shown on the screen.
### 3.	Select the parts in sequence in which they are shown.
### 4.	When the first part is selected then it will open in the blank space in the left side of the screen.
### 5.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## Procedure for UV Curing
### 1.	Select UV curing from the list.
### 2.	All the parts related to UV curing are shown on the screen.
### 3.	Select the parts in sequence in which they are shown.
### 4.	When the first part will be selected then it will open in the blank space on the left side of the screen.
### 5.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## Procedure for heat treatment
### 1.	Select heat treatment from the list.
### 2.	All the parts related to heat treatment are shown on the screen.
### 3.	Select the parts in sequence in which they are shown.
### 4.	When the first part is selected then it will open in the blank space in the left side of the screen.
### 5.	If the user follows an incorrect sequence then a pop-up will appear on the screen showing the name of the part to be selected.

## OUTPUT :

## Support Removal Process
### Step 1:

![71](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/12ec7b57-02b8-4514-a9c5-0049fb0324c5)


In a 3D printer, the main part refers to the primary structure or framework that holds and guides the printing process, typically including the frame, motors, and control systems.

Support in a 3D printer refers to the additional structures or materials used to provide stability and reinforcement to the printed object during the printing process, such as support structures or rafts that are printed alongside the main part to prevent deformation or collapse.


Together, the main part and support elements in a 3D printer ensure the accuracy, stability, and successful fabrication of complex three-dimensional objects by providing a solid foundation and temporary scaffolding when necessary.

### Step 2:

![72](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/4127a897-e365-4b3e-a961-b98d6c2095f3)



A container refers to a vessel or reservoir used to store and dispense a chemical solution, such as a resin or filament material, which is essential for the printing process.

A chemical solution in a 3D printer typically refers to a specialized material, such as a photopolymer resin, that undergoes a chemical reaction, such as curing or solidification, when exposed to specific conditions, such as UV light or heat. This solution is used as the raw material for creating 3D printed objects.

The container holds the chemical solution, which is then selectively dispensed and processed by the 3D printer to form successive layers and ultimately build the desired object. The properties and characteristics of the chemical solution greatly impact the final quality and properties of the printed object.

### Step 3:
![73](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/cdfd39d7-a2c3-4457-a379-91fbfd2a1b7f)



When a 3D model is dropped into a chemical solution in the context of 3D printing, it typically refers to a process known as resin or vat polymerization. The model is submerged or lowered into a liquid resin or photopolymer solution.

Once the model is immersed in the chemical solution, it undergoes a chemical reaction, often triggered by light exposure or heat, causing the resin to solidify or cure selectively, layer by layer, following the design of the 3D model.

This process allows for the creation of intricate and precise three-dimensional objects with fine details, as the chemical solution hardens and adheres to the model's surfaces, forming a solid, tangible representation of the original 3D model.


### Step 4:

![74](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/f6b05e23-f7e6-4959-98d2-94d6e61c4f51)



In 3D printing, the main part refers to the primary component or structure of the printed object itself, excluding any support structures or additional elements.

It represents the intended design or shape that is being fabricated layer by layer, using the chosen printing technology and material, without the need for additional temporary or auxiliary structures.

The main part in 3D printing is the final desired outcome, embodying the form and function specified in the 3D model, and does not include any additional support structures that may be required during the printing process.


### Step 5 & 6:

![76](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/2c2f5fbc-5b17-49be-85fb-c35ff7092d08)



In the support removal process of additive manufacturing, the final product is often dipped in a container filled with a support removal solution. The solution is specifically formulated to dissolve or weaken the support structures while preserving the integrity of the printed part. The dipping process allows the solution to penetrate and remove the supports, resulting in a clean and finished product.

## UV Curing of 3D printed part
### Step 1:


![77](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/9e596f90-afea-49fd-b00c-107e87036ba4)



Before UV curing in the context of 3D printing, the part refers to the printed object that has been created through the additive manufacturing process, typically using a resin-based material.

At this stage, the part is in a semi-solid or liquid state, as it has been formed by depositing and solidifying layers of the printing material, but has not yet undergone the final curing or hardening process.

The part may still be fragile or prone to deformation, and additional post-processing steps, such as cleaning or removal of excess material, may be necessary before subjecting it to UV curing.

### Step 2:


![78](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/5b99f798-35c6-4e5b-9cd4-337441f47355)



A UV carving machine is a cutting-edge device used for precise and intricate carving on various materials. It utilizes ultraviolet (UV) light technology to etch designs on surfaces. The machine employs a high-powered laser that focuses UV light to remove layers of material, creating intricate patterns and textures. It is commonly used in industries such as signage, woodworking, and jewelry making. UV carving machines offer excellent precision, speed, and versatility, making them a valuable tool for artistic and industrial applications.

### Step 3:

![79](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/18eb59b7-52f0-4144-9600-635f7c3238a2)



When using a UV carving machine, the parts being carved must be carefully prepared and positioned. The parts are typically placed onto a worktable or fixture within the machine. It is essential to ensure that the parts are securely held in place to prevent movement during the carving process. Proper alignment and orientation are crucial to achieving accurate and consistent results. Depending on the machine's design, parts may be manually loaded or placed onto a conveyor system for automated carving.

### Step 4:

![710](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/2a448081-a905-4e47-bec4-85e0643efe98)



After the UV carving process, the parts undergo a post-carving treatment. This treatment may involve removing any excess debris or dust from the carved surface using compressed air or gentle cleaning methods. The parts may also be inspected to ensure the desired carving quality and precision have been achieved. Depending on the material and application, additional steps like polishing, coating, or finishing may be performed to enhance the appearance and durability of the carved parts. Finally, the parts are ready for use or further processing according to the specific application requirements.

### Step 5 & 6:

![711](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/33c85dd0-aad6-4dc0-b40c-6ea1868d5247)



The UV light technology used in these machines focuses on the precise removal of material layers through photopolymerization. Heating the final product may not be necessary unless there are specific post-processing requirements for the material being carved. If heat treatment is needed, it would typically be carried out separately using specialized equipment or methods suited for the specific material and desired outcome.



## Heat Treatment of 3D printed part

### Step 1:


![713](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/91cda397-f4d2-4693-aa4a-14fbdd2fc64e)


Before heat treatment, the part that has undergone UV carving should be thoroughly cleaned and inspected. The cleaning process ensures the removal of any debris, dust, or residues from the carving process. Inspection is carried out to verify the quality and accuracy of the carving and identify any potential flaws or imperfections. Proper cleaning and inspection are crucial to ensure that the part is ready for the subsequent heat treatment process, which may involve specific temperature and time requirements based on the material and desired outcome.


### Step 2:


![714](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/f2cf7f74-3d15-440d-a002-608713137601)


A heat treatment oven is a specialized piece of equipment used to subject materials to controlled heating processes. It is designed to provide a controlled environment for heating and treating parts or products. The oven typically has adjustable temperature settings and can reach high temperatures required for specific heat treatment processes. It ensures uniform heat distribution to achieve consistent results. Heat treatment ovens are commonly used in various industries, including metalworking, manufacturing, and ceramics, to modify the material properties such as hardness, strength, or durability through processes like annealing, tempering, or curing.


### Step 3:


![715](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/585c0a65-52c9-4218-bc89-c993b28701a3)


When parts are prepared for entry into a heat treatment oven, they are usually placed onto a suitable tray, rack, or fixture. The parts need to be arranged in a manner that allows for proper heat circulation and ensures even heating throughout. It is important to consider the size, shape, and quantity of the parts to maximize the oven's capacity while maintaining adequate spacing between the parts. Care should be taken to avoid overcrowding, as it can hinder heat transfer and affect the effectiveness of the heat treatment process. Once properly loaded, the parts are then inserted into the heat treatment oven for the desired treatment cycle.


### Step 4:



![716](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/01baa857-03cd-43fe-a4e2-9ad514797f53)


After undergoing heat treatment, the parts are considered the final product. The heat treatment process alters the material's properties, such as hardness, strength, or durability, according to the desired specifications. Depending on the specific heat treatment performed, the parts may be quenched, tempered, annealed, or subjected to other heat treatment processes. The resulting final product exhibits improved mechanical or physical characteristics, making it suitable for its intended application. After heat treatment, the parts may undergo additional finishing processes such as cleaning, polishing, or coating before being assembled or used in the final product assembly.


### Step 5 & 6:


![717](https://github.com/A-Thiyagarajan/Ex.No.9---SIMULATION-OF-POST--PROCESSING-IN-ADDITIVE-MANUFACTURING/assets/118707693/573da4a7-9bf4-4e55-b826-072e64574771)


Further heat treatment of the final product is typically carried out only if there is a specific need or desired outcome. The decision to perform additional heat treatment depends on factors such as the material composition, desired properties, and the intended application of the product. If further heat treatment is required, it would involve subjecting the final product to a controlled heating process using specialized equipment or methods. This subsequent heat treatment may aim to refine or adjust the material's properties, improve structural integrity, relieve residual stresses, or achieve specific metallurgical transformations. The specific temperature, duration, and conditions of the further heat treatment would be determined based on the desired outcome and the material being treated.

### Name:SARGURU K
### Register Number: 212222230134

## Result: 
### Thus the simulation on the Postprocessing in additive manufacturing is completed.


# Ex. 10 - REVERSE ENGINEER THE GIVEN PRODUCT

### DATE: 

## AIM: 
### To reverse engineering the product and prototyping the same in 3D printer.

## REQUIREMENTS:
### ●	CURA 4.0 Software
### ●	 Autodesk Fusion 360
### ●	 System - Windows 7 or higher, 1 GB RAM.

## PROCEDURE:
### Step 1.:- Duplicate all the geometric features for the given object using vernier caliper, measuring tapes or any instruments provided
### Step 2.:- Design the geometric features in 3D using auto desk fusion 360.
### Step 3.:- Save the file and export as .stl
### Step 4.:- Check all Electrical connections in the 3D printer.
### Step 5.:- First we install the software related the 3D printer (idea maker, ultimaker etc.)In idea maker first open the software and click the open file option.
### Step 6.:- Select the Pan option and select the extruder (left or right) for printing the design.
### Step 7.:- Select the Move option for design print position in build tack plate and then after select the Rotate option for rotating the design easily printed and used low print material.
### Step 8.:- select the Scale option for design scale according to build tack plate area and then
### after click the start option and select printing option standard as shown in below figure.
### Step 9.:- After completing the all setting then click the Slice option and export the file in gcode Format.
### Step 10.:- After generate the gcode format then follow the these instruction 
  ###   ●	Switch on the 3d printer.
  ###   ●	Place your Pen drive in USB.
  ###   ●	Clean your surface bed plate.
  ###   ●	Load your filament into the required extruder as per the requirement.
  ###   ●	Wait until the nozzle & bed plate comes into the required temperature.
  ###   ●	Close the doors of the 3d printer.
  ###   ●	Open the file from the USB storage and select the Print option.

## Input:
![241512521-e07f501d-01f3-4799-8a7e-da1cb59b05f0](https://github.com/dharmaraj-007/Ex.-10---REVERSE-ENGINEER-THE-GIVEN-PRODUCT/assets/119560386/de355802-98e6-45b7-8b73-e7fd26ea7253)

### Output:
![241512951-d779075a-d906-4c63-8bed-ab95b048ebb1](https://github.com/dharmaraj-007/Ex.-10---REVERSE-ENGINEER-THE-GIVEN-PRODUCT/assets/119560386/f91ef060-ef2e-4238-95d3-2c752cf52e88)
![241513242-b961831f-19b3-44a8-9623-813716667add](https://github.com/dharmaraj-007/Ex.-10---REVERSE-ENGINEER-THE-GIVEN-PRODUCT/assets/119560386/01e1d80c-4a5a-4f4b-a81d-ecfd9b29456d)


### Name: SARGURU K
### Register Number: 212222230134

## RESULT:
Thus the given product is reverse engineered and prototyped using 3D Printer.


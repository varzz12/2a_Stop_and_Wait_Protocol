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

'''python

    import socket

    s = socket.socket()
    s.bind(('localhost', 8000))
    s.listen(1)

    print("Waiting for connection...")
    conn, addr = s.accept()
    print("Connected to", addr)

    while True:
       data = conn.recv(1024).decode()
       if not data:
          break

    print("Frame received:", data)
    conn.send("ACK".encode())

    conn.close()

    import socket

    s = socket.socket()
    s.connect(('localhost', 8000))

    n = int(input("Enter number of frames: "))

    for i in range(n):
       msg = input("Enter frame: ")
      s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

    s.close()
    
## OUTPUT
<img width="1452" height="302" alt="Screenshot 2026-11-04 100605" src="https://github.com/user-attachments/assets/09212ce6-a2e5-4c07-93a9-c791a30a310e" />
<img width="1440" height="267" alt="Screenshot 2026-11-04 100641" src="https://github.com/user-attachments/assets/ba31a82e-3de5-4c55-a777-8854243c0546" />
<img width="1451" height="130" alt="Screenshot 2026-11-04 100740" src="https://github.com/user-attachments/assets/95bd7386-3a40-46cd-b9e8-cb6b6c58a210" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

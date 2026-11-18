# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## serverfile
```

import socket

server = socket.socket()

server.bind(("127.0.0.1", 5555))

server.listen(1)

print("Server waiting for connection...")

client, addr = server.accept()

print("Connected to:", addr)

filename = input("Enter file name to send: ")

with open(filename, "rb") as file:
    data = file.read()
    client.sendall(data)

print("File sent successfully")

client.close()
server.close()

```
## clientfile
```

import socket

# Create socket
client = socket.socket()

# Connect to server
client.connect(("127.0.0.1", 5555))

# Save file name
save_name = input("Enter name to save file: ")

# Receive data
data = client.recv(1000000)

# Save file
with open(save_name, "wb") as file:
    file.write(data)

print("File received successfully")

# Close connection
client.close()

```
## OUPUT
<img width="877" height="198" alt="image" src="https://github.com/user-attachments/assets/6a474169-4814-4412-bf01-fd11674b1b25" />
<img width="873" height="143" alt="image" src="https://github.com/user-attachments/assets/3b7c4c57-70cd-40f9-98ec-1661f0c30f88" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.

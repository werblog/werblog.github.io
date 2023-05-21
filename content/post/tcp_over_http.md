---
title: TCP UDP OVER THE HTTp
date: 2023-05-17T22:43:28Z
image: "thumb-1920-924466.jpg"

---
https://github.com/jpillora/chisel

## Benefits?
1 -: You can use TCP over HTTP or UDP over http : simple dns serever  
2 -: If your Cloud Provider doesn't allow tcp,udp port forward then you can go with this project

## How is this work
![alt text](https://werblog.github.io/images/tunnel.png)
This project create a tunnel like a reverse proxy  but fast '


# Tutorial
Installation:
Download the chisel from [here](https://github.com/jpillora/chisel/releases/tag/v1.8.1)  

For server: 
 ```chisel server --port $PORT --proxy http://example.com```
 Client: 
 ``` chisel client http://<ip addr or domain> 3000 ```
 The command fowward the server 3000 port to client 
 

For benchmarking the reverse proxy speed
```
# Terminal 0 - Netcat listening
nc -l 1234 > /dev/null

# On server 1 - Server Node
chisel server --port $PORT --proxy http://example.com

# On client 2 - Client Node
chisel client http://<ip addr or domain> 1234

# On client 3 - Sending \0 data
# Using pipeviewer (pv) to see current data rate
time cat /dev/zero | pv | nc localhost 1234
```
thx for reading ;

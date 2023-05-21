---
title: TCP UDP OVER THE HTTp
date: 2023-05-17T22:43:28Z
image: "thumb-1920-924466.jpg"

---
# https://github.com/jpillora/chisel

## Benefits?
1 -: You can use TCP over HTTP or UDP over http : simple dns serever  
2 -: If your Cloud Provider doesn't allow tcp,udp port forward then you can go with this project

## How is this work
![alt text](https://werblog.github.io/images/tunnel.png)
This project create a tunnel like a reverse proxy  but fast '

You can also use https://github.com/julianbuettner/tcp-over-http this project for tcp over http only:
* Benchmark
🏅 Result: 900MiB/s vs 1.3GiB/s (nc | pv > nc)
Command that use:
```
# Terminal 0 - Netcat listening
nc -l 1234 > /dev/null

# Terminal 1 - Exit Node
tcp-over-http exit --target-addr localhost:1234

# Terminal 2 - Entry Node
tcp-over-http entry --target-url http://localhost:8080/

# Terminal 3 - Sending \0 data
# Using pipeviewer (pv) to see current data rate
time cat /dev/zero | pv | nc localhost 1415
```
thx for reading ;

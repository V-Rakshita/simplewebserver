# EX01 Developing a Simple Webserver
## Date: 27.03.2025
## Name: V. Rakshita
## Register number: 212224100049 

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.


## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<head>
    <title>TCP/IP</title>
</head>
<body bgcolor="skyblue">
    <center>
        <H1>TCP/IP PROTOCOLS</H><br>
    </center>
 <h3>
    1. Application layer protocols - HTTP, FTP, SSH, DNS & TELNET<br>
    2. Transport layer protocols - TCP, UDP<br>
    3. Internet layer protocols - IPv4v6<br>
    4. Physical layer protocols - ETHERNET
    <br>
    <br>
    <br>
    <br>
    Name : V. Rakshita<br>
    Register no : 212224100049
</body>
</html>
'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',5000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
![alt text](<WEB EXP 1.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

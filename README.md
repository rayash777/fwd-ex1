# EX01 Developing a Simple Webserver
## Date:

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
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:

from http.server import HTTPServer, BaseHTTPRequestHandler

content = '''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
  <center><font color="blue" face="Times new roman" size="99">
        <b>Lists of protocols in TCP/IP Model</b>
        </font></center>
        <font color="red">
        <h2>Application Layer - HTTP, FTP, DNS, Telnet<br>
        Transport Layer - TCP & UDP<br>
        Network Type - IPV4/TPV6<br>
        Link Layer - Ethernet/h2>
        </font>
</body>
</html>'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',6600)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()





## OUTPUT:
<img width="1242" height="787" alt="Screenshot 2025-08-31 215053" src="https://github.com/user-attachments/assets/c1d2682f-4966-4cba-9289-6d00a1c681f0" />
<img width="944" height="357" alt="Screenshot 2025-08-31 215102" src="https://github.com/user-attachments/assets/7fbfebf6-e3c7-44fb-b3e0-ea86642cec73" />
<img width="1914" height="521" alt="Screenshot 2025-08-31 215200" src="https://github.com/user-attachments/assets/04ca5a96-8c75-4ec1-8dc2-cf93386aea47" />



## RESULT:
The program for implementing simple webserver is executed successfully.

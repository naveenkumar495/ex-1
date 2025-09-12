# EX01 Developing a Simple Webserver
## Date:1/09/2025

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
```
from http.server import HTTPServer,BaseHTTPRequestHandler
content="""
<html>
    <head>
        <title> My web server</title>
    </head>
    <body>
        <table border="1" align="center" cellpadding="10"bgcolor="yellow">
            <caption><center><h1>LIST OF PROTOCOLS IN TCP/IP PROTOCOL SUITE</h1></center></caption>
            <tr>
                <th>S.NO.</th><th>NAME OF THE LAYER</th><th>NAME OF THE PROTOCOL</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Application Layer</td>
                <td>HTTP,FTP,DNS,Telnet & SSH</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Transport Layer </td>
                <td>TCP & UDP</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Network Layer</td>
                <td>IPV4/IPV6</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Network Interface Layer</td>
                <td>Ethenet,Token ring,ATM </td>
            </tr>

        </table>
    </body>
</html>
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")

server_address=('',8000)
httpd=HTTPServer(server_address,Myserver)
httpd.serve_forever()

```
## OUTPUT:

![WhatsApp Image 2025-09-01 at 08 34 36_5c7c6b69](https://github.com/user-attachments/assets/249e6891-f13a-475c-b81b-b5b00d5c24fd)

![WhatsApp Image 2025-09-01 at 18 23 35_2c188a5d](https://github.com/user-attachments/assets/85b64185-8449-4f46-a67b-fab6473bc9fa)

## RESULT:
The program for implementing simple webserver is executed successfully.

# EX01 Developing a Simple Webserver
## Date: 18.04.25

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
content = """
<html>
    <head>
        <style>
            table{
                border-top: 15;
                border-bottom: 15;
                border-left: 15;
                border-right: 15;
                border-color: brown;
            }
            td{
                background-color: silver;
                font-size: medium;
            }
            th{
                background-color: gold;
                font-size: 20;
            }
        </style>
    </head>
    <body bgcolor="lightblue">
        <h1 style="color:darkgreen;text-align: center"></h1>
        <table align="center" border="10" cellpadding="15" cellspacing="0" width=700>
            <tr">
                <th style="color:blue">Layer</th>
                <th style="color:blue">Protocol</th>
            </tr>
            <tr>
                <td>Application Layer</td>
                <td>HTTP, HTTPS, FTP, SMTP, DNS</td>
            </tr>
            <tr>
                <td>Transport Layer</td>
                <td>TCP, UDP, SCTP</td>
            </tr>
            <tr>
                <td>Internet Layer</td>
                <td>IP (IPv4, IPv6), ICMP, ARP</td>
            </tr>
            <tr>
                <td>Network Access Layer</td>
                <td>Ethernet, Wi-Fi, MAC, PPP</td>
            </tr>
            </th>
        </table>
    </body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer(server_address, myhandler)
print("my webserver is running...")
httpd.serve_forever()



## OUTPUT:
![alt text](<Screenshot 2025-05-11 180431.png>)

![alt text](<Screenshot 2025-05-11 180517.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.

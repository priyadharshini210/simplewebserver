# EX01 Developing a Simple Webserver
## Date:15/03/2024

## AIM:
To develop a simple webserver to serve html pages.

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Software Companies</title>
</head>
<body bgcolor="silver">
<table border="9" cellspacing="10" cellpadding="10" height="150" width="300" align="center">
<caption> <h3>Top Five Revenue Generating Sotware Companies </h3></caption>
<tr>
<th>Rank</th>
<th>COMPANY</th>
<th>REVENUE</th>
</tr>
<tr>
<th>8</th>
<th>Apple</th>
<th>$389.7 B</th>
</tr>
</tr>
<tr>
<th>14</th>
<th>Micrsoft</th>
<th>$227.5 B</th>
</tr>
<tr>
<th>1</th>
<th>Walmart</th>
<th>$640.6 B</th>
</tr>
<tr>
<th>3</th>
<th>Amazon</th>
<th>$578.7 B</th>
</tr>
<tr>
<th>4/th>
<th>NVIDIA</th>
<th>$61.4 B</th>
</tr>
</table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:
![Screenshot (3)](https://github.com/priyadharshini210/simplewebserver/assets/148514638/ff4a4fac-e900-4057-99d1-be43159450aa)
![Screenshot (4)](https://github.com/priyadharshini210/simplewebserver/assets/148514638/6fd6f758-97fe-4e08-a5ab-04b6eb145ebd)


## RESULT:
The program for implementing simple webserver is executed successfully.

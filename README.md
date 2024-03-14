# EX01 Developing a Simple Webserver
## Date:14/03/2024

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
```C
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Software Companies</title>
</head>
<body bgcolor="pink">
<table border="9" cellspacing="10" cellpadding="10" height="150" width="300" align="center">
<caption> <h3>Top Five Revenue Generating Sotware Companies </h3></caption>
<tr>
<th>Company</th>
<th>Sales(USD)</th>
<th>Nationality</th>
</tr>
<tr>
<th>Microsoft</th>
<th>57.9</th>
<th>USA</th>
</tr>
<tr>
<th>Oracle</th>
<th>21.0</th>
<th>USA</th>
</tr>
<tr>
<th>SAP</th>
<th>16.1</th>
<th>Germany</th>
</tr>
<tr>
<th>Computer Associates</th>
<th>4.2</th>
<th>USA</th>
</tr>
<tr>
<th>Electronic Arts</th>
<th>3.2</th>
<th>USA</th>
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
```

## OUTPUT:
![Screenshot (4)](https://github.com/srinivasanvaiyali/simplewebserver/assets/145117665/caf91892-a709-40a6-89c6-f305817be143)
![3](https://github.com/srinivasanvaiyali/simplewebserver/assets/145117665/7bec2805-8241-4406-90ed-fc5107d6f11b)

## RESULT:
The program for implementing simple webserver is executed successfully.

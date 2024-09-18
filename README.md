# EX01 Developing a Simple Webserver
## Date:18/09/2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<title> Top Software Industry </title>
<body>
<table border ="2"  cellspacing ="10" cellpadding = "6" > 
<caption> TOP FIVE REVENUE GENERATING SOFTWARE COMPANIES </caption>
<tr>
<th> S.No </th>
<th> Company </th>
<th> Revenue </th>
</tr>

<tr>
<td> 1. </td>
<td> Microsoft </td>
<td> 65 Billion  </td>
</tr>

<tr>
<td> 2. </td>
<td> Oracle </td>
<td> 29.6 Billion  </td>
</tr>

<tr>
<td> 3. </td>
<td> IBM </td>
<td> 29.1 Billion  </td>
</tr> 

<tr>
<td> 4. </td>
<td> SAP </td> 
<td> 6.4 Billion </td>
</tr> 
 
<tr>
<td> 5. </td>
<td> Syamntec </td>
<td> 5.6 Billion </td>
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
![image1](https://github.com/user-attachments/assets/0ac06598-ba05-4161-b6dd-49cad882a95d)
![image2](https://github.com/user-attachments/assets/33471fa5-7945-40cc-a17f-d5ed98a2aff5)

## RESULT:
The program for implementing simple webserver is executed successfully

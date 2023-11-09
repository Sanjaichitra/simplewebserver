# EX01 Developing a Simple Webserver
## Date:6.10.2023

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
	<title> Revenue chart </title>
	<body>
		<table border="2" cellspacing="2" cellpadding="3">
			<caption> Top five highest revenue generating software companies </caption>
				<tr>
					<th> Serial Number </th>
					<th> Companies </th>
					<th> Revenue Generated </th>
				</tr>
				<tr>
					<th> 1 </th>
					<td> Microsoft </td>
					<td> $203.08 billion </td>
				</tr>
				<tr>
					<th> 2 </th>
					<td> Oracle </td>
					<td> $46.07 billion </td>
				</tr>
				<tr>
					<th> 3 </th>
					<td> SAP </td>
					<td> $32.97 billion </td>
				</tr>		
				<tr>
					<th> 4 </th>
					<td> Salesforce </td>
					<td> $30.29 billion </td>
				</tr>
				<tr>
					<th> 5 </th>
					<td> Adobe </td>
					<td> $17.61 billion </td>
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
![Screenshot 2023-11-03 205916](https://github.com/Sanjaichitra/simplewebserver/assets/144870518/6e229aac-e886-440b-9155-d724b274c417)

![Screenshot 2023-11-07 125047 (1)](https://github.com/Sanjaichitra/simplewebserver/assets/144870518/395f5805-97e9-4633-bff7-e8a7b162804f)


## RESULT:
The program for implementing simple webserver is executed successfully.

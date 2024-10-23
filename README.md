# EX01 Developing a Simple Webserver
## Date:23-10-2024

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content="""
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Configuration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color:gainsboro;
            margin: 0;
            padding: 0;
        }

        h1 {
            text-align: center;
            margin-top: 20px;
        }

        table {
            width: 70%;
            margin: 50px auto;
            border-collapse: collapse;
            background-color: #fff;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }

        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        th {
            background-color:gray;
            color: white;
        }

        tr:hover {
            background-color: #f1f1f1;
        }

        td {
            color: #333;
        }

        .highlight {
            background-color: #e0f7fa;
        }
    </style>
</head>
<body>

<h1>SHARON HARSHINI L M</h1>
<h1>212223040193</h1>
<h1>Laptop Configuration</h1>

<table>
    <tr>
        <th>Component</th>
        <th>Details</th>
    </tr>
    <tr>
        <td>Model</td>
        <td>Lenovo Thinkpad</td>
    </tr>
    <tr>
        <td>Processor</td>
        <td>12th Gen Intel(R) Core(TM) i5-1235U   1.30 GHz</td>
    </tr>
    <tr>
        <td>RAM</td>
        <td>16 GB DDR4</td>
    </tr>
    <tr>
        <td>Storage</td>
        <td>512 GB SSD</td>
    </tr>
    <tr>
        <td>Graphics</td>
        <td>Intel Iris XE</td>
    </tr>
    <tr>
        <td>Display</td>
        <td>15.6" 2K</td>
    </tr>
    <tr>
        <td>Battery</td>
        <td>86 Whr</td>
    </tr>
</table>

</body>
</html>
"""
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
![Screenshot 2024-10-23 120626](https://github.com/user-attachments/assets/2806f6f4-0b44-42d4-a57a-dae0caee43e2)
![Screenshot 2024-10-23 120734](https://github.com/user-attachments/assets/924590ae-4f0b-4f2f-a7fb-d4b5e1e8a809)


## RESULT:
The program for implementing simple webserver is executed successfully.

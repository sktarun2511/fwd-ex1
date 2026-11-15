# EX01 Developing a Simple Webserver
## Date: 14-11-2026
## REG NO: 26015012

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>TCP/IP Protocol Suite</title>
</head>
<body>

    <h1>TCP/IP Protocol Suite</h1>
    <p>The four layers of rules that move data across the internet, from your screen to physical cables.</p>

    <hr>

    <h2>1. Application Layer (User Apps)</h2>
    <ul>
        <li><strong>HTTP / HTTPS:</strong> Loads websites (HTTPS adds encryption).</li>
        <li><strong>DNS:</strong> Translates human domain names (<em>google.com</em>) into IP addresses.</li>
        <li><strong>SMTP:</strong> Sends outgoing emails.</li>
        <li><strong>IMAP / POP3:</strong> Receives emails (IMAP syncs across devices; POP3 downloads to one).</li>
        <li><strong>FTP / SFTP:</strong> Transfers files between computers and servers.</li>
        <li><strong>SSH:</strong> Securely controls remote servers via command line.</li>
        <li><strong>DHCP:</strong> Automatically assigns IP addresses when you join a network.</li>
    </ul>

    <h2>2. Transport Layer (Delivery Method)</h2>
    <ul>
        <li><strong>TCP:</strong> Reliable, ordered delivery with error-checking (web, email, files).</li>
        <li><strong>UDP:</strong> Fast, unverified delivery with no retries (gaming, live video, calls).</li>
    </ul>

    <h2>3. Internet Layer (Addressing &amp; Routing)</h2>
    <ul>
        <li><strong>IP (IPv4 / IPv6):</strong> Assigns logical addresses and routes packets globally.</li>
        <li><strong>ICMP:</strong> Sends network error messages and diagnostics (used by <code>ping</code>).</li>
        <li><strong>IGMP:</strong> Manages multicast groups for streaming to multiple receivers at once.</li>
    </ul>

    <h2>4. Network Access Layer (Physical Hardware)</h2>
    <ul>
        <li><strong>Ethernet (802.3):</strong> Moves data frames over wired cables.</li>
        <li><strong>Wi-Fi (802.11):</strong> Transmits data wirelessly over radio waves.</li>
        <li><strong>ARP:</strong> Maps IP addresses to physical hardware (MAC) addresses locally.</li>
        <li><strong>PPP:</strong> Creates direct point-to-point links between two nodes.</li>
    </ul>

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

~~~

## OUTPUT:
![alt text](<Screenshot 2026-11-14 162323.png>)
![alt text](<Screenshot 2026-11-14 162431.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.


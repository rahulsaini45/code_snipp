import xml.etree.ElementTree as ET

from http.server

import

HTTPServer, BaseHTTPRequestHandler

class SimpleHTTPRequestHandler (BaseHTTPRequestHandler):

def do POST(self): content_length = int(self.headers['Content-Length'])

post_data = self.rfile.read(content_length)

root = ET.fromstring (post_data) file_path = root.find('file').text

with open(file_path, 'r') as f:

file_content= f.read()

self.send_response(200)

self.end_headers()

self.wfile.write(file_content.encode())

httpd HTTPServer (('localhost', 8000),

SimpleHTTPRequestHandler)

httpd.serve forever()

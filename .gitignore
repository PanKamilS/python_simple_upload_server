
from http.server import HTTPServer, BaseHTTPRequestHandler
import os

class SimplePUTHandler(BaseHTTPRequestHandler):
    def do_PUT(self):
        filename = os.path.basename(self.path)
        if not filename:
            self.send_response(400)
            self.end_headers()
            self.wfile.write(b"No filename specified in the URL.")
            return
        
        content_length = int(self.headers['Content-Length'])
        file_data = self.rfile.read(content_length)
        
        with open(filename, "wb") as f:
            f.write(file_data)
        
        print(f"File '{filename}' has been uploaded via PUT and saved.")
        
        self.send_response(201)
        self.end_headers()
        self.wfile.write(b"File uploaded successfully.")

if __name__ == "__main__":
    address = input("Which address? Just leave blank for localhost: ")
    if not address:
        address = "0.0.0.0"

    port_input = input("Default port is 8080, type other or leave blank: ")
    port = 8080
    if port_input.strip().isdigit():
        port = int(port_input.strip())

    print(f"Starting server on {address}:{port}")
    httpd = HTTPServer((address, port), SimplePUTHandler)
    print(f"Server running at http://{address}:{port}/")
    httpd.serve_forever()

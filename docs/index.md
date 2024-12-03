
# Python Simple HTTP PUT Server Documentation

This is a simple HTTP server implemented in Python to handle file uploads via the HTTP `PUT` method.

## How to Run

1. Clone the repository.
2. Run the `put_server.py` script.
3. Configure the IP address and port.

## File Upload

Use the `PUT` method to upload files:
```bash
curl -T path_to_file http://<address>:<port>/<filename>
```

Uploaded files are saved in the working directory of the server.

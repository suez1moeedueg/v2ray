# v2ray
# PyV2Ray

PyV2Ray is a lightweight, Python-based implementation inspired by the V2Ray proxy server. This project serves as a basic example of how to create a proxy server with features similar to V2Ray, including user authentication and support for both HTTP and HTTPS traffic.

## Features

- Supports both HTTP and HTTPS connections
- User authentication using UUIDs
- Configuration via JSON file
- Multi-threaded design for handling multiple connections simultaneously
- Parses incoming requests to determine target host and port
- Establishes connections to target servers on behalf of clients
- Facilitates bidirectional communication between clients and servers

## How It Works

1. The proxy server reads configuration from a JSON file.
2. It listens for incoming connections on a specified host and port.
3. For each new connection, it performs user authentication.
4. If authentication is successful, a separate thread is spawned to handle the client.
5. The client's request is parsed to determine the target server and port.
6. A connection is established with the target server.
7. Two additional threads are created to handle bidirectional data flow between the client and the server.
8. For HTTPS connections, the socket is wrapped with SSL.

## Usage

1. Create a `config.json` file with the following structure:
   ```json
   {
     "server": "0.0.0.0",
     "port": 8388,
     "users": [
       "13b5e740-7af6-11eb-9439-0242ac130002",
       "23c6e741-7af6-11eb-9439-0242ac130003"
     ]
   }
 2-  Run the server:
Copypython pyv2ray.py

3-Configure your client with the server address and a UUID from the config.

Limitations
This implementation is a simplified version of V2Ray concepts. It lacks:

Advanced protocols (VMess, VLESS, etc.)
Robust error handling
Comprehensive logging
Production-level security measures
Performance optimizations

Note: This project is for educational purposes only. It is not suitable for production environments or as a substitute for the official V2Ray software.
Contributing
Contributions, issues, and feature requests are welcome. Feel free to check the issues page if you want to contribute.
License
MIT License


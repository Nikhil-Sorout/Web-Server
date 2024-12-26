# Proxy Server in C

## Overview

This project implements a simple HTTP proxy server in C that handles client requests by forwarding them to the appropriate remote servers and returning the responses back to the clients. The server supports multiple concurrent client connections using multithreading and employs a Least Recently Used (LRU) cache to store and retrieve frequently accessed data efficiently.

## Features

- **Multithreading**: Utilizes POSIX threads (`pthread`) to handle multiple client requests concurrently, improving server responsiveness and throughput.
- **LRU Cache**: Implements an LRU caching mechanism to store and retrieve frequently accessed data, reducing latency and network load.
- **Error Handling**: Provides appropriate HTTP error responses (e.g., 400 Bad Request, 404 Not Found) for invalid or unsupported requests.
- **Synchronization**: Employs semaphores and mutexes to manage access to shared resources, ensuring thread safety.

## Prerequisites

- **Operating System**: Unix-based systems (e.g., Linux, macOS)
- **Compiler**: GCC (GNU Compiler Collection)
- **Libraries**: POSIX threads (`pthread`), semaphores (`semaphore.h`), and standard C libraries

## Compilation and Execution

1. **Compile the Server**:
   ```bash
   gcc -o proxy_server proxy_server.c proxy_parse.c -lpthread
   ```
   This command compiles the `proxy_server.c` and `proxy_parse.c` files and links them with the pthread library.

2. **Run the Server**:
   ```bash
   ./proxy_server [port_number]
   ```
   Replace `[port_number]` with the desired port number (e.g., `8080`). If no port number is specified, the server defaults to port `8080`.

## Usage

1. **Start the Proxy Server**:
   Run the server using the command mentioned above. The server will start listening for incoming client connections.

2. **Configure Client**:
   Configure your web browser or HTTP client to use the proxy server by setting the proxy address to `localhost` and the port to the one specified during server startup.

3. **Send Requests**:
   Navigate to any website using your configured client. The proxy server will handle the requests, cache the responses, and forward them back to the client.

## Learnings from the Project

- **Socket Programming**: Gained experience in creating and managing sockets for network communication in C.
- **Multithreading**: Learned how to implement multithreading to handle multiple client requests concurrently, improving server performance.
- **Caching Mechanisms**: Implemented an LRU cache to efficiently manage frequently accessed data, reducing latency and network load.
- **Synchronization**: Utilized semaphores and mutexes to ensure thread safety when accessing shared resources.
- **Error Handling**: Developed robust error handling to manage various HTTP error responses appropriately.

## Acknowledgments

Special thanks to the resources and tutorials that aided in the development of this project.

Feel free to open issues or submit pull requests if you find any bugs or have suggestions for improvements.

For more detailed information and advanced configurations, refer to the Multithreaded Proxy Web Server in C repository [https://github.com/Lovepreet-Singh-LPSK/MultiThreadedProxyServerClient/tree/main].
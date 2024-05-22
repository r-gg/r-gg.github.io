---
layout: page
title: http
description: C implementation of RFC-7230 compliant HTTP client and server
img: assets/img/http/client_server.jpg
# redirect: https://unsplash.com
importance: 3
category: software development
---

<span class="lead"><span class="badge badge-pill badge-primary">C</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">TCP/IP Sockets</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Client-Server</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">HTTP</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Binary Data</span></span>

<span class="lead"><span class="badge badge-pill badge-secondary">Development Period: 12.2020</span></span>


> Code available in [GitHub repository](https://github.com/r-gg/http).

# HTTP client and server

- Implementation Language : **C**
- Supported filetypes:
  - Plaintext
  - Binary
- Compression of the transferred content possible
- Tool used:
  - TCP/IP Sockets
  
## Client

The client takes an URL as input, connects to the corresponding server and requests the file specified in the URL. The transmitted content of that file is written to stdout or to a file.

Usage:

![image](https://github.com/r-gg/http/assets/90387385/c432e200-1934-49f0-954c-a6f30bb118ec)

## Server

The server waits for connections from clients and transmits the requested files.

Usage:

![image](https://github.com/r-gg/http/assets/90387385/a6d5fb89-1646-4aa9-840c-c16e2a714a00)


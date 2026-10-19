# Fundamentals of the Web

Below is a comprehensive set of notes on the fundamentals of the web. It draws from the reference book *HTML & CSS: Design and Build Websites* by Jon Duckett (pages cited where relevant) and expands on the many topics you listed that the book does not cover. The goal is to give you a solid foundation before you dive deeper into HTML, CSS, and web development.

---

## 1. The Internet vs. the World Wide Web

**The Internet** is a global system of interconnected computer networks that use the Internet Protocol Suite (TCP/IP) to communicate. It is the physical and logical infrastructure—cables, routers, switches, satellites, protocols—that allows data to travel between devices.

**The World Wide Web (WWW)** is an information system built *on top of* the Internet. It uses HTTP/HTTPS to access documents (web pages) linked by hyperlinks. The Web is just one of many services that run on the Internet (others include email, FTP, VoIP, online gaming, etc.).

> The book introduces the web on pages 9–10, explaining how browsers, web servers, and DNS work together to deliver web pages. It does not explicitly contrast the Internet vs. the Web, but this distinction is fundamental.

---

## 2. Network Fundamentals

### 2.1 IP Addresses

Every device connected to the Internet has a unique **IP address**—a numerical label used for identification and location addressing.

- **IPv4**: 32-bit address, written as four octets (0–255) separated by dots, e.g., `192.168.1.1`. It allows ~4.3 billion unique addresses.
- **IPv6**: 128-bit address, written as eight groups of four hexadecimal digits, e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`. It allows a vastly larger number of addresses.
- **Public vs. Private IPs**: Private IPs (e.g., `192.168.x.x`, `10.x.x.x`) are used within local networks; public IPs are routable on the Internet.
- **Static vs. Dynamic**: Static IPs don’t change; dynamic IPs are assigned by DHCP and can change.

> The book mentions IP addresses on page 10: “An IP address is a number of up to 12 digits separated by periods / full stops. Every device connected to the web has a unique IP address.”

### 2.2 Ports and Sockets

- **Port**: A 16-bit number (0–65535) that identifies a specific process or service on a device. It allows multiple services to run on the same IP address.
  - Well-known ports: HTTP (80), HTTPS (443), FTP (21), SSH (22), SMTP (25), DNS (53).
  - Registered ports: 1024–49151 (e.g., MySQL 3306).
  - Dynamic/private ports: 49152–65535 (used for temporary client connections).
- **Socket**: An endpoint for communication, defined by an IP address and a port number, e.g., `192.168.1.10:80`. A connection is identified by a pair of sockets (client IP:port + server IP:port).

### 2.3 TCP vs. UDP

Both are transport-layer protocols.

| Feature | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
| --------- | -------------------------------------- | ------------------------------- |
| Connection | Connection-oriented (3-way handshake) | Connectionless |
| Reliability | Reliable: guarantees delivery, ordering, and error checking | Unreliable: no guarantee of delivery or order |
| Speed | Slower due to overhead | Faster, lower latency |
| Use cases | Web (HTTP/HTTPS), email, file transfer | Streaming, VoIP, online gaming, DNS |

**TCP 3-way handshake**:

1. Client → Server: SYN
2. Server → Client: SYN-ACK
3. Client → Server: ACK  
Then data transfer begins.

### 2.4 Packets, Routers, and Switches

- **Packet**: A small unit of data transmitted over a network. Large messages are broken into packets, each containing a header (source/destination IP, port, sequence number) and payload.
- **Router**: A device that forwards packets between different networks (e.g., between your home network and the Internet). It uses IP addresses to determine the best path.
- **Switch**: A device that connects devices within the same local network (LAN) and forwards frames based on MAC addresses. It operates at the data link layer (Layer 2).

Data travels through multiple routers (hops) before reaching its destination.

---

## 3. The Domain Name System (DNS)

DNS is the phonebook of the Internet. It translates human-friendly domain names (e.g., `www.example.com`) into IP addresses.

> The book explains DNS on pages 9–10: “Your computer contacts a network of servers called Domain Name System (DNS) servers. These act like phone books; they tell your computer the IP address associated with the requested domain name.”

### 3.1 DNS Resolution Lifecycle

When you type a URL into your browser:

1. **Browser cache check**: The browser checks its own DNS cache.
2. **OS cache check**: The operating system checks its DNS cache and hosts file.
3. **Recursive resolver**: The ISP’s DNS resolver (or a public resolver like 8.8.8.8) is queried.
4. **Root nameserver**: The resolver asks a root server, which directs it to the appropriate TLD (Top-Level Domain) nameserver (e.g., `.com`).
5. **TLD nameserver**: The TLD server directs the resolver to the authoritative nameserver for the domain.
6. **Authoritative nameserver**: This server holds the actual DNS records and returns the IP address.
7. **Response**: The resolver caches the answer (based on TTL) and returns it to the browser, which then connects to the IP.

### 3.2 DNS Record Types

- **A**: Maps a domain to an IPv4 address.
- **AAAA**: Maps a domain to an IPv6 address.
- **CNAME** (Canonical Name): Alias for another domain name.
- **MX** (Mail Exchange): Specifies mail servers for the domain.
- **TXT**: Text records (used for verification, SPF, DKIM, etc.).
- **NS** (Name Server): Specifies the authoritative nameservers for the domain.
- **SOA** (Start of Authority): Contains administrative information about the zone.
- **SRV**: Service locator records.
- **PTR**: Reverse DNS lookup (IP → domain).

### 3.3 Domain Registrars and Nameservers

- **Domain Registrar**: A company accredited to register domain names (e.g., GoDaddy, Namecheap, Google Domains). You pay an annual fee to keep the domain.
- **Nameservers**: Servers that host DNS records for your domain. When you register a domain, you specify which nameservers are authoritative (usually provided by your hosting company or a DNS service like Cloudflare).

### 3.4 DNS Propagation and Caching

- **Propagation**: When DNS records change, it takes time for the new records to propagate across the Internet because of caching at various levels. This can take from minutes to 48 hours, depending on TTL.
- **TTL (Time To Live)**: A value in DNS records that tells resolvers how long to cache the record (in seconds). A lower TTL means faster propagation but more DNS queries.

---

## 4. The Client-Server Model

### 4.1 Clients and Servers

- **Client**: A device or software that requests resources (e.g., a web browser, a mobile app).
- **Server**: A computer or software that provides resources or services to clients (e.g., a web server like Apache or Nginx).

The client-server model is a distributed application architecture that partitions tasks between providers (servers) and requesters (clients).

> The book describes web servers on page 7: “Web servers are special computers that are constantly connected to the Internet, and are optimized to send web pages out to people who request them.”

### 4.2 Request-Response Cycle

1. Client sends an HTTP request to the server (via a URL).
2. Server processes the request (may query a database, run server-side code).
3. Server sends an HTTP response back to the client.
4. Client renders the response (e.g., browser displays HTML, executes JavaScript).

---

## 5. HTTP (HyperText Transfer Protocol)

HTTP is the foundation of data communication on the Web. It is a request-response protocol.

### 5.1 HTTP Methods

- **GET**: Retrieve a resource. Should be safe and idempotent. Parameters in URL.
- **POST**: Submit data to be processed (e.g., form submission). Not idempotent.
- **PUT**: Update a resource (replace). Idempotent.
- **PATCH**: Partially modify a resource.
- **DELETE**: Remove a resource. Idempotent.
- **HEAD**: Same as GET but returns only headers (no body).
- **OPTIONS**: Returns supported HTTP methods for a resource (used in CORS preflight).
- **TRACE**: Echoes the received request (for debugging).
- **CONNECT**: Establishes a tunnel (used for HTTPS through proxies).

> The book covers form methods `get` and `post` on page 151.

### 5.2 HTTP Status Codes

Grouped by class:

- **1xx (Informational)**: 100 Continue, 101 Switching Protocols.
- **2xx (Success)**: 200 OK, 201 Created, 204 No Content.
- **3xx (Redirection)**: 301 Moved Permanently, 302 Found, 304 Not Modified, 307 Temporary Redirect, 308 Permanent Redirect.
- **4xx (Client Error)**: 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 405 Method Not Allowed, 429 Too Many Requests.
- **5xx (Server Error)**: 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable, 504 Gateway Timeout.

### 5.3 HTTP Headers

Headers carry metadata in requests and responses.

**Common request headers**:

- `Host`: The domain being requested.
- `User-Agent`: Info about the client.
- `Accept`: Media types the client can handle.
- `Accept-Language`: Preferred languages.
- `Cookie`: Sends cookies to the server.
- `Authorization`: Credentials for authentication.
- `Referer`: The URL of the previous page.

**Common response headers**:

- `Content-Type`: Media type of the response (e.g., `text/html`, `application/json`).
- `Content-Length`: Size of the response body.
- `Set-Cookie`: Sends a cookie to the client.
- `Cache-Control`: Caching directives.
- `ETag`: Identifier for a specific version of a resource.
- `Location`: Used with redirects.
- `Access-Control-Allow-Origin`: CORS header.

### 5.4 Statelessness and State Management

HTTP is **stateless**: each request is independent and the server does not retain state between requests.

To manage state, several techniques are used:

- **Cookies**: Small pieces of data stored on the client and sent with every request.
- **Sessions**: Server-side storage of user data, identified by a session ID (usually stored in a cookie).
- **Tokens (e.g., JWT)**: Self-contained tokens that store state on the client.
- **LocalStorage/SessionStorage**: Client-side storage (not automatically sent to server).

### 5.5 HTTPS and TLS/SSL

**HTTPS** is HTTP over TLS (Transport Layer Security). It encrypts communication between client and server, ensuring confidentiality, integrity, and authentication.

- **TLS handshake**: Establishes a secure connection using asymmetric cryptography (public/private keys) to exchange a symmetric session key.
- **Certificates**: Issued by Certificate Authorities (CAs) to verify the server’s identity.
- **SSL** is the predecessor to TLS (SSL 3.0 was deprecated).

> The book notes on page 153: “For full security, the server needs to be set up to communicate with users' browsers using Secure Sockets Layer (SSL).” (Modern equivalent is TLS.)

### 5.6 HTTP Evolution

- **HTTP/1.0 (1996)**: Each request required a new TCP connection. No persistent connections, no pipelining.
- **HTTP/1.1 (1997)**: Persistent connections (keep-alive), pipelining (rarely used), chunked transfer encoding, additional caching headers. Still suffers from head-of-line blocking.
- **HTTP/2 (2015)**: Binary protocol, multiplexing (multiple requests over a single connection), header compression (HPACK), server push. Eliminates head-of-line blocking at the HTTP level.
- **HTTP/3 (2022)**: Uses QUIC (built on UDP) instead of TCP, reduces connection establishment latency, improves multiplexing, and handles packet loss better.

---

## 6. Browser Architecture and Rendering

### 6.1 Browser Architecture

A modern browser consists of several components:

- **User Interface**: Address bar, bookmarks, back/forward buttons, etc.
- **Browser Engine**: Coordinates between UI and rendering engine.
- **Rendering Engine**: Displays content (e.g., Blink in Chrome, Gecko in Firefox, WebKit in Safari).
- **Networking**: Handles HTTP requests.
- **JavaScript Engine**: Executes JavaScript (e.g., V8 in Chrome, SpiderMonkey in Firefox).
- **UI Backend**: Draws basic widgets.
- **Data Storage**: Cookies, localStorage, IndexedDB, cache.

### 6.2 The Rendering Pipeline

When a browser receives HTML:

1. **Parsing HTML** → DOM (Document Object Model) tree.
2. **Parsing CSS** → CSSOM (CSS Object Model) tree.
3. **Style Calculation**: Combine DOM and CSSOM to determine computed styles for each element.
4. **Layout (Reflow)**: Calculate the position and size of each element.
5. **Paint**: Fill in pixels (colors, images, borders, etc.).
6. **Composite**: Combine layers into the final screen image.

Modern browsers use GPU acceleration and layer compositing.

### 6.3 Parsing and Execution Blocking

- **CSS is render-blocking**: The browser won’t render until CSSOM is ready (to avoid FOUC).
- **JavaScript is parser-blocking**: When the browser encounters a `<script>` tag, it pauses HTML parsing to download and execute the script (unless `async` or `defer` is used).
  - `async`: Download in parallel, execute as soon as downloaded (order not guaranteed).
  - `defer`: Download in parallel, execute after HTML parsing is complete (order preserved).

### 6.4 Browser DevTools

Built-in tools (F12 or right-click → Inspect) allow you to:

- Inspect and modify HTML/CSS live.
- Debug JavaScript.
- Monitor network requests (headers, timing, status).
- Analyze performance (rendering, painting, memory).
- Check storage (cookies, localStorage, sessionStorage).
- Run audits (Lighthouse).

---

## 7. Web Security

### 7.1 Same-Origin Policy (SOP)

A critical security concept: scripts from one origin (scheme + host + port) cannot access resources from a different origin. For example, JavaScript on `https://example.com` cannot read data from `https://api.other.com` unless allowed.

### 7.2 Cross-Origin Resource Sharing (CORS)

CORS is a mechanism that allows servers to specify which origins are permitted to access their resources. It uses HTTP headers like `Access-Control-Allow-Origin`. For non-simple requests, the browser sends a **preflight** `OPTIONS` request.

### 7.3 Mixed Content

When an HTTPS page loads resources (images, scripts, styles) over HTTP, it’s called mixed content. Modern browsers block or warn about mixed content because it compromises security.

### 7.4 Secure Cookies

Cookies can be marked with attributes:

- `Secure`: Only sent over HTTPS.
- `HttpOnly`: Not accessible via JavaScript (prevents XSS theft).
- `SameSite`: Controls when cookies are sent with cross-site requests (`Strict`, `Lax`, `None`).

---

## 8. Hosting and Delivery

### 8.1 Web Hosting Types

- **Shared Hosting**: Multiple websites on one server. Cheap but limited resources.
- **VPS (Virtual Private Server)**: Virtualized server with dedicated resources.
- **Dedicated Hosting**: Entire physical server dedicated to one site.
- **Cloud Hosting**: Scalable resources across multiple servers (e.g., AWS, Azure, GCP).
- **Managed WordPress Hosting**: Specialized for WordPress.
- **Static Hosting**: For static sites (e.g., Netlify, Vercel, GitHub Pages).

### 8.2 Content Delivery Networks (CDNs)

A CDN is a network of geographically distributed servers that deliver content (especially static assets) from the closest location to the user. Benefits:

- Reduced latency.
- Increased bandwidth.
- DDoS mitigation.
- Caching.

### 8.3 Browser Caching and Expiration

Browsers cache resources to avoid re-downloading them. Caching is controlled by headers:

- `Cache-Control`: Directives like `max-age`, `no-cache`, `no-store`, `public`, `private`.
- `Expires`: Old HTTP/1.0 header specifying an absolute expiration date.
- `ETag` and `If-None-Match`: Validate cached resources.
- `Last-Modified` and `If-Modified-Since`: Alternative validation.

When a user revisits a page, the browser may serve cached resources (if fresh) or revalidate with the server (304 Not Modified).

> The book mentions caching briefly on page 192 (meta `pragma` and `expires`), but modern caching relies on HTTP headers.

---

## Summary

This covers the essential fundamentals of the web: from the physical network (IP, TCP/UDP, packets, routers) to DNS, client-server architecture, HTTP/HTTPS, browser rendering, security, and hosting. The reference book provides a solid introduction to how browsers, servers, and DNS work, but it is primarily focused on HTML and CSS. The additional topics here will give you a well-rounded understanding as you continue your web development journey.

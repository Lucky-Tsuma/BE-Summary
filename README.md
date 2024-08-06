## BE-Summary

Backend developer road map [guide here](https://roadmap.sh/backend)

### 1) HOW THE INTERNET WORKS

**Internet:** global network of computers connected to each other which communicate through a standardized set of protocols. Developed in the late 1960s by the United States Department of Defense as a means of creating a decentralized communication network that could withstand a nuclear attack.

When you send data over the internet, it is broken up into small _packets_ that are sent from your device to a router. The router examines the packet and forwards it to the next router in the path towards its destination.
To ensure that packets are sent and received correctly, the internet uses a variety of protocols e.g:

1.  **Internet Protocol (IP):** responsible for routing packets to their _correct destination_
2.  **Transmission Control Protocol (TCP):** ensures that packets are transmitted _reliably and in the correct order._

Other technologies and protocols used to enable communication and data exchange over the internet:

-   Domain Name System (DNS)
-   Hypertext Transfer Protocol (HTTP)
-   Secure Sockets Layer/Transport Layer Security (SSL/TLS) protocol.

#### Terminologies

-   _Packet:_ A small unit of data that is transmitted over the internet.
-   _Router:_ A ddevice that directs packets between different netorks.
-   _IP Address:_ A unique identifier for each device on a network, used to route data to the correct destination.
-   _Domain Name:_ Human-readable name used to identify a website. Example: google.com.
-   _DNS:_ Domain Name System. For translating domain names into IP addresses.
-   _HTTP:_ Hypertext Transfer Protocol. Used to transfer data between a client ( e.g web browser) and a server (e.g website).
-   _HTTPS:_ An encrypted version of HTTP.
-   _SSL/TLS:_ The Secure Sockets Layer and Transport Layer Security protocols are used to provide secure communication over the internet.

#### The role of protocols in internet

**Protocol**: A set of rules and standards that define how information is exchanged between devices and systems.

-   **IP** is responsible for _routing packets of data to their correct destination._
-   **TCP** and **UDP** ensure that _packets are transmitted reliably and efficiently._
-   **DNS** is used to _translate domain names into IP addresses._
-   **HTTP** is used to _transfer data between clients and servers._

    Using standardized protocols allow devices and systems from different manufacturers and vendors to communicate with each other seamlessly.

#### IP Addresses and Domain Names

IP addresses are typically represented as a series of four numbers separated by periods, such as “192.168.1.1”.
Domain names are human-readable names used to identify websites and other internet resources.

When you enter a domain name into your web browser, your computer sends a DNS query to a DNS server, which returns the corresponding IP address.
The IP address is then used to connect to the website or other resource you’ve requested.

#### HTTP and HTTPS

HTTP (Hypertext Transfer Protocol)
HTTPS (HTTP Secure)

When you visit a website, your web browser sends an HTTP request to the server, asking for the webpage or other resource you’ve requested. The server then sends an HTTP response back to the client, containing the requested data.

HTTPS encrypts the data being transmitted between the client and server using SSL/TLS (Secure Sockets Layer/Transport Layer Security) encryption.

#### Building applications with TCP/IP

Few key concepts to understand when building applicaitons with TCP/IP:

-   Ports: used to identify the application/service running on a device. Each application/service is assigned a unique port number, allowing data to be sent to the correct destination.
-   Sockets: a combination of an IP address and a port number, representing a specific endpoint for communication. Used to establish connections between devices and transfer data between applications. Each language has its own way of representing sockets.
-   Connections: established between two sockets when two devices want to communicate with each other. During the process, the devices negotiate various parameters e.g the maximum segment size and window size, which determine how data will be transmitted over the connection.
-   Data transfer: happens between applications running on each device once a connection is established. Data is transmitted in segments, with each segment containing a sequence number and other metadata to ensure reliable delivery.

#### Securing Internet Communication with SSL/TLS

SSL/TLS is used to encrypt data being transmitted over the internet. Used to provide secure connections for applications such as web browsers, email clients, and file transfer programs.

Key concepts to understand while using SSL/TLS:

-   Certificates: SSL/TLS certificates are _used to establish trust_ between the client and server. Contain _information about the identity of the server._ Signed by a trusted third party (a Certificate Authority) to verify their authenticity. Trust in a certificate relies in the trust of the CA that issued it. Browsers and OS(s) typically come pre-installed with a list of trusted CAs. Examples of CAs: Digicert, Comodo, GlobalSign, Thawte, Let's Encrypt (free).
-   Handshake: During the SSL/TLS handshake process, the client and server _exchange information to negotiate the encryption algorithm and other parameters for the secure connection._
-   Encryption: Once the secure connection is established, data is encrypted using the agreed-upon algorithm and can be transmitted securely between the client and server.

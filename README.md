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

-   _Packet:_ A small unit of data that is transmitted over the internet. A packet has two parts, the **header** contains information that helps the packet get to its destination, including the length of the packet, its source and destination, and a checksum value that helps the recipient detect if a packet was damaged in transit. After the header comes the **actual data.**
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

#### Emerging trends and technology

-   _5G:_ latest generation of mobile network technology, offering faster speeds, lower latency, and greater capacity than previous generations.
-   _Internet of Things (IoT):_ network of physical devices, vehicles, home appliances, and other objects that are connected to the internet and can exchange data.
-   _Artificial Intelligence (AI):_ technologies such as machine learning and natural language processing.
-   _Blockchain:_ distributed ledger technology that enables secure, decentralized transactions.
-   _Edge computing:_ refers to the processing and storage of data at the edge of the network, rather than in centralized data centers.

#### Types of domain names

1. **generic top-level domains (gTLDs):** such as .com, .edu, .org, and .gov. Authority over these domains is usually delegated to private organizations.
2. **country-code top-level domains (ccTLDs):** Each country in the world has its own 2-letter code. For example, the ccTLD for the United States is .us, Great Britain’s is .uk, and China’s is .cn. These domains are administered by authorities in each country.

### 2) DOCKER

[Youtube tutorial here](https://www.youtube.com/watch?v=3c-iBn73dDE)

-   **Docker:** A platform to build, run and ship applications.
-   **Container:** An isolated environment for running an application.

#### Difference between a docker conainer and a virtual machine

A _virtual machine_ is an abstraction of a physical machine, thus needs a full blown OS. It needs a hypervisor to run e.g Virtualbox, Virtual-Machine, Hyper-v (for windows only). It virtualizes both the application layer and the kernel of an OS. It boots up its own kernel.

A _container_ on the other hand is just a way to package an application with all necessary dependencies and configurations. It virtualizes only the application layer of an OS. It uses the kernel of the host OS.

Thus: 
- A docker image is much smaller that a virtual machine 
- Docker containers are much faster than a virtual machine 
- You can run the VM of any OS on any OS host. You cannot do that with a docker image however. e.g a linux docker image will be incompatible with the windows kernel (win 10 and below especially). The way around this is to install _docker toolbox_, making it possible for your host to run different docker images.

#### Difference between docker image and docker container

-   **Docker image:** The actual package (configs, apps etc). The artifact that can be moved around. Images, like repositories are stored on [Docker Hub](https://hub.docker.com/)
-   **Docker container:** When you pull an image to your local machine and start it. A container is a running environment for an image. Say, a docker image has postgresql, mongo and redis, it will need things such as:
    -   Filesystem: container provides a virtual filesystem
    -   Port binding: containers are port binded, making it possible to talk to applications running inside the container.
    -   By default, there is no data persistence between container restarts.

#### Docker installation

[Installation guide for ubuntu and ubuntu based distros](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

-   **Docker Engine:** Necessary to run docker containers.
-   **Docker CLI client:** Enables one to execute docker commands
-   **Docker compose:** Used for orchestration if you have multiple containers
-   **Docker toolbox:** for environmemts that do not allow running docker natively.

#### Basic docker commands

-   **docker ps:** list running containers
-   **docker images:** show available images
-   **docker run <image_name>:** starts a container for an image. Pulls the image from dockerhub if not available locally
-   **docker run -d <image_name>:** starts a container in detach mode. Container runs in the background leaving the terminal free fpr other tasks. Retuns the container id.
-   **docker stop <container_id>:** stops a docker container
-   **docker start <container_id>:** starts a docker container
-   **docker ps -a:** shows all containers. Those that are running and those that are not
-   **docker pull:** pulls docker image from repository to local

#### Container port vs host port

-   You could for instance have multiple containers of the same application running on the same host e.g different versions of redis. Normally, they will listen on the same port (see when you run `docker ps`), but, take note that this is the container port.
-   Your host machine has some ports available as well that you could open for some applications.
-   You need to create _binding_ between your container port and host machine's port.
-   On the redis example, you could bind the different versions to different ports on the host machine.
-   Use this command for port binding:
    `docker run -p<host_port>:<container_port> <image_name>`
-   In detach mode:
    `docker run -d -p<host_port>:<container_port> <image_name>`

#### Debugging Containers

-   To view the logs of a running container: <br>
    `docker logs <container_id>` or `docker logs <container_name>`
-   To give a container a custom name during runtime:<br>
    `docker run -d -p<host_port>:<container_port> --name <custom_name> <image_name>`
-   To access the terminal of a running container:<br>
    `docker exec -it <container_id> /bin/bash` or `docker exec -it <container_name> /bin/bash`

#### Docker network
Dcoker containers running in the same network do not need additional information to communicate within themselves
-   List docker networks: ```docker network ls```
-   Create a docker network: ```docker network create <network_name>```

#### Docker compose
-   This is a tool for running multiple docker containers. It is a structured way of containing normal/common docker commands.
-   It takes care of creating a common network for the containers (containers in the same compose file)
-   A docker compose file has a *.yaml* extension.
-   To start containers using docker compose, run this command: ```docker-compose -f <docker_filename.yaml> up```
-   To stop containers using docker compose, run this command: ```docker-compose -f <docker_filename.yaml> down```

Below is example of a docker-compose file:
```
# Specify the version of the Docker Compose file format.
version: '3'

# Define the services (containers) that will be managed by Docker Compose.
services:
  # Define the "mongodb" service.
  mongodb:
    # Specify the Docker image to use for this service.
    image: mongo

    # Map the host's port 27017 to the container's port 27017.
    # This allows external applications to connect to the MongoDB database.
    ports:
      - 27017:27017

    # Define environment variables for the MongoDB container.
    environment:
      MONGO_INITDB_ROOT_USERNAME: admin  # Set the MongoDB root username.
      MONGO_INITDB_ROOT_PASSWORD: password  # Set the MongoDB root password.

  # Define the "mongo-express" service.
  mongo-express:
    # Specify the Docker image to use for this service.
    image: mongo-express

    # Always restart the container if it stops or crashes.
    restart: always

    # Map the host's port 8081 to the container's port 8081.
    # This allows accessing the Mongo Express web interface from a browser.
    ports:
      - 8081:8081

    # Define environment variables for the Mongo Express container.
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: admin  # Use the admin username set for MongoDB.
      ME_CONFIG_MONGODB_ADMINPASSWORD: password  # Use the admin password set for MongoDB.
      ME_CONFIG_MONGODB_SERVER: mongodb  # Specify the MongoDB server (name of the "mongodb" service).
```

This file sets up two containers `mongodb` and `mongo-express`. They work together, with `mongo-express` configured to connect to the `mongodb` service

#### Dockerfile
-   A dockerfile is a blueprint for buildiing docker images.
-   This means every single docker image has its own docker file.
-   A dockerfile is a simple text file and is usually named as `Dockerfile`. It cannot be named any other way.
-   Every docker image is based on another image hence the command `FROM` on every docker file.
-   Below is an example of a `Dockerfile`
```
# Use an official Python runtime as the base image
FROM python:3.11-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements file to the working directory
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code into the container
COPY . .

# Expose a port to allow communication with the container
EXPOSE 8000

# Set the command to run the application
CMD ["python", "app.py"]
```

A line by line explanation of the above file:
1.  **FROM python:3.11-slim:** Specifies the base image to use for the container.
2.  **WORKDIR /app:** Sets /app as the working directory inside the container. All subsequent commands will be executed relative to this directory.
3.  **COPY requirements.txt .:** Copies the requirements.txt file from your local machine into the working directory inside the container.
4.  **RUN pip install --no-cache-dir -r requirements.txt:** Installs the dependencies listed in requirements.txt. The --no-cache-dir flag prevents caching, reducing image size.
5.  **COPY . .:** Copies the rest of the application code from your local machine into the container.
6.  **EXPOSE 8000:** Informs Docker that the application listens on port 8000. This doesn't publish the port but serves as documentation.
7.  **CMD ["python", "app.py"]:** Specifies the default command to run when the container starts. This runs the app.py file using Python.

#### Build docker image from Dockerfile
Once we have created the Dockerfile, the next step is to build a docker image from it. This can be done using the command below:
-   `docker build -t <image_name>:<image_tag> <path_to_Dockerfile>` *Example* `docker build -t my-app:1.0 .`

-   Whenever you make any changes to the `Dockerfile`, you need to rebuild the image. Stop the container, delete it (`docker rm <container_id>`), then delete the image (`docker rmi <image_id>`)

#### Docker Volumes

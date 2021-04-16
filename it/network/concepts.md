# Network Concepts

## DNS

- domain name system
- domain name to IP address translation
- TTL
	- time to live
	- time for which a caching nameservers caches DNS record
	- after TTL is expired, the nameserver queries the authoritative nameserver

## TLS

- certificate
- at least one of following
  - private connection (handshake, symmetric cryptography)
  - authentication by public-key-cryptography
  - reliable connection: checksum (message integrity)

## Transfer protocols

### FTP

- client-server architecture (FTP Server)
- separate control and data connection between client and server
- clear text authentication / anonymous
- does not encrypt contect
- active & passive mode
- server:
  - port 21: FTP server command port
  - port 20: FTP server data port
- client: TCP control connection from random (unprivileged) port
  - active: sends PORT M to server where it listens, then server initiates
  - passive: send a PASV, server sends IP:port, client opens a connection from an arbitrary port
- vsftpd: FTP server for Unix-like systems

### FTPS

- FTP over SSL
- support for TLS and SSL(prohibited)

### SFTP

- not compatible with FTPS
- SSH FTP
- ~remote file system protocol (file access, file transfer, file management(mv, cp, rm...))
- SFTP server: usually provided by an SSH server implementation
- shares port 22 with SSH
- extension of SSH
- clients
  - [FileZilla](https://filezilla-project.org/): linux, mac, windows, has also servers
  - [WinSCP](https://winscp.net/eng/download.php): windows only

### SCP

- Secure Copy Protocol
- only allows file transfer
- based on SSH
- Since 2019 April: outdated
- modern protocols: sftp, rsync

### HTTP

- Hypertext Transfer Protocol
- request (client to server)
  - verb
  - headers
  - content
- response (server to client)
  - status code
  - headers
  - content
- each connection is short lived
- the server is stateless

#### Verb

- action to perform
- GET: request resource
- POST: create resource
- PUT: update resource
- PATCH: update partial resource
- DELETE: delete resource

#### Header

- metadata about the request
- e.g.
  - Content Type
  - Content Length
  - Authorization
  - Accept
  - Cookies
  - Expires

#### Content

- content concerning request
- not for GET
- HTML, CSS, JavaScript, XML, JSON

#### Status Code

- 100-199: informational
- 200-299: success
- 300-399: redirection to different sides
- 400-499: client errors
- 500-599: server errors

## Server

### File server

- no logic, just disk drives
- runs NFS or other network file system
- for storage

### Web server

- a program that uses HTTP to server files in response to client requests
- can run ftp, ssh...
- examples
  - Apache
  - nginx

### Mail server

- deliver mails (~ postman)

## Tools

### Curl

```bash
# get body
curl arest.me

# get headers and response except for the body
curl arest.me -I

# get entire response
curl arest.me -i
```
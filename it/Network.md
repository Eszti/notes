# Network

## Concepts

### DNS

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

## Security

### Proxy

- intermediary between client and server, potentially masking the true orgin of the request
- types
  - open proxy (forwarding proxy
    - forwards requests
    - on behalf of the clients
  - reverse proxy
    - resources returned to the client appear as if they originated from the proxy
    - on behalf of the servers

### CIA Triad

- confidentiality
  - information is not made available for unauthorized
  - hacker reads sensible information
  - two-factor auth...
- integrity
  - accuracy & completeness = maintain the consistency
  - hacker/software bug/human error changes information
  - authentication, hash checks, redundancy
- availability
  - being accessible & usable on demand
  - DoS (denial-of-service) attack
  - intrusion detection, firewalls

### Crypto

- encoding
  - not really cryptographgy
  - Base64
    - transform all kinds of bytes to a specific range (ASCII readable)
    - reversible
    - transform each 6 bit to a byte (8 bits) -> 33% increase
    - Basic Authentication uses Base64 encoding
  - HTML
    - space is not allowed in URL -> %20
- hashing
  - for detecting if the original data has been changed
  - if the orginal data changes - hash changes
  - irreversible
  - not recommended: MD5, SHA-1 (changed payload can still generate the same password)
  - salted hashes
    - pw + unique, randomly generated string -> hash
    - not possible to determine identical passwords
    - modern hashing algos have it by default (Argon2, Bcrypt)
    - store salt & pw hash
- encryption
  - symmetric
    - shared secret used both for encryption & decryption
    - AES, 3DES
  - asymmetric
    - key pairs (private & public)
    - private: secret
    - public: freely accessible
    - encrypted with private key, can only be decripted with the public key
    - decrypted wtih public key, can only be encrypted with the private key
    - RSA, DSA
  - HTTPS uses both
    - browser gets certificate, looks up if it can be trusted and gets the public key of the server
    - browser generates random symmetric key and encrypts it with the public key
    - only the server can decrypt the symmetric key with its private key
    - they communicate with the symmetric key

### Signing

- for checking the validity of the data
- when integrity is important
- A creates hash and encrypts it with private key
- B creates hash and decodes the encrypted data with public key, then compares
- data, signature, certificate

### Keystores

- keystore: for keys
- truststore: for trusted certificates and public keys (browser & OS)
- Let's Encrypt: creates trusted certificates

### Web exploits

- Pentest = Penetration test
  - ethical hacking
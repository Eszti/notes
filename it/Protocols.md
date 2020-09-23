# Protocols

## Compression

- archive file: composed of one or more files with metadata

### Zip

- archive + compression
- Store: no compression
- lossless data compression
- mostly uses DEFLATE (Huffmann...)
- up to 4GB files --> zip64 up to 16EB
- [java library](https://github.com/srikanth-lingala/zip4j)

### Gzip

- based on DEFLATE
- compressed file or archive
- usually faster than zip
- can save more disk space than zip
- can be combined with tar to create archive compressed files

### Tar

- uncompressed archive file

## FTP

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

## FTPS

- FTP over SSL
- support for TLS and SSL(prohibited)

## SFTP

- not compatible with FTPS
- SSH FTP
- ~remote file system protocol (file access, file transfer, file management(mv, cp, rm...))
- SFTP server: usually provided by an SSH server implementation
- shares port 22 with SSH
- extension of SSH
- clients
  - [FileZilla](https://filezilla-project.org/): linux, mac, windows, has also servers
  - [WinSCP](https://winscp.net/eng/download.php): windows only

## SCP

- Secure Copy Protocol
- only allows file transfer
- based on SSH
- Since 2019 April: outdated
- modern protocols: sftp, rsync

## TLS

- at least one of following
  - private connection (handshake, symmetric cryptography)
  - authentication by public-key-cryptography
  - reliable connection: checksum (message integrity)

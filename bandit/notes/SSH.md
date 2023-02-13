
ssh “Secure Shell” is a protocol used to securely connect to a remote server/system. An inherent feature of ssh is that the communication between the two computers is encrypted meaning that it is suitable for use on insecure networks, ssh runs at TCP/IP port 22.

```bash
ssh user_name@host(IP/Domain_name)
```
SSH is often used to "login" and perform operations on remote computers but it may also be used for transferring data, so after logging into the host computer, commands will work as if they were written directly in the host terminal.

SSH client "your computer" will typically support SCP (Secure Copy) and/or SFTP (SSH File Transfer Protocol) for transferring data

It is used to replace unprotected remote login protocols such as Telnet, rlogin, rsh, etc., and insecure file transfer protocol FTP.

## The architecture of SSH Protocol

The SSH architecture is made-up of three well-separated layers. These layers are:

1. Transport Layer => similar to the transport layer security (TLS)
2. User-authentication layer => can be used with the custom authentication methods
3. Connection Layer =>  allows multiplexing different secondary sessions into a single SSH connection.


The SSH protocol architecture is an open architecture; hence it provides great flexibility and enables SSH use for many other purposes instead of only a secure shell.

### Transport Layer

For SSH-2, this layer is responsible for handling initial key exchange, server authentication, set up encryption, compression, and integrity verification.

It works as an interface for sending and receiving plaintext packets with sizes up to 32, 768bytes.

### User authentication Layer

 responsible for handling client authentication and provides various authentication methods. The authentication is done at the client-side; hence when a prompt occurs for a password, it usually for an SSH client rather than a server, and the server responds to these authentications.

This layer includes various methods of authentication; these methods are:

1.** Password**: a straightforward way of authentication. It includes the feature to change the password for easy access. But it is not used by all the applications.
2.** Public-key**: public key-based authentication method, which supports DSA, ECDSA, or RSA keypairs.
3. **Keyboard-interactive**: It is one of the versatile authentication methods. In this, the server sends a prompt to enter information & the client sends it back with keyed-in responses by the user. It is used to provide a one-time password or OTP authentication.
4. **GSSAPI**: In this method, the authentication is performed by external methods such as Kerberos 5 or NTLM, which provide the single sign-on capability to SSH sessions.


### Connection Layer

defines various channels through which SSH services are provided. It defines the concept of channels, channel requests, and global requests. One SSH connection can host different channels simultaneously and can also transfer data in both directions simultaneously.

Channel requests are used in the connection layer to relay out-of-band channel-specific data, for example, the altered size of a terminal window or the exit code of a server-side process. The standard channel types of connection layer are:

1. **shell**: It is used for terminal shells, SFTP, and exec requests.
2. **direct-tcpip**: It is used for the client-to-server forwarded connections.
3. **forwarded-tcpip**: It is used for the server-to-client forwarded connections.


## What can be transferred with SSH protocol?

1. Data
2. Text
3. Commands
4. Files


The files are transferred using the SFTP(Secure file transfer protocol), the encrypted version of FTP that provides security to prevent any threat.

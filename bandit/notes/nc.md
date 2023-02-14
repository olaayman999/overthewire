The Netcat (nc) command is used for reading and writing data between two computer networks. The communication happens using either TCP or UDP.

Netcat is a crucial tool to master for network and system administrators due to the rich connection troubleshooting features and scripting usability.

```bash
nc [<options>] <host> <port>
```
Netcat has two working modes:

**Connect mode**.  Netcat works as a client. The utility requires the `<host>` and `<port>` parameters.
**Listen mode**.  Netcat works as a server. When `<host>` is omitted, Netcat listens on all available addresses for the specified port.

you can test the connect and listen modes via your terminal, this is a very simple chat using 2 terminal windows, one act ac server om 0.0.0.0:1234 and other is the client

![image](https://user-images.githubusercontent.com/72671239/218603844-2e18a733-4684-48b5-9ed9-1723863543a7.png)

### start listening

```bash
nc -lv 0.0.0.0 1234
```
-l listen and -v for verbose output

### start the connection

```bash
nc -v 0.0.0.0 1234
```

### Ping Specific Port on Website
```bash
nc -zv google.com 443
```
The command check if the specified host (google.com) is reachable on port 443. The options used in this command are:

`-z`: This option specifies that `nc` should only scan for listening daemons, **without sending any data**. It essentially _performs a "zero-I/O" connection_ to the target host and port.

`-v`: This option turns on verbose output, which will display information about the progress of the connection attempt.

`google.com`: This is the hostname or IP address of the target host.

`443`: This is the port number of the target service.

The `nc` command will attempt to connect to the specified host and port and report the status of the connection attempt. If the connection is successful, the output will indicate that the connection was established and the host is reachable on the specified port. If the connection is unsuccessful, the output will indicate that the connection was **refused** or **timed out**, and the host is either not reachable or not listening on the specified port.

This command can be useful for troubleshooting network connectivity issues and testing if a specific service is available on a remote host.

------------------------------------------------


if you get this error while trying to establish a listening server:

```text
Ncat: bind to 0.0.0.0:1234: Address already in use. QUITTING.
```
occurs when Ncat, a network utility that reads and writes data across networks, is trying to bind to a specific IP address and port number (0.0.0.0:1234), but the address is already in use by another process. In other words, the port number 1234 is already occupied by another program, and Ncat is unable to bind to it.

There are several ways to find out what program is using a specific IP address and port number on a computer:

 The `netstat` command is a network tool that provides information about network connections and network status. You can use the `netstat`  to list all active connections and the process ID (PID) of the program that is using each connection. You can then use the PID to find the name of the program using the following command:
```bash
sudo netstat -anp | grep 0.0.0.0
```
![image](https://user-images.githubusercontent.com/72671239/218606676-016825df-7acb-4265-9f44-93c9d5bcaf83.png)

to stop a process you can use the following command using thr process id PID
```bash
sudo kill -9 <PID>
```
some processes need root permissions to be killed, and some processes don't respond to the `kill` command so you may use the `-9` flag to force kill

---
id: llt39zkmyoqev9xndqcp2f0
title: SSH
desc: ''
updated: 1690870419468
created: 1689641345561
---

> Secure [[computing.command-line-interface.terminal.shell]]

Is a cryptographic `network protocol` that provides secure communication over a potentially unsecured network. It is widely used for securely accessing and managing remote systems, as well as transferring files between hosts. SSH was designed to replace older, less secure remote login protocols such as Telnet and rlogin.

Key aspects of SSH include:

1. Encryption: SSH encrypts all data transmitted between the client and server, ensuring that sensitive information, including usernames, passwords, and other data, remains confidential and protected from eavesdropping.

2. Authentication: SSH supports various methods of user authentication, including password-based authentication, public-key cryptography, and host-based authentication. Public-key authentication is considered more secure as it eliminates the need to send passwords over the network.

3. Integrity: SSH uses cryptographic mechanisms to verify the integrity of transmitted data, ensuring that it has not been tampered with during transit.

4. Port Forwarding: SSH allows users to set up secure tunnels (port forwarding) that forward traffic from a local port to a remote server and vice versa. This feature enables access to services that are only available on the remote system's network, enhancing security by avoiding direct exposure of services to the internet.

5. X11 Forwarding: SSH supports X11 forwarding, allowing users to run graphical applications on a remote server and display them locally.

6. SFTP (SSH File Transfer Protocol): SFTP provides a secure alternative to FTP (File Transfer Protocol) for transferring files between systems over SSH.

SSH is typically used by system administrators, developers, and network engineers to manage and maintain servers and network devices remotely. It is available on various operating systems, including Unix-based systems (Linux, macOS) and Windows.

OpenSSH is the most widely used implementation of SSH, and it comes pre-installed on many Unix-based systems. For Windows users, there are third-party SSH clients like PuTTY and WinSCP that provide SSH capabilities.

Using SSH, administrators can securely access remote servers, transfer files, manage configurations, perform system maintenance tasks, and troubleshoot issues without physically being present at the remote location, providing a powerful and secure tool for remote management and administration.
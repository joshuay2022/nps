
# NPS

NPS is a lightweight, high-performance, powerful **intranet penetration** proxy server, with a powerful web management terminal.

## Modification

- Add separate certificates for different https reverse hosts on different clients.
    ```bash
    [web1]
    host_cert_file=/path/to/cert.crt ## specify the certificate file on server
    host_key_file=/path/to/key.pem   ## specify the private key file on server

    [web2]
    host_cert_path_prefix=/path/to/dir/ ## specify the directory that contains the certificates for the host domain
    ```

    > `host_cert_file` covers `host_cert_path_prefix`. Certificate path should be `{host_cert_path_prefix}/{host}/fullchain.pem` and key file path should be `{host_cert_path_prefix}/{host}/privkey.pem`

## Feature

- Comprehensive protocol support, compatible with almost all commonly used protocols, such as tcp, udp, http(s), socks5, p2p, http proxy ...
- Full platform compatibility (linux, windows, macos, Synology, etc.), support installation as a system service simply.
- Comprehensive control, both client and server control are allowed.
- Https integration, support to convert backend proxy and web services to https, and support multiple certificates.
- Just simple configuration on web ui can complete most requirements.
- Complete information display, such as traffic, system information, real-time bandwidth, client version, etc.
- Powerful extension functions, everything is available (cache, compression, encryption, traffic limit, bandwidth limit, port reuse, etc.)
- Domain name resolution has functions such as custom headers, 404 page configuration, host modification, site protection, URL routing, and pan-resolution.
- Multi-user and user registration support on server.

**Didn't find the feature you want? It doesn't matter, click [Enter the document](https://ehang-io.github.io/nps/) to find it!**

## Quick start

### Installation

> [releases](https://github.com/joshuay2202/nps/releases)

Download the corresponding system version, the server and client are separate.

### Server start

After downloading the server compressed package, unzip it, and then enter the unzipped folder.

- execute installation command

For linux、darwin ```sudo ./nps install```

For windows, run cmd as administrator and enter the installation directory ```nps.exe install```

- default ports

The default configuration file of nps use 80，443，8080，8024 ports

80 and 443 ports for host mode default ports

8080 for web management access port

8024 for net bridge port, to communicate between server and client

- start up

For linux、darwin ```sudo nps start```

For windows, run cmd as administrator and enter the program directory ```nps.exe start```

```After installation, the windows configuration file is located at C:\Program Files\nps, linux or darwin is located at /etc/nps```

**If you don't find it started successfully, you can check the log (Windows log files are located in the current running directory, linux and darwin are located in /var/log/nps.log).**

- Access server IP:web service port (default is 8080).
- Login with username and password (default is admin/123, must be modified when officially used).
- Create a client.

### Client connection
- Click the + sign in front of the client in web management and copy the startup command.
- Execute the startup command, Linux can be executed directly, Windows will replace ./npc with npc.exe and execute it with cmd.

### Configuration
- After the client connects, configure the corresponding penetration service in the web.
- For more advanced usage, see [Complete Documentation](https://ehang-io.github.io/nps/)

## Contribution
- If you encounter a bug, you can submit it to the dev branch directly.
- If you encounter a problem, you can feedback through the issue.
- The project is under development, and there is still a lot of room for improvement. If you can contribute code, please submit PR to the dev branch.
- If there is feedback on new features, you can feedback via issues or qq group.

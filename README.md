# Web Shell (License: MIT)

- Brief: A kind of Secure Shell Server completely replacing OpenSSH Server, sharing connection message over websocket protocol.
- Support: HTTPS, Basic AUTH, Docker Integration, WebSocket FileUpload, FileDownload, etc.

![image](webshell.png "Web Shell")

--------------------------------------------------------

*Features of webssh-proxy*:

- UTF-8 Support, Color Terminal, Visual Bell/Beep Sound, ..
- Local File Uploading to Remote: support HUGE file upload
- Remote File Downloading to Local: support HUGE file download
- No dependency with OpenSSH Server
- Fully AsyncIO based

*Supported All mainstream browsers*:

-	Firefox/Iceweasel latest (all supported)
-	Chrome/Chromium latest (all supported)
-	IE 11 (only beep sound is not supported)

--------------------------------------------------------

### Run Embeded Web Shell in Docker from Repository

```sh
docker pull ghostplant/webshell
docker run -it --rm --net=host -e LISTEN="8080" ghostplant/webshell
docker run -it --rm --net=host -e LISTEN="8443 ssl" ghostplant/webshell
docker run -it --rm --net=host -e LISTEN="8443 ssl" -e ACCOUNT="admin:badmin" ghostplant/webshell
```
--------------------------------------------------------

### Compile Source Codes on Ubuntu 16.04 LTS

```sh
sudo apt install nginx-core
sudo apt build-dep nginx-core

git clone https://github.com/ghostplant/webshell
cd webshell/
./wsh-compile
./wsh-run
```

### Make Alpine-Embedded WebShell on Ubuntu 16.04 LTS

```sh
sudo apt install nginx-core
sudo apt build-dep nginx-core

git clone https://github.com/ghostplant/webshell
cd webshell/
ALPINE=y ./wsh-compile
docker build -t ghostplant/webshell .

docker run -it --rm --net=host -e LISTEN="8080" ghostplant/webshell
```

--------------------------------------------------------

### Next, open your browser to get access to the terminal

```sh
firefox "http://localhost:8080/"
```

--------------------------------------------------------

If you want to enable http over SSL, change listen ports, or add WWW authorization,
you can add your custom settings in nginx config file - [www.cfg.in](www.cfg.in). 

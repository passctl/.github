# 🔑 passctl
Simple and secure self-hosted command-line password manager

### 📑 Repos
- [Server](https://github.com/passctl/server): An API server to store/backup your local vault
- [Client](https://github.com/passctlr/client): A CLI client to manage your passwords and interact with the API

### 👀 Installing the client
Download the [latest release](https://github.com/passctl/client/releases/latest) for your system. Then place is somewhere on your `PATH`.
For example:
```bash
tar xvf passctl_linux-amd64.tar.gz
sudo mv client /usr/bin/passctl
```
If this is your first installation, run `passctl setup` to create a master password and to generate a token. To learn more about
all the commands run `passctl help` or just `passctl`.

### 🚀 Self-hosting the server
You can self-host a passctl server using docker:
```bash
docker run -d -v $PWD/db:/app/db            \
              -p 80:8080                    \
              ghcr.io/passctl/server:latest \
              0.0.0.0:8080 http://127.0.0.1:8080
```
The first argument (`0.0.0.0:8080`) is the interface that the application
will listen on, the second argument (`http://127.0.0.1:8080`) is the URL for the application.
This should be the full URL that will be used by the clients. For example if you are hosting this server
on `passctl.example.com` using HTTPS, with a reverse proxy setup, then the URL should be `https://passctl.example.com`.

---
<img src="https://files.ngn.tf/gpl3.png" width="300px">

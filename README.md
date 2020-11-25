# big-data

## Contents

1. [Centos 8](#centos-8)
1. [Docker](#docker)

<!-- EMPTY BASE -->
<!-- ```bash

``` -->

## Centos 8

### Install SSH

Install:

```bash
sudo dnf install openssh-server
```

Start & enable:

```bash
sudo systemctl start sshd && sudo systemctl enable sshd
```

Check status:

```bash
sudo systemctl status sshd
```

**Remember to add [ssh service](#services)**

Edit config file:

```bash
sudo nano /etc/sshd/sshd_config
```

### Firewall operations

Default zone:

```bash
sudo firewall-cmd --get-default-zone
```

Get current active zones and their interfaces:

```bash
sudo firewall-cmd --get-active-zones
```

List firewall info:

```bash
sudo firewall-cmd --list-all
```

Reload firewall:

```bash
sudo firewall-cmd --reload
```

Commit runtime changes to permanent firewall config:

```bash
sudo firewall-cmd --runtime-to-permanent
```

#### Services

Add service to firewall **permanently** (--permanent can be excluded to remove the rule at reboot):

```bash
sudo firewall-cmd --zone=YOUR_ZONE --add-service=YOUR_SERVICE --permanent
```

Remove service:

```bash
sudo firewall-cmd --zone=YOUR_ZONE --remove-service=YOUR_SERVICE
```

#### Ports

List ports:

```bash
sudo firewall-cmd --zone=public --list-ports
```

Add port to firewall (Adds permanently. Protocol can be tcp or udp):

```bash
sudo firewall-cmd --zone=public --add-port=PORT/tcp
```

Remove port:

```bash
sudo firewall-cmd --zone=public --remove-port=PORT/tcp
```

---

## Docker

### Docker for Ubuntu

Install for Ubuntu:

[https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)

#### ONE COMMAND (x86_64 / amd64)

(Not guaranteed to work! Check the [Docker official documentation](https://docs.docker.com/engine/install/ubuntu/) for the latest info.)

```bash
curl -fsSL https://get.docker.com -o get-docker.sh && \
sudo sh get-docker.sh && \
sudo usermod -aG docker {user}
```

OR

```bash
sudo apt-get update && \
sudo apt-get install \
  apt-transport-https \
  ca-certificates \
  curl \
  gnupg-agent \
  software-properties-common -y && \
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && \
sudo add-apt-repository \
  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) \
  stable" && \
sudo apt-get update && \
sudo apt-get install docker-ce docker-ce-cli containerd.io -y && \
sudo docker run hello-world && \
sudo usermod -aG docker $USER
```

---

#### Default STEP BY STEP

```bash
sudo apt-get update
```

```bash
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

#### x86_64 / amd64

```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

TEST:

```bash
sudo docker run hello-world
```

User group:

```bash
sudo usermod -aG docker {user}
```

---

### Docker for CentOS

Install for CentOS:

[https://docs.docker.com/engine/install/centos/](https://docs.docker.com/engine/install/centos/)

#### ONE COMMAND

(Not guaranteed to work! Check the [Docker official documentation](https://docs.docker.com/engine/install/centos/) for the latest info.)

```bash
curl -fsSL https://get.docker.com -o get-docker.sh && \
sudo sh get-docker.sh && \
sudo usermod -aG $USER
```

---

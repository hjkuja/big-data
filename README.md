# big-data

## Contents

1. [Centos 8](#centos-8)
1. [Docker](#docker)

## Commands

<!-- EMPTY BASE -->
<!-- ```bash

``` -->

### Centos 8

#### Firewall operations

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

Add service to firewall **permanently** (--permanent can be excluded to remove the rule at reboot):

```bash
sudo firewall-cmd --zone=YOUR_ZONE --add-service=YOUR_SERVICE --permanent
```

---

List ports:

```bash
sudo firewall-cmd --zone=public --list-ports
```

Add port to firewall (Adds permanently. Protocol can be tcp or udp):

```bash
sudo firewall-cmd --zone=public --add-port=5000/tcp
```

Commit runtime changes to permanent firewall config:

```bash
sudo firewall-cmd --runtime-to-permanent
```

---

### DOCKER

Install for Ubuntu:

https://docs.docker.com/engine/install/ubuntu/

#### ONE COMMAND (x86_64 / amd64)

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

Käyttäjän group:

```bash
sudo usermod -aG docker {user}
```

---

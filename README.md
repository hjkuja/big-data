# big-data

## Komentoja ja linkkejä

### DOCKER

Install for Ubuntu:

https://docs.docker.com/engine/install/ubuntu/

#### YKSI KOMENTO (x86_64 / amd64)

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

#### PERUS STEP BY STEP

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

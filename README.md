<img width="1024" height="1024" alt="ChatGPT Image Nov 17, 2025, 05_55_06 PM" src="https://github.com/user-attachments/assets/3dd95127-1329-4db0-bc32-588fc16744da" />





# Swarm-Gensyn
Run swarm node and contribute to gensyn network, also get the Swarm role




# 1) Install Requirements :

```
 sudo apt update && sudo apt upgrade -y
```

```
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```

```
sudo apt install python3 python3-pip python3-venv python3-dev -y
```
```
sudo apt update
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo bash -
sudo apt install -y nodejs
node -v
npm install -g yarn
yarn -v
```


```
curl -o- -L https://yarnpkg.com/install.sh | bash
```

```
export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"
```

```
source ~/.bashrc
```

---

## Go
```console
sudo rm -rf /usr/local/go
curl -L https://go.dev/dl/go1.22.3.linux-amd64.tar.gz | sudo tar -xzf - -C /usr/local
echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bash_profile
source .bash_profile
go version
```
## Docker, Docker-Compose
```console
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test Docker
sudo docker run hello-world
docker ps -a
```
```
docker compose run --rm --build -Pit swarm-cpu
```

---

## 2) Clone the Repository :
```
git clone https://github.com/gensyn-ai/rl-swarm/
```


```
cd rl-swarm
```




## 3) Run the swarm :


### CLI Method 
1- Open a screen to run it in background
```bash
screen -S swarm
```
2- Get into the `rl-swarm` directory
```
cd rl-swarm
```
3- Install swarm
```bash
python3 -m venv .venv

source .venv/bin/activate
# if not worked, then:
. .venv/bin/activate

```


## 4) Login :
**1- You have to receive `Waiting for userData.json to be created...` in logs**

Note: Open a new terminal


**2- Open login page in browser**
* **Local PC:** Open `http://localhost:3000/` in your browser
* **GPU Cloud & VPS Users: Tunnel to external URL:**
  * 1- Open a new terminal
  * 2- Install **localtunnel**:
    ```
    sudo npm install -g localtunnel
    ```
  * 3- Get a password:
    ```
    curl https://loca.lt/mytunnelpassword
    ```
  * The password is actually your VPS IP
  * 4- Get URL
    ```
    lt --port 3000
    ```
  * Visit the prompted url, and enter your password to access Gensyn login page

 ## If You Encounter This Error
 
 <img width="1920" height="779" alt="image_2025-11-17_17-47-22" src="https://github.com/user-attachments/assets/9a158a3e-55da-40e5-ab56-75de1b3d53f9" />

 ```
deactivate && rm -rf .venv && python3 -m venv .venv && source .venv/bin/activate && bash run_rl_swarm.sh
```
 
 ## Important note: 
  if after 3 or 4 hours you don't get any TX on `https://gensyn-testnet.explorer.alchemy.com` please `rm -rf rl-swarm` and rerun

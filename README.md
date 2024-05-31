# Run Nwaku with Docker Compose
![Capture](https://github.com/Rezaheydariii/Run-Nwaku-with-Docker-Compose/assets/140112620/01dbf6e0-e499-4fb4-b4bd-e95f1ba94851)

Connect with me:
Disc : reloolooza
X : [Shahfilsoof](https://x.com/ShahFilsoof)
# Prerequisites:
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
# Install Docker:
```
sudo apt install docker-ce
sudo systemctl status docker
```
# Install Docker Compose:
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
```
sudo chmod +x /usr/local/bin/docker-compose
```
# Docker Compose V. :
```
docker-compose --version
```
# Clone a GitHub repository:
```
git clone https://github.com/waku-org/nwaku-compose.git
cd nwaku-compose
```
# Editing  .env file:
```
cp .env.example .env
```
```
nano .env
```
like this:

![Capture](https://github.com/Rezaheydariii/Run-Nwaku-with-Docker-Compose/assets/140112620/68f68573-bc32-43a5-9086-17ba5e9af668)


# Do these things:
Ethereum Sepolia WebSocket endpoint : [Here](https://github.com/waku-org/nwaku/blob/master/docs/tutorial/pre-requisites-of-running-on-chain-spam-protected-chat2.md#3-access-a-node-on-the-sepolia-testnet-using-infura )
* Place final result in  .env file at appropriate location.
* private key at appropriate location.
* sepolia faucet:[Here](https://www.infura.io/faucet/sepolia)
 # Register RLN membership:
The RLN membership is your access key to The Waku Network. Its registration is done onchain, and allows your nwaku node to publish messages in a decentralized and private way, respecting some rate limits. Messages exceeding the rate limit won't be relayed by other peers.

This command will register your membership and store it in keystore/keystore.json. Note that if you just want to relay traffic (not publish), you don't need one.
```
./register_rln.sh
```
If you see an error, ignore it.
#  Start your node:
```
docker-compose up -d
```
* The node might take ~5' the very first time it runs because it needs to build locally the RLN community membership tree.
![Capture](https://github.com/Rezaheydariii/Run-Nwaku-with-Docker-Compose/assets/140112620/876f92dd-d159-4b52-91a9-3e0a726f4c38)

#  Interact with your nwaku node:
See http://localhost:3000/d/yns_4vFVk/nwaku-monitoring for node metrics.

See localhost:4000. Under development 🚧


# Useful commands:
logs node:
```
docker compose logs
```
down node:
```
docker compose down
```
get nwaku version: At this moment v0.28.0
```
curl http://127.0.0.1:8645/debug/v1/version
```
get nwaku info:
```
curl http://127.0.0.1:8645/debug/v1/info
```
or for enr address
```
curl http://127.0.0.1:8645/debug/v1/info | json_pp
```
get nwaku node logs:
```
docker compose logs nwaku
```

```
docker ps
```


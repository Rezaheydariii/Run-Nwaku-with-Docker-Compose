# Run-Nwaku-with-Docker-Compose
![Capture](https://github.com/Rezaheydariii/Run-Nwaku-with-Docker-Compose/assets/140112620/01dbf6e0-e499-4fb4-b4bd-e95f1ba94851)
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

#RPC URL for accessing testnet via HTTP.
#e.g. https://sepolia.infura.io/v3/123aa110320f4aec179150fba1e1b1b1
ETH_CLIENT_ADDRESS=https://sepolia.infura.io/v3/<key>

#Private key of testnet where you have sepolia ETH that would be staked into RLN contract.
#Note: make sure you don't use the '0x' prefix.
#e.g. 0116196e9a8abed42dd1a22eb63fa2a5a17b0c27d716b87ded2c54f1bf192a0b
ETH_TESTNET_KEY=Ethereum wallet private key.

#Password you would like to use to protect your RLN membership.
RLN_RELAY_CRED_PASSWORD="my_secure_keystore_password"

#Advanced. Can be left empty in normal use cases.
NWAKU_IMAGE=
NODEKEY=
DOMAIN=
EXTRA_ARGS=
STORAGE_SIZE=

# Do these things:
Ethereum Sepolia WebSocket endpoint : [Here](https://github.com/waku-org/nwaku/blob/master/docs/tutorial/pre-requisites-of-running-on-chain-spam-protected-chat2.md#3-access-a-node-on-the-sepolia-testnet-using-infura )
* Place final result in  .env file at appropriate location.
* private key at appropriate location.
sepolia faucet:[Here](https://www.infura.io/faucet/sepolia)
 # Register RLN membership:
The RLN membership is your access key to The Waku Network. Its registration is done onchain, and allows your nwaku node to publish messages in a decentralized and private way, respecting some rate limits. Messages exceeding the rate limit won't be relayed by other peers.

This command will register your membership and store it in keystore/keystore.json. Note that if you just want to relay traffic (not publish), you don't need one.
```
./register_rln.sh
```
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



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
# RPC URL for accessing testnet via HTTP.
# e.g. https://sepolia.infura.io/v3/123aa110320f4aec179150fba1e1b1b1
ETH_CLIENT_ADDRESS=https://sepolia.infura.io/v3/<key>

# Private key of testnet where you have sepolia ETH that would be staked into RLN contract.
# Note: make sure you don't use the '0x' prefix.
#       e.g. 0116196e9a8abed42dd1a22eb63fa2a5a17b0c27d716b87ded2c54f1bf192a0b
ETH_TESTNET_KEY=Ethereum wallet private key.

# Password you would like to use to protect your RLN membership.
RLN_RELAY_CRED_PASSWORD="my_secure_keystore_password"

# Advanced. Can be left empty in normal use cases.
NWAKU_IMAGE=
NODEKEY=
DOMAIN=
EXTRA_ARGS=
STORAGE_SIZE=

# Ethereum Sepolia WebSocket endpoint. Get one free from Infura. 



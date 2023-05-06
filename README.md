# QSAC-IoT
QSAC-IoT is a project that aims to provide a quantum-safe access control solution for IoT devices. 
It uses Hyperledger Indy for decentralized identifier creation and Delithium-Crystals for post-quantum digital signatures.

## Files
QSAC-IoT consists of two files in the components folder:
+ **verkeyQuery.js** - This file contains the code for creating a decentralized identifier (DID) using Hyperledger Indy and searching its verification key on the blockchain.
+ **dilithiumSignatures.js** - This file contains the implementation of the Delithium-Crystals signature functions.


## Requirements
 - Node.js
 - Docker
 - Hyperledger Indy + Libindy

## Hyperledger Indy + Libindy Setup
```
sudo apt-get install ca-certificates -y
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys CE7709D068DB5E88
sudo add-apt-repository "deb https://repo.sovrin.org/sdk/deb (xenial|bionic) stable"
sudo apt-get update
sudo apt-get install -y libindy
git clone https://github.com/hyperledger/indy-sdk.git
cd indy-sdk
docker build -f ci/indy-pool.dockerfile -t indy_pool .
docker run -itd -p 9701-9708:9701-9708 indy_pool
```
(xenial|bionic) xenial for 16.04 Ubuntu and bionic for 18.04 Ubuntu.

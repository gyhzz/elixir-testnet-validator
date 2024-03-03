# elixir-testnet-validator

## Follow these steps to host an Elixir Testnet Validator on GCP

#### Create New VM Instance on GCP Compute Engine
1. Start a new VM instance on GCP using Compute Engine 
2. Select e2-medium machine type with 2vCPU, 1 core, 4GB memory
3. For boot disk, select Ubuntu 20.04 LTS as OS, 50GB size
4. For Firewall, allow HTTP and HTTPS traffic

#### Create New MetaMask Wallet
1. Create a new MetaMask wallet
2. Copy your wallet address and private key

#### Install Docker and Build Validator Image
1. SSH into your new VM by clicking on SSH by your VM instance in Google Cloud Console
1. By default Docker is not installed in your new VM
2. To install, use these commands -> sudo apt-get update -> sudo apt-get install docker.io
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

#### Install Docker
1. SSH into your new VM by clicking on SSH by your VM instance in Google Cloud Console
2. By default Docker is not installed in your new VM
3. To install, use these commands -> sudo apt-get update -> sudo apt-get install docker.io
4. Give yourself permission to view, create, and run Docker images using this command -> sudo usermod -aG docker your-username
5. Close and reopen your terminal
5. Check if Docker has been installed by running the command docker ps -a. This will show you all containers both running and stopped

#### Build Validator Image and Run Container
1. Open your Dockerfile, change the wallet address and private key fields and give a name to your validator
2. Transfer your Dockerfile to your VM via the SSH terminal
3. Build image using this command -> docker build . -f Dockerfile -t elixir-validator
4. Run the image in a new container using this command -> docker run -d --restart unless-stopped --name ev elixir-validator
5. To verify that your container is running, use the command docker ps -a
6. To see logs from your running Docker container, use this command -> docker logs -f <container id>
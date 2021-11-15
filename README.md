# wsl-setup

Scripts to download and install WSL 

Invoke-WebRequest -Uri https://aka.ms/wslubuntu2004 -OutFile Ubuntu.appx -UseBasicParsing

Add-AppxPackage .\Ubuntu.appx

# Update Ubuntu
sudo apt update
sudo apt upgrade
# Install Terraform in Ubuntu

Configure Repo 
## trust that HashiCorp key for package authentication
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
## add the official HashiCorp repository
sudo apt-add-repository "deb [arch=$(dpkg --print-architecture)] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

sudo apt install terraform=0.13.7


# Install Azure CLI

curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash


or 

Get packages needed for the install process:

Bash

Copy
sudo apt-get update
sudo apt-get install ca-certificates curl apt-transport-https lsb-release gnupg
Download and install the Microsoft signing key:

Bash

Copy
curl -sL https://packages.microsoft.com/keys/microsoft.asc |
    gpg --dearmor |
    sudo tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null
Add the Azure CLI software repository:
Bash

Copy
AZ_REPO=$(lsb_release -cs)
echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" |
    sudo tee /etc/apt/sources.list.d/azure-cli.list
Update repository information and install the azure-cli package:

Bash

Copy
sudo apt-get update
sudo apt-get install azure-cli

REF https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt
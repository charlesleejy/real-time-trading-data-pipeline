# real-time-trading-data-pipeline


Install Minikube, Helm, Docker, and Terraform on MacOS

1. Install Homebrew

Paste in Terminal

``` bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Ref: https://brew.sh


2. Install Docker Desktop

Docker Desktop now provides native support for Apple Silicon.

Download Docker Desktop for Mac with Apple Silicon from the Docker Hub:

- Go to Docker Hub and download the version for Apple Silicon.

Install Docker Desktop:

- Open the .dmg file you downloaded and drag the Docker icon to your Applications folder.
- Open Docker from your Applications folder. The first launch will ask for permissions and guide you through the initial setup.

3. Install Minikube

Minikube runs a Kubernetes cluster locally. Install it using Homebrew:

``` bash
brew install minikube
```

Since Minikube runs a Kubernetes cluster within a virtual machine, ensure your Docker Desktop is configured correctly to integrate with Minikube by setting it as your driver:

minikube config set driver docker
minikube start

4. Install Helm

Helm is a package manager for Kubernetes, which helps you manage Kubernetes applications. Install it using Homebrew:

``` bash
brew install helm
```

5. Install Terraform

Terraform is an infrastructure as code software by HashiCorp. It allows you to define and provision infrastructure using a high-level configuration language. Install it using Homebrew:

``` bash
brew install terraform
```

6. Verify Installation

``` bash
docker --version
minikube version
helm version
terraform version 
```

Additional Configurations and Tips
- Docker Desktop Configuration: Go to Docker's Preferences -> Resources to adjust the CPU and memory allocated to Docker, which affects Minikube's performance.
- Network Permissions: MacOS may prompt you for additional network permissions for Docker or Minikube, especially during the first run. Make sure to allow these permissions for proper functionality.
- Minikube and Virtualization: If you experience issues with Minikube, consider switching the driver from Docker to another virtualization technology like HyperKit, though Docker is generally recommended for its performance on Silicon chips.
### Set Up

### 1. Set Environment Variables

```bash
export HTTP_PROXY=http://<proxy hostname:port>
export HTTPS_PROXY=https://<proxy hostname:port>
export NO_PROXY=localhost,127.0.0.1,10.96.0.0/12,192.168.59.0/24,192.168.49.0/24,192.168.39.0/24
```

### 2. Start Minikube

```bash
minikube start --driver=virtualbox --memory 10240 --cpus 6 --no-vtx-check
```
You can also switch `--driver=virtualbox` to `--driver=docker` if you prefer using Docker.

### 3. Configure Docker Environment
On macOS, you can similarly source the Docker environment setup. Minikube provides a convenient command to do this:

```bash
eval $(minikube docker-env)
```

### 4. Build Docker Images with Docker Compose
Assuming you have `docker-compose` installed (it comes with Docker Desktop for Mac), you can run:

```bash
docker-compose -f docker-compose-ci.yaml build --no-cache
```

### 5. Run Terraform
Navigate to your Terraform directory and apply your configuration:

```bash
cd terraform-k8s
terraform init  # Only needed if you haven't initialized Terraform in this directory
terraform apply
```

### Additional Setup Steps for macOS

#### Install Homebrew (if not already installed)
Homebrew is a package manager for macOS that simplifies the installation of software. Paste the following command into a terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Install Minikube, Docker, and Terraform via Homebrew
You can easily install these tools using Homebrew:

```bash
brew install minikube docker docker-compose terraform
```

#### Install VirtualBox (if using as a driver for Minikube)
If you choose to use VirtualBox instead of Docker as your Minikube driver:

```bash
brew install --cask virtualbox
```

By following these steps, you'll be able to configure and run your Kubernetes cluster. Make sure each component is correctly installed and configured before proceeding with starting Minikube or deploying services with Terraform.
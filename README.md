# kind_setup_ubantu

install kind on ubantu

[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.31.0/kind-linux-amd64

Run these commands:

chmod +x kind
sudo mv kind /usr/local/bin/kind

Now verify:

kind --version
for deploy cluster Verify Prerequisites
docker --version
kubectl version --client
kind --version

You already installed kind ✔️, but Docker and kubectl are missing, which are required for running a Kubernetes cluster. Let's install everything step-by-step. 🔨🤖🔧

Install Required Packages
sudo apt update
sudo apt install -y ca-certificates curl gnupg

Add Docker GPG Key
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

Add Docker Repository

echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo $VERSION_CODENAME) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Update Package Index

sudo apt update
Install Docker
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
Start Docker

sudo systemctl start docker
sudo systemctl enable docker

Verify:
docker --version

Verify:
docker --version

Allow Running Docker Without sudo (Recommended)
sudo usermod -aG docker $USER
Then reload your session:
newgrp docker
Test:
docker run hello-world

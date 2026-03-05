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

sudo apt update
sudo apt install -y docker.io

Start Docker:
sudo systemctl start docker
sudo systemctl enable docker

Verify:
docker --version

Allow Running Docker Without sudo (Recommended)
sudo usermod -aG docker $USER
Then reload your session:
newgrp docker
Test:
docker run hello-world

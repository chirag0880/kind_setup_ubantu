# kind_setup_ubantu

install kind on ubantu

[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.31.0/kind-linux-amd64

Run these commands:

chmod +x kind
sudo mv kind /usr/local/bin/kind

Now verify:

kind --version

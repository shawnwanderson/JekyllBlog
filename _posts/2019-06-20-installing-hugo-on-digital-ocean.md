---
published: true
---
## Installing Hugo on Digital Ocean (with fish shell)

```
sudo apt-get update
sudo apt-get -y upgrade

cd /tmp
wget https://dl.google.com/go/go1.11.linux-amd64.tar.gz

sudo tar -xvf go1.11.linux-amd64.tar.gz
sudo mv go /usr/local

mkdir ~/goworkspace
set --universal -x GOPATH ~/goworkspace
set --universal -x GOROOT /usr/local
set -gx PATH $PATH $GOROOT/bin

go version

cd ~/goworkspace
git clone https://github.com/gohugoio/hugo.git
cd hugo
go install --tags extended

```

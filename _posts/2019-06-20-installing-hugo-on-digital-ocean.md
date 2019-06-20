---
published: true
---
## Installing Hugo on Digital Ocean (with fish shell)

```
sudo apt-get update
sudo apt-get -y upgrade

cd /tmp
wget https://github.com/gohugoio/hugo/releases/download/v0.55.6/hugo_extended_0.55.6_Linux-64bit.deb
sudo dpkg -i  hugo_extended_0.55.6_Linux-64bit.deb
hugo version

```

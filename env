#!/usr/bin/env bash

# git init
git config --global color.status auto
git config --global color.diff   auto
git config --global color.branch auto
git config --global color.interactive auto
git config --global color.ui    true
git config --global pull.rebase true
git config --global core.autocrlf input
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
git config --global alias.lgh "log --graph --decorate --oneline --pretty=format:'%Cred%h - %C(bold white) %s %Creset %C(yellow)%d  %C(cyan) <%cd> %Creset %Cgreen(%cn)' --abbrev-commit --date=format:'%Y-%m-%d %H:%M:%S'"
git config --global url."https://github.com.cnpmjs.org".insteadOf "https://github.com"


# helm install
wget -O helm.tar.gz https://get.helm.sh/helm-v3.6.3-linux-amd64.tar.gz
tar -zxvf helm.tar.gz
sudo mv linux-amd64/helm /usr/local/bin/helm
rm -rf linux-amd64 helm.tar.gz

# docker
#curl -fsSL https://get.docker.com -o get-docker.sh | sudo sh 

sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
sudo yum install -y yum-utils
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io
sudo systemctl start docker
sudo docker run hello-world

#uninstall docker
#sudo yum remove docker-ce docker-ce-cli containerd.io
#sudo rm -rf /var/lib/docker /var/lib/containerd

#kubernetes install
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client

# ubuntu-22-personal-system-installation

Table of Contents
=================

   * [Error zsh: command not found: jq](#error-zsh-command-not-found-jq)
   * [Too many authentication failures](#too-many-authentication-failures)
   * [Pull newly create Github branches on working directoy](#pull-newly-create-github-branches-on-working-directoy)
   * ['zsh: command not found: python'](#zsh-command-not-found-python)
   * [permission denied while trying to connect to the Docker daemon socket at unix](#permission-denied-while-trying-to-connect-to-the-docker-daemon-socket-at-unix)
   * [zsh: command not found: helm](#zsh-command-not-found-helm)
   * [Remove snap install package](#remove-snap-install-package)
   * [Install Relax Brack Package](#install-relax-brack-package)
   

## Error zsh: command not found: jq
* 🤔 Try to add EKS node label with the command `export FIRST_NODE_NAME=$(kubectl get nodes -o json | jq -r '.items[0].metadata.name')`
* ❌ `Error: zsh: command not found: jq`
* 🎯 `sudo apt-get install jq`

## Too many authentication failures
* 🤔  try to ssh to ec2 instance from ubuntu `ssh username@X.X.X.X`
* ❌ `Received disconnect from X.X.X.X port 22:2: Too many authentication failures`
* 🎯 add the following line to your `/home/user/.ssh/config`
```
  Host * 
       	IdentitiesOnly=yes
```
## Pull newly create Github branches on working directoy 
* 🤔  on `main` or `Working-Branch` try `git pull origin main` and then run command `git checkout New-existing-branch`
* ❌ `error: pathspec 'New-existing-branch' did not match any file(s) known to git`
* 🎯 run `git pull` only not with origin
##  'zsh: command not found: python'
* 🤔  Try to deploy SAM aws solution 
* ❌  'zsh: command not found: python'
* 🎯 run `sudo apt-get install python3.8` and ` echo "alias python=/usr/bin/python3.8" >> ~/.zshrc`
##  permission denied while trying to connect to the Docker daemon socket at unix
* 🤔  Try to run `docker ps` 
* ❌  `permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json": dial unix /var/run/docker.sock: connect: permission denied`
* 🎯 Run following command
    ```
    ls -l /var/run/docker.sock
    sudo chmod 666 /var/run/docker.sock
    systemctl restart docker.service
    ```
##  zsh: command not found: helm
* 🤔  Try to run `helm repo add` 
* ❌  `zsh: command not found: helm`
* 🎯 Run following command
  ```
  wget https://get.helm.sh/helm-v3.12.0-linux-amd64.tar.gz
  tar -xvf  helm-v3.12.0-linux-amd64.tar.gz
  mv linux-amd64/helm  /usr/local/bin
  ```

##  Remove snap install package
* 🤔  Try remove snap install package
* 🎯 Run following command `sudo snap remove breaktimer`


##  Install Relax Brack Package 
* 🤔  Try add breaks from work software
* 🎯 Run following command `sudo snap install stretchly`
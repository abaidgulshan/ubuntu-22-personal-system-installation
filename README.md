# ubuntu-22-personal-system-installation
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

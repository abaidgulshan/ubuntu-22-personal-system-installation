# ubuntu-22-personal-system-installation
## Error zsh: command not found: jq
* 🤔 Try to add EKS node label with the command `export FIRST_NODE_NAME=$(kubectl get nodes -o json | jq -r '.items[0].metadata.name')`
* ❌ `Error: zsh: command not found: jq`
* 🎯 `sudo apt-get install jq`

## Too many authentication failures
* 🤔  try to ssh to ec2 instance from ubuntu `ssh username@X.X.X.X`
* ❌ Received disconnect from X.X.X.X port 22:2: Too many authentication failures
* 🎯 add following line to your `/home/user/.ssh/config`
```
  Host * 
       	IdentitiesOnly=yes
```

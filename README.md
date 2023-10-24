# ubuntu-22-personal-system-installation
## Error zsh: command not found: jq
* 🤔 Try to add EKS node label with the command `export FIRST_NODE_NAME=$(kubectl get nodes -o json | jq -r '.items[0].metadata.name')`
* ❌ Error: zsh: command not found: jq 
* 🎯 `sudo apt-get install jq`

# Intro to Docker orchestration with Rancher using Terraform & Ansible for deployment

# Description
- Aids in setup of Docker + Rancher on Digital Ocean with Terraform/Ansible
- Also contains [nodejs-echo-hostname](https://hub.docker.com/r/johnculviner/nodejs-echo-hostname/)
which helps to illustrate Rancher load balancing

# Setup
- Create a Digital Ocean [API token](https://cloud.digitalocean.com/settings/api/tokens)
- set an environment variable for the token
```
export DIGITALOCEAN_TOKEN="ABDC123..."
```
- Install ansible
- Install terraform

- To create your VMs, from `./terraform` run
```
terraform apply
```
- The script updates ansible inventory with the new IPs 

- Visit http://IP_OF_YOUR_DOCKER_0_BOX:8080/
  Infrastructure > Add Hosts
- Run
```
ansible all -u root -a "COMMAND_RANCHER_GIVES_YOU"
```
NOTE: add a curl to grab this and automatically insert into ansible cmd

# Done!
You should now have a multi-node Rancher + Cattle + Docker cluster going that you can now run containers on

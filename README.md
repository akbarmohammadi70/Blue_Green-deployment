# Blue/Green deployment with Ansible
A sample project to Docker Swarm and blue-green deployment model plus a load balanced and reversed proxy with nginx.

## Prerequisites
- at least four machines

## An ansible playbook for setup Docker and nginx machine
Install ansible on master machine and execute **ansible-playbook install.yml**  on the master , Executing this command will install Docker and Nginx as well as firewall settings .

## An ansible playbook for building and pushing docker images
Execute **ansible-playbook buildAndpush.yml --extra-vars "v:(version) push:(accountname/imagename)"** on the master for build and push to docker hub.

## An ansible playbook which deploys
Execute **ansible-playbook blue-green.yml** for deploy containers. 

## Conclusion

I used here 3 machines for Docker and one machine for Nginx, one of which used Workers as Blue and the other as Green, which are running as a Service in Swarm and have their own ports in Nginx. They can also be accessed.
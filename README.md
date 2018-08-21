# ansible-testing

## This tool can be used to maintain a source of truth of load balancer configuration within GitHub.

### The main files used within this tool are:

- **inventory.yaml** - contains the host IPs of the F5's to be managed
- **githubplay.yaml** - contains the ansible playbook to add, modify and delete pools, virtuals servers, client-ssl profiles and nodes.
- **opt/vars/virtuals.yaml** - contains virtual server configuration for the load balancer
- **opt/vars/pools.yaml** - contains pool configuration for the load balancer
- **opt/vars/nodes.yaml** - contains node member configuration for the load balancer
- **opt/vars/clientssl_profiles.yaml** - contains client-ssl profile configuration for the load balancer

### To use this tool you need to:

1) Add your SSH Key to GitHub if it is not already. (See: https://help.github.com/articles/connecting-to-github-with-ssh/)

2) Download virtualenv by running the command `easy_install virtualenv`

3) Once virtualenv is installed make a new directory to create a virtualenv within. `mkdir ~/f5-ansible`, `cd ~/f5-ansible`, `virtualenv f5-ansible`.

4) Spin up your newly created virtualenv. `source bin/active`

Download the f5-sdk, python, bigsudds.

Clone the ansible-testing repo.

/var/ contains virtual, pool and node info.

Run the playbook using: ansible-playbook -i inventory.yaml githublplay.yaml 

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

4) Spin up your newly created virtualenv. `source bin/f5-ansible/activate`

5) Download pip (if not installed already), f5-sdk, python and bigsuds.

`easy_install pip`
`pip install f5-sdk`
`pip install python`
`pip install bigsuds`

6) Fork this repository and clone it to your local machine by performing a `git clone`.

7) Add the necessary ammendments to the respective /opt/var files and submit a PR to have your changes reviewed.

8) Once reviewed and merged, delete the previously forked respository and any previous git clone from your virtualenv.

9) Fork the repository once again and clone it to your local machine by performing a `git clone`.

10) Navigate to the directory ansible testing by entering `cd ansible-testing`

11) Run the playbook in dry run mode using the command: `ansible-playbook -i inventory.yaml githubplay.yaml --check`

12) Verify that any changes that Ansible is suggesting will be made are in fact correct and that no errors are output.

13) Once satisfied that they are, run the playbook normally using the command: `ansible-playbook -i inventory.yaml githubplay.yaml`

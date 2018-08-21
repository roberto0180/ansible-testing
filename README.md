# ansible-testing

Inventory.yaml contains the host IPs of the F5.

Githubplay.yaml contains the ansible playbook to add, change pools, virtuals, and nodes.

Before running you need to add your SSH key to GitHub. Download the f5-sdk, python, bigsudds.

/var/ contains virtual, pool and node info.

Run the playbook using: ansible-playbook -i inventory.yaml githublplay.yaml 

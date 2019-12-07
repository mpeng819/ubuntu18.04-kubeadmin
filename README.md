Setup a K8S Cluster 
1xmaster
4xnodes

# Setup the VMs in Virtualbox 
0. vagrant up 

# Init all the VM servers
1. ansible-playbook -i hosts -u vagrant -k initial_server_setup.yaml

# Install the K8s dependencies
2. ansible-playbook -i hosts -u vagrant k8s-dependencies.yaml

# Init the master
3. ansible-playbook -i hosts -u vagrant k8s-master.yaml

# Init the nodes
4. ansible-playbook -i hosts -u vagrant k8s-nodes.yaml

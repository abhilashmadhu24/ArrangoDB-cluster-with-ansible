##### Ansible-play book for ArangoDB cluster installation:

Pre-requisites: 3 ubuntu machines
Ansible 2.5.1

1) Edit inventory file and add nodes IP address (If your ansible master server is in same vpc , add private IP of nodes here , else use public IP)
   Edit ansible connection configurations also like below with your parameters

ansible_connection='ssh'
ansible_ssh_port='<ssh port>'
ansible_user='<ssh user>'
ansible_ssh_private_key_file=<ssh private key location>

2) Edit vars/default.yml and change below values

main_node: "<private IP of node 1>"
db_root_passwd: "<arangoDB cluster root password>"
max_count: "<max count value>"

#how to find max count value : no of cores X ram X 8000

===================================================

how to run :
```
Extract the tar file arangoDB_cluster.tar.gz
cd arangoDB_cluster.tar
ansible-playbook deploy_dbcluster.yml
```

===================================================

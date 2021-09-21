##### Ansible-play book for ArangoDB cluster installation ####

Hi,

This is a ansible playbook for ArangoDB cluster Installation on Ubuntu Machines.

ArangoDB is an open source native multi-model database. It supports graph, document, and key-value data models allowing users to freely combine all data models in a single query. The querry language used for ArrangoDB is is called AQL. (ArangoDB Query Language). The query language is declarative and allows the combination of different data access patterns in a single query.

For More details : https://www.arangodb.com/

![Blank diagram (1)](https://user-images.githubusercontent.com/50264439/134165532-197dcb43-93d0-4273-a762-517fea1310fe.jpeg)


Pre-requisites: 3 ubuntu machines
Ansible 2.5.1

1) Edit inventory file and add nodes IP address (If your ansible master server is in same vpc , add private IP of nodes here , else use public IP)
   Edit ansible connection configurations also like below with your parameters
```
ansible_connection='ssh'
ansible_ssh_port='<ssh port>'
ansible_user='<ssh user>'
ansible_ssh_private_key_file=<ssh private key location>
```

2) Edit vars/default.yml and change below values
```
main_node: "<private IP of node 1>"
db_root_passwd: "<arangoDB cluster root password>"
max_count: "<max count value>"
```
#how to find max count value : no of cores X ram X 8000



How to run :
```
Extract the tar file arangoDB_cluster.tar.gz
cd arangoDB_cluster.tar
ansible-playbook deploy_dbcluster.yml
```



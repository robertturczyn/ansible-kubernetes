# ansible-kubernete

These are simple playbooks to setup a Kubernetes cluster on Raspberry Pi's running Raspbian Buster OS. You will need at least two Pi's running Buster, a master and a slave, for this to work. This is designed as more of a personal project to play around with Kubernetes.
The steps in this read me will remain very general. I have included my yaml style inventory file, but you could modify the host file in /etc/ansible or do it in INI if you want.

# Requirements
You will need to install ansible on one of these nodes to use it as a deploy node. I personally do it on the master node. To install ansible use the following command:

```
yum install ansible
```

After ansible is installed setup ssh keys so the deployment ndoe can connect to the other nodes in the cluster. I also change the hostname of the Raspberry Pi's as well for the host file.

# Running a playbook

Once everything is installed you can run the ansible playbook. If you use a custom inventory file like I do make sure you use the -i arg and point it to where that file resides on the subsystem. 

An example command would be similar to what I use like this: 

```
ansible-playbook master.yml -i /etc/ansible/inventory.yml
```

My inventory file takes care of which nodes this gets ran on.

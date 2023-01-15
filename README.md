# Cloud_hpc
A repo with notes, scripts, and source code for running hpc codes on clusters of VMs

# VM cluster set up
In my case the cloud is set up in OpenStack. We are using one external and one internal network There is one VM connected to both the external and internal network, and the rest are only connected to the internal network

## Launching an instance and connecting to it through SSH
Before launching an instance configure security rules for instances as described here:\
https://docs.openstack.org/horizon/queens/user/configure-access-and-security-for-instances.html

Save the SSH key to your local machine. 

Then launch a new instance, specifying the created security rules and SSH key. As described here:\
https://www.youtube.com/watch?v=BZ204OE8CSc&t=29s \
(Configuring floating IPs is not necessary)

Change the permissions for SSH.pem:
```shell
$ chmod 700 SSH.pem
```

Connect to instance using:
```shell
$ ssh -i SSH.pem ubuntu@x.x.x.x
```

## Setting up an mpi cluster
After creating all the instances, they can be configured for MPI in the dollowing way:

Because the instances are fresh installations run:
```shell
sudo apt-get update
```

### Create separate users for mpi on each server and conect them with ssh:

(Note to self - do we really need to do this? Can we use the default ubuntu user and its SSH connections instead?)

### Install Open MPI
Then, install Open MPI:

```shell
sudo apt-get install openmpi-bin
```

edit /etc/hosts on all servers. For example, for the parent node:

#MPI CLUSTERS
x.x.x.x manager
x.x.x.x node1
x.x.x.x node2
x.x.x.x node3

and for the child nodes:

#MPI CLUSTERS
x.x.x.x manager
x.x.x.x worker1

## Useful links

# Cloud_hpc
A repo with notes, scripts, and source code for running hpc codes on clusters of VMs

# VM cluster set up
In my case the cloud is set up in OpenStack. We are using one external and one internal network There is one VM connected to both the external and internal network, and the rest are only connected to the internal network

## Launching an instance and connecting to it through SSH
Before launching an instance configure security rules for instances as described here:
https://docs.openstack.org/horizon/queens/user/configure-access-and-security-for-instances.html
Save the SSH key to your local machine. 

Then launch a new instance, specifying the created security rules and SSH key. As described here:
Link
(Last part about floating IPs is not necessary)

Connect to instance using:
ssh -i SSH.pem ubuntu@x.x.x.x

## Useful links

## Setting up an mpi cluster

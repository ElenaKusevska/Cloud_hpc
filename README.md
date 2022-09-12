# Cloud_hpc
A repo with notes, scripts, and source code for running hpc codes on clusters of VMs

# VM cluster set up
In my case the cloud is set up in OpenStack. We are using one external and one internal network There is one VM connected to both the external and internal network, and the rest are only connected to the internal network

## Important - provisioning instances and connecting to them with SSH in openstack
Link
Last part about floating IPs is not necessary
Note - don't use ubuntu 18.04 on a machine that will connect to two networks.
Link
Download ssh file and connect with:
command

## Useful links

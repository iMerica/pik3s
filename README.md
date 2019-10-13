# Pi K3s

Ansible playbook for deploying kubernetes to cluster of Raspberry Pis. I personally use this on a cluster of 
Raspberry Pi 4s, but earlier Raspberry Pis should work fine too.

# Requirements and Assumptions
- Latest Ansible (as of this writing)
- Raspberry Pis with SSH already enabled. (e.g `touch /boot/ssh` on all)

# Set up
- Clone this Repo and cd into the source.
- Update `./inventory` with your own IP addresses.
- Test the connection `ansible -m ping all`
- Apply the playbook `ansible-playbook main.yml`

## Optional
Connect to the cluster from your development computer
```
ssh <user>@<ip_address> sudo cat /etc/rancher/k3s/k3s.yaml > ~/.kube/pi_cluster.yml
export KUBECONFIG=$HOME/.kube/pi_cluster.yml
````



# FAQ
Q: I'm having trouble connecting to the cluster.

A: Update the ssh configuration as needed in `ansible.cfg`

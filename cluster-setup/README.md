# CREATE kube-master VM using gcloud command
## Cloud Shell or SDK or using the browser interface
Name: kube-master

Size: 50 GB 

Image:  Ubuntu 22.04 LTS 

Machine Type: e2-medium (2 vCPU, 4 GB memory)

# CREATE kube-worker VM using gcloud command
## Cloud Shell or SDK or using the browser interface
Name: kube-worker

Size: 50 GB 

Image:  Ubuntu 22.04 LTS

Machine Type: e2-medium (2 vCPU, 4 GB memory)

# You can use a region near you
https://cloud.google.com/compute/docs/regions-zones


# INSTALL kube-master
gcloud compute ssh kube-master

sudo -i

bash <(curl -s https://raw.githubusercontent.com/pathwaytipsorg/k8s-setup/main/cluster-setup/latest/install_master.sh)


# INSTALL kube-worker
gcloud compute ssh kube-worker

sudo -i

bash <(curl -s https://raw.githubusercontent.com/pathwaytipsorg/k8s-setup/main/cluster-setup/latest/install_worker.sh)

# Open Port (Firewall Rules to allow below TCP)
30000 to 40000

# containerd (Instead docker)
crictl ps

# kubernetes-ansible-setup
Ansible playbook for quick Kubernetes setup on a Linux node

Based on a Digital Ocean's tutorial [How To Create a Kubernetes 1.11 Cluster Using Kubeadm on Ubuntu 18.04 ](https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-1-11-cluster-using-kubeadm-on-ubuntu-18-04).

1. Install Ansible on your local machine (not the node you are intending to run Kubernetes).
2. For each of nodes add your `~/.ssh/id_rsa.pub` key to the `~/.ssh/authorized_keys` on the node so that Ansible can connect via SSH keys.
3. Test that you can actually connect to the node without password by `ssh root@ip.or.domain`.
4. Then use the `initial.yml` playbook and run it with `ansible-playbook -i hosts ./initial.yml`.
5. Follow with `ansible-playbook -i hosts ./kube-dependencies.yml`
6. Log to your node and confirm that `docker --version`, `kubectl`, `kubeadm` are installed correctly.

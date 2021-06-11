czstlocp001.dhl.com


### ELR
[210114-APP-6281](https://elm.dhl.com/request/1/210114-APP-6281/)
[210118-B2B-6522](https://elm.dhl.com/request/5/210118-B2B-6522/)
[210118-SEG-6508](https://elm.dhl.com/request/7/210118-SEG-6508/)

| VIP      |     URL |
|--------| ------ |
|165.72.137.177|     *.prod-int.apps.czstlocp001.dhl.com|
|165.72.181.44|    *.prod-dmz.apps.czstlocp001.dhl.com|
|165.72.137.178|    api.czstlocp001.dhl.com|
|165.72.137.179|    api-int.czstlocp001.dhl.com|
|165.72.137.180|    oauth-openshift.apps.czstlocp001.dhl.com|
|165.72.137.181|    *.apps.czstlocp001.dhl.com|


### DNS Records

| Hostname |  Subnet | Zone | VLAN name | VLAN Id |
|--------| ------ | -----| ------| ------ |
|czstllspc005204 - czstllspc005218|	2.253.115.160/27|	management zone internal|	ocp_mgmt1|768|
|czstllspc005225 - czstllspc005339|	2.253.94.0/25|	production app nodes internal|	opc_app_int|769|
|czstllspc005455 - czstllspc005462| 2.253.94.128/25|	production egress internal|ocp_prod_int_egress1|770|
|czstllspc005340 - czstllspc005430|	2.253.93.0/25|	production app nodes dmz|	dmz_ocp_app|765|
|czstllspc005463 - czstllspc005470|	2.253.93.128/25|	production egress dmz|	dmz_ocp_prod_ea_egress1|766|
|czstllspc005204-b - czstllspc005339-b, czstllspc005455-b - czstllspc005462-b,czstllspc005340-b - czstllspc005430-b, czstllspc005463-b - czstllspc005470-b|	2.253.95.0/24|	Barn-mgmt-internal|ocp_prod_int_barn1|362|


```
This Incident was cloned from Incident INC35376257


INC37072424

Request to create DNS A records and SRV records for new OpenShift 4 PRG DR cluster installation

For new Openshift V4 PRG-DR cluster, could you please create following DNS A records and SRV records ?

etcd-0.czstlocp001.dhl.com 2.253.115.172
etcd-1.czstlocp001.dhl.com 2.253.115.173
etcd-2.czstlocp001.dhl.com 2.253.115.174


And can you please create following SRV records:

_etcd-server-ssl._tcp.czstlocp001.dhl.com. 86400 IN SRV 0 10 2380 etcd-0.czstlocp001.dhl.com
_etcd-server-ssl._tcp.czstlocp001.dhl.com. 86400 IN SRV 0 10 2380 etcd-1.czstlocp001.dhl.com
_etcd-server-ssl._tcp.czstlocp001.dhl.com. 86400 IN SRV 0 10 2380 etcd-2.czstlocp001.dhl.com
```


### Management internal (VLAN OCP_Mgmt_Zone_Int)
```

Bastion (Ansible) host RHEL, deployed via ITS Private Cloud
2 vCPU, 8 GB RAM, 250 GB Disk
2.253.115.175    czstllspc005204.prg-dc.dhl.com

Bootstrap Node RHCOS
4 vCPU, 16 GB RAM, 120 GB Disk
2.253.115.190   czstlap0080.prg-dc.dhl.com

Master Node 1 RHCOS
4 vCPU, 16 GB RAM, 120 GB Disk
2.253.115.172    czstlap0081.prg-dc.dhl.com

Master Node 2 RHCOS
4 vCPU, 16 GB RAM, 120 GB Disk
2.253.115.173    czstlap0082.prg-dc.dhl.com

Master Node 3 RHCOS
4 vCPU, 16 GB RAM, 120 GB Disk
2.253.115.174    czstlap0083.prg-dc.dhl.com

Registry 1 RHEL, deployed via ITS Private Cloud
8 CPU, 16 GB RAM, 256 GB
2.253.115.176 czstllspc005205.prg-dc.dhl.com

Registry 2, deployed via ITS Private Cloud
8 CPU, 16 GB RAM, 256 GB
2.253.115.177 czstllspc005206.prg-dc.dhl.com

EFK 1, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 50 GB / 200GB / 200GB / 900GB / 900GB (5 disks)
2.253.115.178    czstllspc005207.prg-dc.dhl.com

EFK 2, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 50 GB / 200GB / 200GB / 900GB / 900GB (5 disks)
2.253.115.179    czstllspc005208.prg-dc.dhl.com

EFK 3, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 50 GB / 200GB / 200GB / 900GB / 900GB (5 disks)
2.253.115.180    czstllspc005209.prg-dc.dhl.com
```


### Apps internal (VLAN Name opc_app_int)
```
Router 1, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 250 GB
2.253.94.12 czstllspc005225.prg-dc.dhl.com

Router 2, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 250 GB
2.253.94.13 czstllspc005226.prg-dc.dhl.com

Ceph node 1, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 250 GB, 500 GB
2.253.94.14 czstllspc005227.prg-dc.dhl.com

Ceph node 2, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 250 GB, 500 GB
2.253.94.15 czstllspc005228.prg-dc.dhl.com

Ceph node 3, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 250 GB, 500 GB
2.253.94.16 czstllspc005229.prg-dc.dhl.com

Compute node 1, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 256 GB
2.253.94.17 czstllspc005230.prg-dc.dhl.com

Compute node 2, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 256 GB
2.253.94.18 czstllspc005231.prg-dc.dhl.com

```

### Egress internal (VLAN Name ocp_prod_int_egress1)
```
Egress router 1, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 256 GB
2.253.94.140 czstllspc005455.prg-dc.dhl.com

Egress router 2, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 256 GB
2.253.94.141 czstllspc005456.prg-dc.dhl.com
```

### Apps DMZ (VLAN Name dmz_ocp_app)
```
Router 1, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 250 GB
2.253.93.12 czstllspc005340.prg-dc.dhl.com

Router 2, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 250 GB
2.253.93.13 czstllspc005341.prg-dc.dhl.com

Compute node 1, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 256 GB
2.253.93.14 czstllspc005342.prg-dc.dhl.com

Compute node 2, deployed via ITS Private Cloud
16 CPU, 64 GB RAM, 256 GB
2.253.93.15 czstllspc005343.prg-dc.dhl.com
```
### Egress DMZ (VLAN Name dmz_ocp_prod_ea_egress1)nmap -sn 
```
Egress router 1, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 250 GB
2.253.93.140 czstllspc005463.prg-dc.dhl.com

Egress router 2, deployed via ITS Private Cloud
8 CPU, 8 GB RAM, 250 GB
2.253.93.141 czstllspc005464.prg-dc.dhl.com
```


### Preparing the Bastion host

PLEASE MAKE SNAPSHOTS OF VMs BEFORE STARTING INSTALLATION!!!

```bash
# lvextend -L +13G /dev/mapper/rootdg-var -r
# yum install subscription-manager
# cp /etc/rhsm/rhsm.conf /etc/rhsm/rhsm.conf.orig
# sed -i -e 's#^[ 	]*proxy_hostname[ 	]*=.*#proxy_hostname = b2b-http.dhl.com#' -e 's#^[ 	]*proxy_port[ 	]*=.*#proxy_port = 8080#' -e 's#^[ 	]*baseurl[ 	]*=.*#baseurl = https://cdn.redhat.com:443#' /etc/rhsm/rhsm.conf
# subscription-manager register --org=11134574 --activationkey=ocp_app_nodes
# subscription-manager refresh
# subscription-manager list --available --matches '*OpenShift*'
# subscription-manager attach --pool=8a85f99b73354297017347659a3e450d
# subscription-manager repos --disable="*"
# yum-config-manager --disable \*
# subscription-manager repos --enable="rhel-7-server-rpms" --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ansible-2.9-rpms" --enable="rhel-7-server-ose-4.5-rpms"
# yum clean all --enablerepo='*' --verbose
# yum makecache
# yum update
# yum -y install podman httpd-tools httpd openshift-ansible openshift-clients jq git
---
```
Get pull secret from [cloud.redhat.com](https://cloud.redhat.com/openshift/install/pull-secret)
and save it to the file pull_secret.json on the bastion host.

Download openshift-install program and unpack it.

```bash
$ HTTPS_PROXY=http://b2b-http.dhl.com:8080 curl -O https://mirror.openshift.com/pub/openshift-v4/clients/ocp/4.5.20/openshift-install-linux-4.5.20.tar.gz
$ cd /home/ans && tar xvzf openshift-install-linux-4.5.20.tar.gz
```

### Prepare VMs for OCP 4 cluster installation

Please see the instructions [here](https://docs.openshift.com/container-platform/4.5/installing/installing_vsphere/installing-restricted-networks-vsphere.html#installation-vsphere-machines_installing-restricted-networks-vsphere).

vAPP_settings - INC37081230 , INC37222923

**You need to have appliances deployed and vAPP options applied in vSphere.**

**ATTENTION**

Be aware that: "The Ignition config files that the installation program
generates contain certificates that expire after 24 hours. You must complete
your cluster installation and keep the cluster running for 24 hours in a
non-degraded state to ensure that the first certificate rotation has finished."

This means that you do instalation in one day, or you revert to latest snapshot
and repeat steps below again.

On Bastion host czstllspc005204.prg-dc.dhl.com

Pre-defined DHL sample [install-config.yaml](https://git.dhl.com/bimodal-coc/czchoocp001.dhl.com/blob/master/misc/install-config.yaml) file.

Based on https://access.redhat.com/solutions/4931551 
Put all subnet CIDR to no_proxy variable in `install-config.yaml` as well. 

```bash
# ssh-keygen -t rsa -b 4096 -N '' -f id_rsa_rhcos
# mkdir installation_directory/
# cp install-config.yaml czstlocp001-installation/
# ./openshift-install create manifests --dir=czstlocp001-installation
WARNING   Discarding the Master Ignition Config that was provided in the target directory because its dependencies are dirty and it needs to be regenerated
INFO Consuming Install Config from target directory
INFO Consuming Master Ignition Config from target directory
WARNING Making control-plane schedulable by setting MastersSchedulable to true for Scheduler cluster settings

# vim cluster-scheduler-02-config.yml
# diff -u cluster-scheduler-02-config.yml cluster-scheduler-02-config.yml.orig
--- cluster-scheduler-02-config.yml     2021-02-03 12:08:08.130556217 +0100
+++ cluster-scheduler-02-config.yml.orig        2021-02-03 12:07:51.776554687 +0100
@@ -4,7 +4,7 @@
   creationTimestamp: null
   name: cluster
 spec:
-  mastersSchedulable: false
+  mastersSchedulable: true
   policy:
     name: ""
 status: {}

#  ./openshift-install create ignition-configs --dir=czstlocp001-installation
WARNING Discarding the Bootstrap Ignition Config that was provided in the target directory because its dependencies are dirty and it needs to be regenerated
INFO Consuming Worker Machines from target directory
INFO Consuming Common Manifests from target directory
INFO Consuming OpenShift Install (Manifests) from target directory
INFO Consuming Master Machines from target directory
INFO Consuming Openshift Manifests from target directory

# cp installation_directory/bootstrap.ign  /var/www/html/bootstrap.ign
# cp installation_directory/master.ign /var/www/html/master.ign
# cp installation_directory/worker.ign /var/www/html/worker.ign
# chmod a+r /var/www/html/*ign
# systemctl enable httpd
#  systemctl start httpd
```

**ATTENTION**
MAKE SNAPSHOTS OF APPLIANCES BEFORE USING THEM

Boot bootstrap machine first, then masters. Break boot process in grub and
edit grub options as described below.

Boot lines for grub for appliances to apply static IPs:

```
ip=2.253.115.190::2.253.115.161:255.255.255.224:czstlap0080.prg-dc.dhl.com:ens192:none nameserver=165.72.12.88 nameserver=165.72.136.88
ip=2.253.115.172::2.253.115.161:255.255.255.224:czstlap0081.prg-dc.dhl.com:ens192:none nameserver=165.72.12.88 nameserver=165.72.136.88
ip=2.253.115.173::2.253.115.161:255.255.255.224:czstlap0082.prg-dc.dhl.com:ens192:none nameserver=165.72.12.88 nameserver=165.72.136.88
ip=2.253.115.174::2.253.115.161:255.255.255.224:czstlap0083.prg-dc.dhl.com:ens192:none nameserver=165.72.12.88 nameserver=165.72.136.88
```
### Troubleshooting BIGIP
Problem with api-int URL - [INC37296350](https://servicenow.dhl.com/nav_to.do?uri=%2Fincident.do%3Fsys_id%3D377c2f061b4ae450a9ea744c8b4bcbaf%26sysparm_stack%3D%26sysparm_view%3D)
                        - [INC37296350](https://servicenow.dhl.com/nav_to.do?uri=%2Fincident.do%3Fsys_id%3D377c2f061b4ae450a9ea744c8b4bcbaf%26sysparm_stack%3D%26sysparm_view%3D)

```
ssh -i .ssh/id_rsa_rhcos core@czstlap0080.prg-dc.dhl.com journalctl -b -f -u release-image.service -u bootkube.service
ssh -i .ssh/id_rsa_rhcos core@czstlap0081.prg-dc.dhl.com
ssh -i .ssh/id_rsa_rhcos core@czstlap0082.prg-dc.dhl.com
ssh -i .ssh/id_rsa_rhcos core@czstlap0083.prg-dc.dhl.com
```

Once the access is verified, please run the command below.


```
./openshift-install --dir=czstlocp001-installation wait-for bootstrap-complete --log-level=debug
DEBUG OpenShift Installer 4.5.20
DEBUG Built from commit b7489c1afcca2aee02f27a11f8f93b8dc3c5124c
INFO Waiting up to 20m0s for the Kubernetes API at https://api.czstlocp001.dhl.com:6443...
INFO API v1.18.3+ca4017d up
INFO Waiting up to 40m0s for bootstrapping to complete...
DEBUG Bootstrap status: complete
INFO It is now safe to remove the bootstrap resources
INFO Time elapsed: 0s
```
Turn off bootstrap node
```
ssh -i .ssh/id_rsa_rhcos core@czstlap0080.prg-dc.dhl.com sudo poweroff
```

Verify control plane installation (there must be 3 nodes in Ready status and a bunch of pods. Most of the operators must be in Available state).

```
# export KUBECONFIG=/home/ans/czstlocp001-installation/auth/kubeconfig
# oc get nodes -o wide
# oc get pods -A
# oc get clusteroperators
# oc get clusterversion

[root@czstllspc005204 ans]# oc --kubeconfig=/home/ans/czstlocp001-installation/auth/kubeconfig get clusterversion
NAME      VERSION   AVAILABLE   PROGRESSING   SINCE   STATUS
version             False       True          134m    Unable to apply 4.5.20: some cluster operators have not yet rolled out

[root@czstllspc005204 ans]# oc --kubeconfig=/home/ans/czstlocp001-installation/auth/kubeconfig get clusterversion -o jsonpath='{range .items[*]}{range .status.conditions[*]}{.message}{"\n"}{end}{"\n"}{end}'

Some cluster operators are still updating: authentication, console, ingress, kube-storage-version-migrator, monitoring
Unable to apply 4.5.20: some cluster operators have not yet rolled out

```
Configure NTP synchronization on master nodes as described [here](https://docs.openshift.com/container-platform/4.5/installing/install_config/installing-customizing.html#installation-special-config-chrony_installing-customizing). Configuration file [here](https://git.dhl.com/bimodal-coc/czchooct002.dhl.com/blob/master/misc/99-masters-chrony-configuration.yaml). Be aware that nodes will be rebooted after you run "oc apply command".

```
oc --kubeconfig=/home/ans/czstlocp001-installation/auth/kubeconfig apply -f 99-masters-chrony-configuration.yaml
machineconfig.machineconfiguration.openshift.io/masters-chrony-configuration created
oc --kubeconfig=/home/ans/czstlocp001-installation/auth/kubeconfig get nodes -w
NAME                         STATUS   ROLES    AGE     VERSION
czstlap0081.prg-dc.dhl.com   Ready    master   6h17m   v1.18.3+ca4017d
czstlap0082.prg-dc.dhl.com   Ready    master   6h10m   v1.18.3+ca4017d
czstlap0083.prg-dc.dhl.com   Ready    master   6h6m    v1.18.3+ca4017d
czstlap0083.prg-dc.dhl.com   Ready    master   6h6m    v1.18.3+ca4017d
czstlap0082.prg-dc.dhl.com   Ready    master   6h11m   v1.18.3+ca4017d
czstlap0082.prg-dc.dhl.com   Ready    master   6h11m   v1.18.3+ca4017d
czstlap0082.prg-dc.dhl.com   Ready,SchedulingDisabled   master   6h11m   v1.18.3+ca4017d
czstlap0082.prg-dc.dhl.com   Ready,SchedulingDisabled   master   6h11m   v1.18.3+ca4017d
czstlap0083.prg-dc.dhl.com   Ready                      master   6h7m    v1.18.3+ca4017d
```
Nodes will be ready status after some time

```
oc --kubeconfig=/home/ans/czstlocp001-installation/auth/kubeconfig get nodes
NAME                         STATUS   ROLES    AGE     VERSION
czstlap0081.prg-dc.dhl.com   Ready    master   6h22m   v1.18.3+ca4017d
czstlap0082.prg-dc.dhl.com   Ready    master   6h15m   v1.18.3+ca4017d
czstlap0083.prg-dc.dhl.com   Ready    master   6h11m   v1.18.3+ca4017d
```

Verify time synchronization (status should be Normal).

```
for i in $(oc --kubeconfig=/home/ans/czstlocp001-installation/auth/kubeconfig get nodes --no-headers -o custom-columns=NAME:.metadata.name); do echo "### $i";ssh -i /home/ans/.ssh/id_rsa_rhcos core@${i} chronyc tracking | grep status; done
### czstlap0081.prg-dc.dhl.com
Leap status     : Normal
### czstlap0082.prg-dc.dhl.com
Leap status     : Normal
### czstlap0083.prg-dc.dhl.com
Leap status     : Normal
```
#### Installing worker (compute) nodes

**ATTENTION**

MAKE SNAPSHOTS OF COMPUTE NODES BEFORE USING THEM.

On bastion host first prepare things for installation as described at
https://docs.openshift.com/container-platform/4.5/machine_management/adding-rhel-compute.html

On Bastion (Ansible host) create Inventory file.

```
[ans@czstllspc005204 ~]$ cat /etc/ansible/hosts
[all:vars]
ansible_user=ans
ansible_become=True

openshift_kubeconfig_path="/home/ans/czstlocp001-installation/auth/kubeconfig"

[registry]
czstllspc005205.prg-dc.dhl.com
czstllspc005206.prg-dc.dhl.com

[efk]
czstllspc005207.prg-dc.dhl.com
czstllspc005208.prg-dc.dhl.com
czstllspc005209.prg-dc.dhl.com

[prom]
czstllspc005207.prg-dc.dhl.com
czstllspc005208.prg-dc.dhl.com
czstllspc005209.prg-dc.dhl.com

[infra]
czstllspc005225.prg-dc.dhl.com
czstllspc005226.prg-dc.dhl.com

[ceph]
czstllspc005227.prg-dc.dhl.com
czstllspc005228.prg-dc.dhl.com
czstllspc005229.prg-dc.dhl.com

[app]
czstllspc005230.prg-dc.dhl.com
czstllspc005231.prg-dc.dhl.com

[egress]
czstllspc005455.prg-dc.dhl.com
czstllspc005456.prg-dc.dhl.com

[new_workers]
czstllspc005205.prg-dc.dhl.com
czstllspc005206.prg-dc.dhl.com
czstllspc005207.prg-dc.dhl.com
czstllspc005208.prg-dc.dhl.com
czstllspc005209.prg-dc.dhl.com
czstllspc005225.prg-dc.dhl.com
czstllspc005226.prg-dc.dhl.com
czstllspc005227.prg-dc.dhl.com
czstllspc005228.prg-dc.dhl.com
czstllspc005229.prg-dc.dhl.com
czstllspc005230.prg-dc.dhl.com
czstllspc005231.prg-dc.dhl.com
czstllspc005455.prg-dc.dhl.com
czstllspc005456.prg-dc.dhl.com
```
Establish ssh host authenticity.
```bash
$ ansible new_workers --list-hosts | grep czstllspc | while read i; do a=$(getent ahostsv4 $i | awk '/STREAM/{print $3 "," $1}'); ssh-keyscan  -t ecdsa-sha2-nistp256 $a | grep -v ^# >> ~/.ssh/known_hosts; done
```

Preparing the nodes before the installation.

```
ansible new_workers -m shell -a "grep vg /etc/fstab"
ansible efk -m shell -a "vgs"
ansible ceph -m shell -a "vgs"
ansible efk -m shell -a "grep vg /etc/fstab"
ansible ceph -m shell -a "grep vg /etc/fstab"
ansible new_workers -m lineinfile -a "dest=/etc/fstab state=absent regexp='\/dev\/vg1*'"
ansible new_workers -m shell -a "umount /mnt/disk2"
ansible new_workers -m lvol -a "vg=vg1 lv=lv01 state=absent force=yes"
ansible new_workers -m shell -a "vgremove -y vg1"
ansible new_workers -m shell -a "yum clean all --enablerepo='*' --verbose; yum makecache"
ansible new_workers -m shell -a "lvextend -L +13G /dev/mapper/rootdg-var -r"
ansible new_workers -m shell -a "lvextend -L +4G /dev/mapper/rootdg-varlog -r"
ansible-playbook subscribe-rhsm.yml |& tee -a subscribe-rhsm.log [for registering with RH using Proxy]
ansible new_workers -m yum -a "name=subscription-manager state=latest"
ansible new_workers  -m shell -a 'subscription-manager list'
ansible new_workers  -m shell -a 'subscription-manager identity'
ansible new_workers -m shell -a "subscription-manager repos --disable='*'"
ansible new_workers -m shell -a "yum-config-manager --disable '*'"
ansible new_workers -m shell -a "subscription-manager repos --enable='rhel-7-server-rpms' --enable='rhel-7-server-extras-rpms' --enable='rhel-7-server-ose-4.5-rpms'"
ansible new_workers -m shell -a "yum clean all --enablerepo='*' --verbose; yum makecache"
ansible new_workers -m yum -a "name=selinux-policy,selinux-policy-targeted state=present"
ansible new_workers -m yum -a "name='*' state=latest"
ansible new_workers -m shell -a "systemctl disable --now firewalld.service"
```
More details of the bastion host configuration described [here](https://docs.openshift.com/container-platform/4.5/machine_management/user_infra/adding-rhel-compute.html).

Disable swap.
```bash
$ ansible new_workers -m shell -a "swapoff -a"
```

Comment out swap line in "/etc/fstab".
```bash
$ ansible new_workers -m shell -a "sed -i -e 's@^/dev/mapper/rootdg-swap@#/dev/mapper/rootdg-swap@g' /etc/fstab"
```

Change "selinux=0" to "selinux=1" in "/etc/default/grub".
```bash
$ ansible new_workers -m shell -a "sed -i -e 's/selinux=0/selinux=1/g' /etc/default/grub"
```

Create grub config.
```bash
$ ansible new_workers -m shell -a "grub2-mkconfig -o /etc/grub2.cfg"
```

Edit "/etc/selinux/config" to enable selinux enforcing.
```bash
$ ansible new_workers -m shell -a "sed -i -e 's@^SELINUX=.*@SELINUX=enforcing@g' /etc/selinux/config"
$ ansible new_workers -m shell -a "sed -i -e 's@^SELINUXTYPE=.*@SELINUXTYPE=targeted@g' /etc/selinux/config"
```
Enable ipv4 forwarding.

Replace "net.ipv4.ip_forward=0" with "net.ipv4.ip_forward=1" in
"/etc/sysctl.conf" so change will persist across reboots.
```bash
$ ansible new_workers -m shell -a "sed -i -e 's@^net.ipv4.ip_forward=0@net.ipv4.ip_forward=1@g' /etc/sysctl.conf"
```

Take care of 200 GB disk in the machine for later usage.
```bash
$ ansible new_workers -m shell -a "wipefs -a /dev/sdb"
$ ansible new_workers -m shell -a "pvcreate /dev/sdb"
$ ansible new_workers -m shell -a "vgextend rootdg /dev/sdb"
$ ansible new_workers -m shell -a "lvextend -L +100G /dev/mapper/rootdg-var -r"
```

##### EFK NODES

```
ansible efk -m shell -a "umount /mnt/disk3;umount /mnt/disk4;umount /mnt/disk5"
ansible efk -m shell -a "rmdir /mnt/disk?"
ansible efk -m shell -a "lvremove -y vg3/lv01; lvremove -y vg4/lv01"
ansible efk -m shell -a "vgremove -y vg3; vgremove -y vg4"
ansible efk -m shell -a "vgcreate elasticsearch /dev/sdd1 /dev/sde1"
ansible efk -m shell -a "lvcreate -n elasticsearch -l 100%FREE -y elasticsearch"
```

Reboot the nodes.
```
ansible new_workers -m shell -a "sync && sync && reboot"
```

Verify changes:

```
ansible new_workers -m shell -a "sestatus"
ansible new_workers -m shell -a "sestatus | grep -E 'name|mode'"
ansible new_workers -m shell -a "sysctl net.ipv4.ip_forward"
```

Start a tmux session so that the session won't endup even after the network disconnection.

```
# tmux new -s  ocp_v4.5_PRG_DR_install
# tmux ls
ocp_v4.5_PRG_DR_install: 1 windows (created Mon Feb  8 05:22:49 2021) [206x55] (attached)
```

Scale up cluster:

```
cd /usr/share/ansible/openshift-ansible
# ansible-playbook playbooks/scaleup.yml -vvv |& tee -a /home/ans/Aneesh/scaleup/scaleup.log
```

**Validation**
Verify the scale up status, use commands to view all nodes ready and all CSRs are approved unless you have to approve the CSRs manually.


```
$ oc get nodes -o wide
$ oc get csr
```

```
$ oc get csr
NAME        AGE   SIGNERNAME                                    REQUESTOR                                                                   CONDITION
csr-7ggjp   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005455.prg-dc.dhl.com                                  Approved,Issued
csr-7rqz8   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005229.prg-dc.dhl.com                                  Approved,Issued
csr-85tws   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005207.prg-dc.dhl.com                                  Approved,Issued
csr-8bf8q   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005226.prg-dc.dhl.com                                  Approved,Issued
csr-8ljzw   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005456.prg-dc.dhl.com                                  Approved,Issued
csr-8rtmz   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005228.prg-dc.dhl.com                                  Approved,Issued
csr-9q2xc   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-cd8jk   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-dcjxq   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005230.prg-dc.dhl.com                                  Approved,Issued
csr-dh2tk   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005206.prg-dc.dhl.com                                  Approved,Issued
csr-dqxtr   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-f5x4v   23m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-f9rh7   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005208.prg-dc.dhl.com                                  Approved,Issued
csr-j6pxn   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-jqn4w   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005225.prg-dc.dhl.com                                  Approved,Issued
csr-lnw5d   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-njfkp   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-nx7p7   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-pj9rk   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005227.prg-dc.dhl.com                                  Approved,Issued
csr-pp6b6   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005205.prg-dc.dhl.com                                  Approved,Issued
csr-ql4z4   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-rd6cw   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005209.prg-dc.dhl.com                                  Approved,Issued
csr-sr29s   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-szs2p   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-tm2gf   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-wqwr2   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-wvr2n   24m   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-xd9qs   23m   kubernetes.io/kubelet-serving                 system:node:czstllspc005231.prg-dc.dhl.com                                  Approved,Issued

$ oc get nodes -o wide
NAME                             STATUS   ROLES    AGE    VERSION           INTERNAL-IP     EXTERNAL-IP   OS-IMAGE                                                       KERNEL-VERSION                 CONTAINER-RUNTIME
czstlap0081.prg-dc.dhl.com       Ready    master   4d6h   v1.18.3+ca4017d   2.253.115.172   <none>        Red Hat Enterprise Linux CoreOS 45.82.202011131531-0 (Ootpa)   4.18.0-193.29.1.el8_2.x86_64   cri-o://1.18.4-4.rhaos4.5.git6dee389.el8
czstlap0082.prg-dc.dhl.com       Ready    master   4d6h   v1.18.3+ca4017d   2.253.115.173   <none>        Red Hat Enterprise Linux CoreOS 45.82.202011131531-0 (Ootpa)   4.18.0-193.29.1.el8_2.x86_64   cri-o://1.18.4-4.rhaos4.5.git6dee389.el8
czstlap0083.prg-dc.dhl.com       Ready    master   4d6h   v1.18.3+ca4017d   2.253.115.174   <none>        Red Hat Enterprise Linux CoreOS 45.82.202011131531-0 (Ootpa)   4.18.0-193.29.1.el8_2.x86_64   cri-o://1.18.4-4.rhaos4.5.git6dee389.el8
czstllspc005205.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.115.176   <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005206.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.115.177   <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005207.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.115.178   <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005208.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.115.179   <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005209.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.115.180   <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005225.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.12     <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005226.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.13     <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005227.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.14     <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005228.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.15     <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005229.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.16     <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005230.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.17     <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005231.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.18     <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005455.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.140    <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
czstllspc005456.prg-dc.dhl.com   Ready    worker   23m    v1.18.3+65bd32d   2.253.94.141    <none>        OpenShift Enterprise                                           3.10.0-1160.15.2.el7.x86_64    cri-o://1.18.4-6.rhaos4.5.gitbe796d1.el7
```

To approve all pending CSRs, run the following command(Just incase any pending left, if all approved no need to excecute this)

```
$ oc get csr -o go-template='{{range .items}}{{if not .status}}{{.metadata.name}}{{"\n"}}{{end}}{{end}}' | xargs oc adm certificate approve
```
Verify the correct cluster setup using following commands.

```
$ oc get clusteroperators
$ oc get clusterversion
```

```
$ oc get clusteroperators
NAME                                       VERSION   AVAILABLE   PROGRESSING   DEGRADED   SINCE
authentication                             4.5.20    True        False         False      28m
cloud-credential                           4.5.20    True        False         False      4d7h
cluster-autoscaler                         4.5.20    True        False         False      4d6h
config-operator                            4.5.20    True        False         False      4d6h
console                                    4.5.20    True        False         False      33m
csi-snapshot-controller                    4.5.20    True        False         False      4d
dns                                        4.5.20    True        False         False      4d6h
etcd                                       4.5.20    True        False         False      4d6h
image-registry                             4.5.20    True        False         False      4d6h
ingress                                    4.5.20    True        False         False      36m
insights                                   4.5.20    True        False         False      4d6h
kube-apiserver                             4.5.20    True        False         False      4d6h
kube-controller-manager                    4.5.20    True        False         False      4d6h
kube-scheduler                             4.5.20    True        False         False      4d6h
kube-storage-version-migrator              4.5.20    True        False         False      37m
machine-api                                4.5.20    True        False         False      4d6h
machine-approver                           4.5.20    True        False         False      4d6h
machine-config                             4.5.20    True        False         False      4d6h
marketplace                                4.5.20    True        False         False      4d
monitoring                                 4.5.20    True        False         False      34m
network                                    4.5.20    True        False         False      4d6h
node-tuning                                4.5.20    True        False         False      4d6h
openshift-apiserver                        4.5.20    True        False         False      22h
openshift-controller-manager               4.5.20    True        False         False      4d6h
openshift-samples                          4.5.20    True        False         False      4d6h
operator-lifecycle-manager                 4.5.20    True        False         False      4d6h
operator-lifecycle-manager-catalog         4.5.20    True        False         False      4d6h
operator-lifecycle-manager-packageserver   4.5.20    True        False         False      4d
service-ca                                 4.5.20    True        False         False      4d6h
storage                                    4.5.20    True        False         False      4d6h
```

```
$ oc get clusterversion
NAME      VERSION   AVAILABLE   PROGRESSING   SINCE   STATUS
version   4.5.20    True        False         35m     Cluster version is 4.5.20

```


Move new installed OCP4 RHEL nodes in ansible inventory file from group "[new_workers]" to "[workers]".

```
[all:vars]
ansible_user=ans
ansible_become=True

openshift_kubeconfig_path="/home/ans/czstlocp001-installation/auth/kubeconfig"

[registry]
czstllspc005205.prg-dc.dhl.com
czstllspc005206.prg-dc.dhl.com

[efk]
czstllspc005207.prg-dc.dhl.com
czstllspc005208.prg-dc.dhl.com
czstllspc005209.prg-dc.dhl.com

[prom]
czstllspc005207.prg-dc.dhl.com
czstllspc005208.prg-dc.dhl.com
czstllspc005209.prg-dc.dhl.com

[infra]
czstllspc005225.prg-dc.dhl.com
czstllspc005226.prg-dc.dhl.com

[ceph]
czstllspc005227.prg-dc.dhl.com
czstllspc005228.prg-dc.dhl.com
czstllspc005229.prg-dc.dhl.com

[app]
czstllspc005230.prg-dc.dhl.com
czstllspc005231.prg-dc.dhl.com

[egress]
czstllspc005455.prg-dc.dhl.com
czstllspc005456.prg-dc.dhl.com

[workers]
czstllspc005205.prg-dc.dhl.com
czstllspc005206.prg-dc.dhl.com
czstllspc005207.prg-dc.dhl.com
czstllspc005208.prg-dc.dhl.com
czstllspc005209.prg-dc.dhl.com
czstllspc005225.prg-dc.dhl.com
czstllspc005226.prg-dc.dhl.com
czstllspc005227.prg-dc.dhl.com
czstllspc005228.prg-dc.dhl.com
czstllspc005229.prg-dc.dhl.com
czstllspc005230.prg-dc.dhl.com
czstllspc005231.prg-dc.dhl.com
czstllspc005455.prg-dc.dhl.com
czstllspc005456.prg-dc.dhl.com

[new_workers]
```
**Assigning labels and creating routers**

```
[ans@czstllspc005204 ~]$ oc get nodes -L network -L stage -L zone -L router
NAME                             STATUS   ROLES    AGE    VERSION           NETWORK    STAGE   ZONE     ROUTER
czstlap0081.prg-dc.dhl.com       Ready    master   4d7h   v1.18.3+ca4017d   internal           mgmt
czstlap0082.prg-dc.dhl.com       Ready    master   4d7h   v1.18.3+ca4017d   internal           mgmt
czstlap0083.prg-dc.dhl.com       Ready    master   4d7h   v1.18.3+ca4017d   internal           mgmt
czstllspc005205.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal           mgmt     true
czstllspc005206.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal           mgmt     true
czstllspc005207.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal           mgmt     false
czstllspc005208.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal           mgmt     false
czstllspc005209.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal           mgmt     false
czstllspc005225.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    app      true
czstllspc005226.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    app      true
czstllspc005227.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    ceph     false
czstllspc005228.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    ceph     false
czstllspc005229.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    ceph     false
czstllspc005230.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    app      false
czstllspc005231.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    app      false
czstllspc005455.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    egress   true
czstllspc005456.prg-dc.dhl.com   Ready    worker   75m    v1.18.3+65bd32d   internal   prod    egress   true
```

### Create routers

```
$oc apply -f router-default.yaml
Warning: oc apply should be used on resource created by either oc create --save-config or oc apply
ingresscontroller.operator.openshift.io/default configured

$ oc create -f router-prod-internal.yaml
ingresscontroller.operator.openshift.io/internal-prod-app created

Validation

$  oc get IngressController -n openshift-ingress-operator
NAME                AGE
default             5d23h
internal-prod-app   49s

$ oc get pod -n openshift-ingress
NAME                                        READY   STATUS    RESTARTS   AGE
router-default-84776bb455-4fggz             1/1     Running   0          23m
router-default-84776bb455-jt9fq             1/1     Running   0          24m
router-internal-prod-app-5db68f7dc9-hpss7   1/1     Running   0          9m55s
router-internal-prod-app-5db68f7dc9-tm5g4   1/1     Running   0          9m55s

```
Verify the correct cluster setup using following commands:
```
$ export KUBECONFIG=/home/ans/czstlocp001-installation/auth/kubeconfig
$ oc get co
NAME                                       VERSION   AVAILABLE   PROGRESSING   DEGRADED   SINCE
authentication                             4.5.20    True        False         False      41h
cloud-credential                           4.5.20    True        False         False      6d
cluster-autoscaler                         4.5.20    True        False         False      5d23h
config-operator                            4.5.20    True        False         False      5d23h
console                                    4.5.20    True        False         False      41h
csi-snapshot-controller                    4.5.20    True        False         False      5d17h
dns                                        4.5.20    True        False         False      5d23h
etcd                                       4.5.20    True        False         False      5d23h
image-registry                             4.5.20    True        False         False      5d23h
ingress                                    4.5.20    True        False         False      24m
insights                                   4.5.20    True        False         False      5d23h
kube-apiserver                             4.5.20    True        False         False      5d23h
kube-controller-manager                    4.5.20    True        False         False      5d23h
kube-scheduler                             4.5.20    True        False         False      5d23h
kube-storage-version-migrator              4.5.20    True        False         False      41h
machine-api                                4.5.20    True        False         False      5d23h
machine-approver                           4.5.20    True        False         False      5d23h
machine-config                             4.5.20    True        False         False      5d23h
marketplace                                4.5.20    True        False         False      5d17h
monitoring                                 4.5.20    True        False         False      41h
network                                    4.5.20    True        False         False      5d23h
node-tuning                                4.5.20    True        False         False      5d23h
openshift-apiserver                        4.5.20    True        False         False      2d15h
openshift-controller-manager               4.5.20    True        False         False      5d23h
openshift-samples                          4.5.20    True        False         False      5d23h
operator-lifecycle-manager                 4.5.20    True        False         False      5d23h
operator-lifecycle-manager-catalog         4.5.20    True        False         False      5d23h
operator-lifecycle-manager-packageserver   4.5.20    True        False         False      5d17h
service-ca                                 4.5.20    True        False         False      5d23h
storage                                    4.5.20    True        False         False      5d23h

$ oc get clusterversion
NAME      VERSION   AVAILABLE   PROGRESSING   SINCE   STATUS
version   4.5.20    True        False         41h     Cluster version is 4.5.20

$ oc get clusterversion -o jsonpath='{range .items[*]}{range .status.conditions[*]}{.message}{"\n"}{end}{"\n"}{end}'
Done applying 4.5.20
Cluster version is 4.5.20

$ oc get pod -n openshift-console
NAME                       READY   STATUS    RESTARTS   AGE
console-7744b55f76-2kwqw   1/1     Running   1          41h
console-7744b55f76-xkmw4   1/1     Running   1          41h
downloads-cfb6c966-2vsbz   1/1     Running   0          5d17h
downloads-cfb6c966-4sw7m   1/1     Running   0          5d17h

$ oc logs console-7744b55f76-2kwqw -n openshift-console
2021-02-08T11:43:49Z cmd/main: cookies are secure!
2021-02-08T11:43:49Z auth: error contacting auth provider (retrying in 10s): discovery through endpoint https://kubernetes.default.svc/.well-known/oauth-authorization-server failed: 404 Not Found
2021-02-08T11:43:59Z cmd/main: Binding to [::]:8443...
2021-02-08T11:43:59Z cmd/main: using TLS

$ curl -kv https://oauth-openshift.apps.czstlocp001.dhl.com
* About to connect() to oauth-openshift.apps.czstlocp001.dhl.com port 443 (#0)
*   Trying 165.72.121.249...
* Connected to oauth-openshift.apps.czstlocp001.dhl.com (165.72.121.249) port 443 (#0)
* Initializing NSS with certpath: sql:/etc/pki/nssdb
* skipping SSL peer certificate verification
* NSS: client certificate not found (nickname not specified)
* SSL connection using TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
* Server certificate:
*       subject: CN=*.apps.czstlocp001.dhl.com
*       start date: Feb 04 05:37:03 2021 GMT
*       expire date: Feb 04 05:37:04 2023 GMT
*       common name: *.apps.czstlocp001.dhl.com
*       issuer: CN=ingress-operator@1612417015
> GET / HTTP/1.1
> User-Agent: curl/7.29.0
> Host: oauth-openshift.apps.czstlocp001.dhl.com
> Accept: */*
>
< HTTP/1.1 403 Forbidden
< Cache-Control: no-cache, no-store, max-age=0, must-revalidate
< Content-Type: application/json
< Expires: 0
< Pragma: no-cache
< Referrer-Policy: strict-origin-when-cross-origin
< X-Content-Type-Options: nosniff
< X-Dns-Prefetch-Control: off
< X-Frame-Options: DENY
< X-Xss-Protection: 1; mode=block
< Date: Wed, 10 Feb 2021 05:10:18 GMT
< Content-Length: 233
<
{
  "kind": "Status",
  "apiVersion": "v1",
  "metadata": {

  },
  "status": "Failure",
  "message": "forbidden: User \"system:anonymous\" cannot get path \"/\"",
  "reason": "Forbidden",
  "details": {

  },
  "code": 403
* Connection #0 to host oauth-openshift.apps.czstlocp001.dhl.com left intact
}
```

### Day 2 Operations Guide
#### Configuring the custom console route

```
$ oc get consoles.operator.openshift.io
NAME      AGE
cluster   5d23h

Add 'Route,hostname' under "Management State" in "Spec" section by editing consoles.operator.openshift.io

$ oc edit consoles.operator.openshift.io
$ oc describe consoles.operator.openshift.io | grep -A3 "Spec:"
Spec:
  Management State:  Managed
  Route:
    Hostname:  console.apps.czstlocp001.dhl.com
    
Validate the custom console name console.apps.czstlocp001.dhl.com 

$ oc get routes -n openshift-console
NAME             HOST/PORT                                              PATH   SERVICES           PORT                    TERMINATION          WILDCARD
console          console-openshift-console.apps.czstlocp001.dhl.com            console-redirect   custom-route-redirect   edge/Redirect        None
console-custom   console.apps.czstlocp001.dhl.com                              console            https                   reencrypt/Redirect   None
downloads        downloads-openshift-console.apps.czstlocp001.dhl.com          downloads          http                    edge/Redirect        None
```

#### Configuring the HTPASSWD identity provider

oath.yaml in the misc folder.

```
$ htpasswd -c -B -b users.htpasswd admin Bl2Poor1hjmtjiog
Adding password for user admin
$ pwd
/home/ans/Aneesh/oauth
$ ll
total 4
-rw-r----- 1 ans ans 67 Feb 11 06:02 users.htpasswd
```

Assign cluster-admin cluster role to admin user.

```
$  oc adm policy add-cluster-role-to-user cluster-admin admin
clusterrole.rbac.authorization.k8s.io/cluster-admin added: "admin"
```

Adding the password file as secret:

```
$oc create secret generic htpass-secret --from-file=htpasswd=users.htpasswd -n openshift-config
secret/htpass-secret created

$ oc get secret -n openshift-config | grep htpass-secret
htpass-secret                         Opaque                                1      2m18s

$ oc apply -f oauth.yaml
Warning: oc apply should be used on resource created by either oc create --save-config or oc apply
oauth.config.openshift.io/cluster configured
```

More configuration details [here](https://docs.openshift.com/container-platform/4.5/authentication/identity_providers/configuring-htpasswd-identity-provider.html). 

**validation**

```
[ans@czstllspc005204 oauth]$ oc describe oauth.config.openshift.io/cluster | grep -A7 "Spec:"
Spec:
  Identity Providers:
    Htpasswd:
      File Data:
        Name:        htpass-secret
    Mapping Method:  claim
    Name:            htpasswd
    Type:            HTPasswd
```

### Configuring LDAP identity provider
### ldap integration
Create secret and configmap.

```
$ mkdir /home/ans/Aneesh/ldap-integration
$ cd ldap_integration/
```

Put the LDAP certificate in DPDHLMachineCAI3.pem you may copy from any ansible host where installation already completed.
```
$ vim DPDHLMachineCAI3.pem
```
Create secret ldap-secret in project openshift-config, bindpassword is the LDAP bindpassword collect it from already built cluster.
```
$ oc create secret generic ldap-secret --from-literal=bindPassword='xxxxxxxxxxx' -n openshift-config
secret/ldap-secret created

$ oc get secret  -n openshift-config | grep ldap-secret
ldap-secret                           Opaque                                1      8m6s
```
Create configmap ca-config-map in project openshift-config

```
$ oc create configmap ca-config-map --from-file=ca.crt=DPDHLMachineCAI3.pem -n openshift-config
configmap/ca-config-map created

[ans@czstllspc005204 ldap-integration]$ oc get cm -n openshift-config | grep ca-config-map
ca-config-map                      1      79s
```
Edit oauth cluster and append at the end of the file: add there LDAP identity provider configuration.

```
$ oc edit oauth/cluster
oauth.config.openshift.io/cluster edited

[ans@czstllspc005204 ldap-integration]$ oc get oauth/cluster -o yaml | grep -A20 "ldap:"
  - ldap:
      attributes:
        email:
        - mail
        id:
        - userPrincipalName
        name:
        - displayName
        - userPrincipalName
        preferredUsername:
        - userPrincipalName
      bindDN: CN=srv_czcho-openshift,OU=ServiceAccounts,OU=AdminAccounts,OU=Servers,DC=prg-dc,DC=dhl,DC=com
      bindPassword:
        name: ldap-secret
      ca:
        name: ca-config-map
      insecure: false
      url: ldaps://prg-dc.dhl.com:3269/?cn
    mappingMethod: claim
    name: ldap
    type: LDAP
```
For more details about LDAP integration refer to:[link](https://docs.openshift.com/container-platform/4.5/authentication/identity_providers/configuring-ldap-identity-provider.html)

### Adding API server certificates
Generate certificate request and fill the request form on https://cmc.dhl.com/tlsCertificates/request
To know more follow: [link](https://docs.openshift.com/container-platform/4.5/security/certificates/api-server.html)

```
$ sudo openssl req -new -newkey rsa:2048 -keyout api.czstlocp001.dhl.com_generated_key.txt -config api.czstlocp001.dhl.com_openssl-config.txt -out api.czstlocp001.dhl.com_generated_csr.txt
Generating a 2048 bit RSA private key
..............+++
......................................+++
writing new private key to 'api.czstlocp001.dhl.com_generated_key.txt'
Enter PEM pass phrase:
Verifying - Enter PEM pass phrase:
-----
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Common Name (domain to be signed, e. g. example.dhl.com) []:api.czstlocp001.dhl.com
Organizational Unit Name (enter in command line or leave blank) []:
Organization Name (please accept default) [Deutsche Post AG]:
Locality Name (please accept default) [Bonn]:
State or Province Name (please accept default) [Nordrhein-Westfalen]:
Country Name (please accept default) [DE]:
```

Befor you request for the certificate its wise to verify the CSR.
Following command will show the data you have provided in order to create the CSR and if the validation success it will provide output as "Verify OK" same applys for the private key.

```
$ sudo openssl req -text -noout -verify -in api.czstlocp001.dhl.com_generated_csr.txt | grep verify
verify OK
$ sudo openssl rsa -in api.czstlocp001.dhl.com_generated_key.txt -check | grep RSA
Enter pass phrase for api.czstlocp001.dhl.com_generated_key.txt:xxxx
writing RSA key
RSA key ok
```

Once CMC(Certificate Management Center) issued certificate,(probably in 1day or 2 days) you can download the PEM file.

### Download the PEM file.

The certificate file can contain one or more certificates in a chain. The certificate for the API server FQDN must be the first certificate in the file. It can then be followed with any intermediate certificates, and the file should end with the root CA certificate as shown below. The private key must be unencrypted. If your key is encrypted, decrypt it before importing it into OpenShift Container Platform using command.

```
[ans@czstllspc005204 certs]$ ./ssl_chain.sh api.czstlocp001.dhl.com.pem.crt
 0: subject= /C=DE/ST=Nordrhein-Westfalen/L=Bonn/O=Deutsche Post AG/CN=api.czstlocp001.dhl.com
issuer= /C=DE/O=Deutsche Post AG/CN=DPDHL Global TLS CA - I5
 1: subject= /C=DE/O=Deutsche Post AG/CN=DPDHL Global TLS CA - I5
issuer= /OU=GlobalSign Root CA - R3/O=GlobalSign/CN=GlobalSign
 2: subject= /OU=GlobalSign Root CA - R3/O=GlobalSign/CN=GlobalSign
issuer= /OU=GlobalSign Root CA - R3/O=GlobalSign/CN=GlobalSign

api.czstlocp001.dhl.com.pem.crt: OK
```
### The private key unencryption

```
openssl rsa -in ${encrypted}.key -out ${unencrypted}.key
$ sudo openssl rsa -in api.czstlocp001.dhl.com_generated_key.txt -out api.czstlocp001.dhl.com_generated_unencrypted.key.txt
Enter pass phrase for api.czstlocp001.dhl.com_generated_key.txt:xxxxx
writing RSA key
```
Using chain certificate and private key, create secret in the openshift-config namespace and patch apiserver.

```
$ cp api.czstlocp001.dhl.com.pem api.czstlocp001.dhl.com.pem.crt
$ oc create secret tls api-ssl-certificate --cert=api.czstlocp001.dhl.com.pem.crt --key=api.czstlocp001.dhl.com_generated_key_unencrypted.txt -n openshift-config
secret/api-ssl-certificate created
$ oc patch apiserver cluster --type=merge -p  '{"spec":{"servingCerts": {"namedCertificates":[{"names": ["api.czstlocp001.dhl.com"], "servingCertificate": {"name": "api-ssl-certificate"}}]}}}'
apiserver.config.openshift.io/cluster patched
```

**Validation**
### Verify that new configuration has a secret defined and api pods were restarted.
```
$ oc get secret -n openshift-config | grep api-ssl-certificate
api-ssl-certificate                   kubernetes.io/tls                     2      3d20h

$ oc get apiserver cluster -o yaml | grep -A7 "spec:"
spec:
  servingCerts:
    namedCertificates:
    - names:
      - api.czstlocp001.dhl.com
      servingCertificate:
        name: api-ssl-certificate

$ oc get po -o wide -n openshift-kube-apiserver | grep kube-apiserver
kube-apiserver-czstlap0081.prg-dc.dhl.com       4/4     Running     0          37m   2.253.115.172   czstlap0081.prg-dc.dhl.com   <none>           <none>
kube-apiserver-czstlap0082.prg-dc.dhl.com       4/4     Running     0          33m   2.253.115.173   czstlap0082.prg-dc.dhl.com   <none>           <none>
kube-apiserver-czstlap0083.prg-dc.dhl.com       4/4     Running     0          30m   2.253.115.174   czstlap0083.prg-dc.dhl.com   <none>           <none>

```
You can see that the **Server certificate** part is updated with our above action  as shown below:
```
ans@czstllspc005204 certs]$ curl -kv https://api.czstlocp001.dhl.com:6443
* About to connect() to api.czstlocp001.dhl.com port 6443 (#0)
*   Trying 165.72.121.247...
* Connected to api.czstlocp001.dhl.com (165.72.121.247) port 6443 (#0)
* Initializing NSS with certpath: sql:/etc/pki/nssdb
* skipping SSL peer certificate verification
* NSS: client certificate not found (nickname not specified)
* SSL connection using TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
* Server certificate:
*       subject: CN=api.czstlocp001.dhl.com,O=Deutsche Post AG,L=Bonn,ST=Nordrhein-Westfalen,C=DE
*       start date: Feb 11 12:40:40 2021 GMT
*       expire date: Feb 11 12:39:40 2022 GMT
*       common name: api.czstlocp001.dhl.com
*       issuer: CN=DPDHL Global TLS CA - I5,O=Deutsche Post AG,C=DE
> GET / HTTP/1.1
> User-Agent: curl/7.29.0
> Host: api.czstlocp001.dhl.com:6443
> Accept: */*
>
< HTTP/1.1 403 Forbidden
< Audit-Id: b3257e26-8da8-4315-8d40-7ffbf17f0943
< Cache-Control: no-cache, private
< Content-Type: application/json
< X-Content-Type-Options: nosniff
< X-Kubernetes-Pf-Flowschema-Uid: f6eee3fb-fcec-4bc6-b0c0-d96e12b666b5
< X-Kubernetes-Pf-Prioritylevel-Uid: 1d25c2c6-a8e8-40a9-bcb9-6a8a68217d79
< Date: Tue, 16 Feb 2021 10:55:41 GMT
< Content-Length: 233
<
{
  "kind": "Status",
  "apiVersion": "v1",
  "metadata": {

  },
  "status": "Failure",
  "message": "forbidden: User \"system:anonymous\" cannot get path \"/\"",
  "reason": "Forbidden",
  "details": {

  },
  "code": 403
* Connection #0 to host api.czstlocp001.dhl.com left intact
```

Try to login to the cluster using admin user, you will get "x509 error: x509: certificate signed by unknown authority". This is due to the API certificate is not Signed by valid CA.
For More details refer to [here](https://access.redhat.com/solutions/4878721)

```
[ans@czstllspc005204 Aneesh]$ oc login -u admin
error: x509: certificate signed by unknown authority

[ans@czstllspc005204 ~]$ oc login --loglevel 6
I0211 09:03:04.579587   96865 loader.go:375] Config loaded from file:  /home/ans/installation_directory/auth/kubeconfig
I0211 09:03:08.378658   96865 round_trippers.go:443] HEAD https://api.czstlocp001.dhl.com:6443/ 403 Forbidden in 3798 milliseconds
I0211 09:03:08.378702   96865 request_token.go:86] GSSAPI Enabled
I0211 09:03:08.380535   96865 round_trippers.go:443] GET https://api.czstlocp001.dhl.com:6443/.well-known/oauth-authorization-server 200 OK in 1 milliseconds
I0211 09:03:08.419053   96865 request_token.go:457] falling back to kubeconfig CA due to possible x509 error: x509: certificate signed by unknown authority
I0211 09:03:13.426336   96865 round_trippers.go:443] GET https://oauth-openshift.apps.czstlocp001.dhl.com/oauth/authorize?client_id=openshift-challenging-client&code_challenge=kcSUBVYwFdtjK4veJBWvcBk7o_w31eXthae7ki8RinI&code_challenge_method=S256&redirect_uri=https%3A%2F%2Foauth-openshift.apps.czstlocp001.dhl.com%2Foauth%2Ftoken%2Fimplicit&response_type=code  in 5007 milliseconds
I0211 09:03:13.428721   96865 round_trippers.go:443] GET https://api.czstlocp001.dhl.com:6443/api/v1/namespaces/openshift/configmaps/motd 403 Forbidden in 1 milliseconds
F0211 09:03:13.429173   96865 helpers.go:115] error: x509: certificate signed by unknown authority
[ans@czstllspc005204 ~]$
```
In order to fix **x509: certificate signed by unknown authority**  follow below steps

### CA certs / oc login fix

```
$ openssl s_client -connect console.apps.czstlocp001.dhl.com:443 -showcerts
```
copy the second block of base-64 encoded text (between the “-----BEGIN CERTIFICATE-----“ and the “-----END CERTIFICATE -----“) in the ca.pem file which is the certificate of interest (CA)
In my case it is internal ca as you can see below (it can differ based on how and where SAO team is generating certs for BigIP)
```
1 s:/C=BE/O=GlobalSign nv-sa/CN=GlobalSign RSA OV SSL CA 2018
i:/OU=GlobalSign Root CA - R3/O=GlobalSign/CN=GlobalSign
```
Once you have ca.pem file,create configmap custom-ca using the ca.pem file

```
$ oc create configmap custom-ca --from-file=ca-bundle.crt=ca.pem -n openshift-config
```
Next step is to request the certificate and private key for the apps VIP that was generated by SAO team. When we have both the CA and key and certificate for apps VIP then create configmap for the CA and TLS secret for the apps VIP:

To fix **x509: certificate signed by unknown authority** requested certificate and key from SAO team. For more info, refer to: - [INC37565061](https://servicenow.dhl.com/nav_to.do?uri=%2Fincident.do%3Fsys_id%3D7ab5d5b11b92a01028f4ecac7b4bcbc6%26sysparm_stack%3D%26sysparm_view%3D)
certificate signed by unknown authority in OCP4[Link](https://access.redhat.com/solutions/4542531)

```
$ oc create secret tls apps.czstlocp001.dhl.com --cert=app.cer --key=key.txt -n openshift-ingress
```
Now, we need to patch the **proxy/cluster**  with the configmap(custom-ca)
and patch **ingresscontroller.operator** in project **openshift-ingress-operator** with tls secret(apps.czstlocp001.dhl.com) which we created earlier. 

### Execution of the patches (prepare the config map and secret above first):

```
$ oc patch proxy/cluster --type=merge --patch='{"spec":{"trustedCA":{"name":"custom-ca"}}}'
proxy.config.openshift.io/cluster patched

$ oc patch ingresscontroller.operator default --type=merge -p '{"spec":{"defaultCertificate": {"name": "apps.czstlocp001.dhl.com"}}}' -n openshift-ingress-operator
ingresscontroller.operator.openshift.io/default patched
```
Router pods get redeployed automatically, test oc login and cluster functionality once pods are up and running. There wont be "x509 error: x509: certificate signed by unknown authority" anymore after this activity.

```
$ oc get po -n openshift-ingress
NAME                                        READY   STATUS    RESTARTS   AGE
router-default-77679984bd-d8lxv             1/1     Running   0          166m
router-default-77679984bd-xsfrq             1/1     Running   0          157m
router-internal-prod-app-5db68f7dc9-h4pff   1/1     Running   0          133m
router-internal-prod-app-5db68f7dc9-tcfsw   1/1     Running   0          170m
```
**Validation**

```
[ans@czstllspc005204 ~]$ oc login
Authentication required for https://api.czstlocp001.dhl.com:6443 (openshift)
Username: admin
Password:
Login successful.

You have access to 57 projects, the list has been suppressed. You can list all projects with 'oc projects'

Using project "default".
```

### Fix logrotate and journald settings for RHEL workers

```
$ pwd
/home/ans/Aneesh/playbooks
$ ansible-playbook change-journald-setting.yml
$ ansible-playbook edit.logrotate.yml
```

### Configuring Registry using NFS storage

```
SITEL NFS PATH:
czstlnysvm02.prg-dc.dhl.com:/svm02_vol025/BS31369_ocp_backup
czstlnysvm02.prg-dc.dhl.com:/svm02_vol026/BS31369_ocp_registry
```
Set correct permission for the filer
```
sudo mkdir /mnt/mnt && mount -t nfs czstlnysvm02.prg-dc.dhl.com:/svm02_vol026/BS31369_ocp_registry /mnt/mnt && chmod g+w /mnt/mnt && umount /mnt/mnt
```
To start the image registry, you must change "managementState" in Image Registry Operator config from "Removed" to "Managed".

```
$ oc get configs.imageregistry.operator.openshift.io -o yaml | grep managementState
          f:managementState: {}
    managementState: Removed
To
$ oc get configs.imageregistry.operator.openshift.io -o yaml | grep managementState
          f:managementState: {}
    managementState: Managed
```

Create the PersistentVolume (PV) using [sample](https://git.dhl.com/bimodal-coc/czstlocp001.dhl.com/tree/master/misc)

```
$ oc create -f nfs_registry_pv.yaml
persistentvolume/nfs-image-registry-pv created

$ oc get pv
NAME                    CAPACITY   ACCESS MODES   RECLAIM POLICY   STATUS      CLAIM   STORAGECLASS   REASON   AGE
nfs-image-registry-pv   100Gi      RWX            Retain           Available           nfs01                   21s

```

Create the PerstsistentVolumeClaim (PVC) using [sample](https://git.dhl.com/bimodal-coc/czstlocp001.dhl.com/tree/master/misc)

```
$ oc create -f  nfs_registry_pvc.yaml -n openshift-image-registry
persistentvolumeclaim/nfs-image-registry-pvc created

$ oc get pvc -n openshift-image-registry
NAME                     STATUS   VOLUME                  CAPACITY   ACCESS MODES   STORAGECLASS   AGE
nfs-image-registry-pvc   Bound    nfs-image-registry-pv   100Gi      RWX            nfs01          14s
```

Label the registry nodes with registry=true.

```
$ oc label nodes czstllspc005205.prg-dc.dhl.com czstllspc005206.prg-dc.dhl.com registry=true
node/czstllspc005205.prg-dc.dhl.com labeled
node/czstllspc005206.prg-dc.dhl.com labeled

$ oc get nodes -L network -L stage -L zone -L router -L registry | egrep "czstllspc005205.prg-dc.dhl.com|czstllspc005206.prg-dc.dhl.com"
czstllspc005205.prg-dc.dhl.com   Ready    worker   8d    v1.18.3+65bd32d   internal           mgmt     true     true
czstllspc005206.prg-dc.dhl.com   Ready    worker   8d    v1.18.3+65bd32d   internal           mgmt     true     true

```
Add the name of PVC to Registry configuration(configs.imageregistry.operator.openshift.io) and configure node selector.
```
$ oc edit configs.imageregistry.operator.openshift.io
config.imageregistry.operator.openshift.io/cluster edited

$ oc describe configs.imageregistry.operator.openshift.io | egrep -A2 "Management State:|Storage"
  Management State:  Managed
  Node Selector:
    Registry:  true
--
  Storage:
    Pvc:
      Claim:  nfs-image-registry-pvc
```

Check the clusteroperator status is Available and not Degraded. If degraded, check the configuration again and fix the issue.

```
$ oc get clusteroperator image-registry
NAME             VERSION   AVAILABLE   PROGRESSING   DEGRADED   SINCE
image-registry   4.5.20    True        False         False      22s
```

Configure the default registry route and the custom registry hostname.

```
$ oc edit configs.imageregistry.operator.openshift.io/cluster
config.imageregistry.operator.openshift.io/cluster edited

$ oc get configs.imageregistry.operator.openshift.io/cluster -o yaml 
spec:
defaultRoute: true
routes:
  - hostname: registry.apps.czstlocp001.dhl.com
    name: public

$ oc get route -n openshift-image-registry
NAME            HOST/PORT                                                         PATH   SERVICES         PORT    TERMINATION   WILDCARD
default-route   default-route-openshift-image-registry.apps.czstlocp001.dhl.com          image-registry   <all>   reencrypt     None
public          registry.apps.czstlocp001.dhl.com                                        image-registry   <all>   reencrypt     None

```
Check registry access.

```
[ans@czstllspc005204 Aneesh]$ sudo podman login -u admin -pFMlsstmCtyhZ8p4D1HvbBuknRPmO8kKRzxSTyLXtG_8 https://registry.apps.czstlocp001.dhl.com --tls-verify=false
Login Succeeded!

$ sudo podman logout https://registry.apps.czstlocp001.dhl.com
Removed login credentials for registry.apps.czstlocp001.dhl.com

```

### Mount NFS storage to Ansible host for backups.

```
# cat echo "czstlnysvm02.prg-dc.dhl.com:/svm02_vol025/BS31369_ocp_backup /backup nfs defaults,bg,_netdev 0 0" >> /etc/fstab
# mkdir /backup
# mount /backup
# mkdir /backup/temp
# chown ans:ans /backup/temp

# df -h /backup
Filesystem                                                    Size  Used Avail Use% Mounted on
czstlnysvm02.prg-dc.dhl.com:/svm02_vol025/BS31369_ocp_backup  2.0T     0  2.0T   0% /backup
```

### Disable projects creation for users:
```
$ diff -u clusterrolebinding.rbac_self-provisioners_before.yml clusterrolebinding.rbac_self-provisioners_after.yml
--- clusterrolebinding.rbac_self-provisioners_before.yml        2021-02-17 11:15:26.960691495 +0100
+++ clusterrolebinding.rbac_self-provisioners_after.yml 2021-02-17 11:17:44.014747290 +0100
@@ -2,16 +2,14 @@
 kind: ClusterRoleBinding
 metadata:
   annotations:
-    rbac.authorization.kubernetes.io/autoupdate: "true"
+    rbac.authorization.kubernetes.io/autoupdate: "false"
   creationTimestamp: "2021-02-04T05:33:36Z"
   managedFields:
   - apiVersion: rbac.authorization.k8s.io/v1
     fieldsType: FieldsV1
     fieldsV1:
       f:metadata:
-        f:annotations:
-          .: {}
-          f:rbac.authorization.kubernetes.io/autoupdate: {}
+        f:annotations: {}
       f:roleRef:
         f:apiGroup: {}
         f:kind: {}
@@ -20,8 +18,17 @@
     manager: openshift-apiserver
     operation: Update
     time: "2021-02-04T05:33:36Z"
+  - apiVersion: rbac.authorization.k8s.io/v1
+    fieldsType: FieldsV1
+    fieldsV1:
+      f:metadata:
+        f:annotations:
+          f:rbac.authorization.kubernetes.io/autoupdate: {}
+    manager: oc
+    operation: Update
+    time: "2021-02-17T10:17:09Z"
   name: self-provisioners
-  resourceVersion: "14475"
+  resourceVersion: "6142452"
   selfLink: /apis/rbac.authorization.k8s.io/v1/clusterrolebindings/self-provisioners
   uid: 3e8705e8-9ed6-4eda-be17-3ccde8fbb532
 roleRef:
```


### Syncing groups using ldap-sync
Log in the cluster as admin and get the token, and perform the below action. ldap-sync folder you can get from any newely build OCP 4.5 cluster. Copy the folder to your ansible host and perform the following:

```
$ cd ~/ldap-sync
$ oc whoami
admin
$ oc whoami -t
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
$ cat > token
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
[ans@czstllspc005204 ldap-sync]$ ./ldap-sync --confirm
#O# group.user.openshift.io/UDLDHL-OCPTeam-pnp-meinvertrieb-talend-edit created

#O# group.user.openshift.io/UDLDHL-OCPTeam-its-cloudx-cbj-admin created

#O# group.user.openshift.io/UDLDHL-OCPTeam-frt-spt-edit created
.....
.....
.....
```
After executing LDAP sync command ldap users and respective groups will be synced with OCP.
Now time to grant cluster-admin role to **UDLDHL-OCPCBClusterAdmins** group.

```
$ oc adm policy add-cluster-role-to-group cluster-admin UDLDHL-OCPCBClusterAdmins
clusterrole.rbac.authorization.k8s.io/cluster-admin added: "UDLDHL-OCPCBClusterAdmins"
```

### Installing the EFK stack
Prepare disks

Check the disk status which has been created earlier:
```
$ ansible efk -m shell -a 'lvscan | grep elasticsearch'
czstllspc005208.prg-dc.dhl.com | CHANGED | rc=0 >>
  ACTIVE            '/dev/elasticsearch/elasticsearch' [<1.76 TiB] inherit
czstllspc005207.prg-dc.dhl.com | CHANGED | rc=0 >>
  ACTIVE            '/dev/elasticsearch/elasticsearch' [<1.76 TiB] inherit
czstllspc005209.prg-dc.dhl.com | CHANGED | rc=0 >>
  ACTIVE            '/dev/elasticsearch/elasticsearch' [<1.76 TiB] inherit
```

Install Local storage operator as described [link](https://docs.openshift.com/container-platform/4.5/storage/persistent_storage/persistent-storage-local.html#local-storage-install_persistent-storage-local%22)

Use files local-storage.yaml from "https://git.dhl.com/bimodal-coc/czstlocp001.dhl.com/tree/master/misc".
```
$ oc create -f local-storage.yaml
namespace/local-storage created
operatorgroup.operators.coreos.com/local-operator-group created
subscription.operators.coreos.com/local-storage-operator created
```
Verify operator instalation.

```
$ oc -n local-storage get pods -o wide
NAME                                      READY   STATUS    RESTARTS   AGE   IP            NODE                             NOMINATED NODE   READINESS GATES
local-storage-operator-7475485cff-vjlsk   1/1     Running   0          24m   10.130.4.10   czstllspc005229.prg-dc.dhl.com   <none>           <none>
```
Check the ClusterServiceVersion (CSV) YAML manifest to see that the Local Storage Operator is available in the local-storage project:

```
$ oc get csvs -n local-storage
NAME                                           DISPLAY         VERSION                 REPLACES   PHASE
local-storage-operator.4.5.0-202101300210.p0   Local Storage   4.5.0-202101300210.p0              Succeeded
```

Deploy logging EFK local volumes.

```
$ oc create -f localvolume-es_disks.yaml
localvolume.local.storage.openshift.io/es-disks created
```

Verify installation.

```
$ oc get po -o wide -n local-storage
NAME                                      READY   STATUS    RESTARTS   AGE     IP            NODE                             NOMINATED NODE   READINESS GATES
es-disks-local-diskmaker-4k4p4            1/1     Running   0          7m47s   10.129.2.3    czstllspc005207.prg-dc.dhl.com   <none>           <none>
es-disks-local-diskmaker-r78rk            1/1     Running   0          7m47s   10.130.2.4    czstllspc005209.prg-dc.dhl.com   <none>           <none>
es-disks-local-diskmaker-ssl8h            1/1     Running   0          7m47s   10.129.4.4    czstllspc005208.prg-dc.dhl.com   <none>           <none>
es-disks-local-provisioner-dvfqn          1/1     Running   0          7m47s   10.129.4.3    czstllspc005208.prg-dc.dhl.com   <none>           <none>
es-disks-local-provisioner-jvbjz          1/1     Running   0          7m47s   10.129.2.4    czstllspc005207.prg-dc.dhl.com   <none>           <none>
es-disks-local-provisioner-kwf5q          1/1     Running   0          7m47s   10.130.2.3    czstllspc005209.prg-dc.dhl.com   <none>           <none>
local-storage-operator-7475485cff-vjlsk   1/1     Running   0          48m     10.130.4.10   czstllspc005229.prg-dc.dhl.com   <none>           <none>

$ oc get storageclass
NAME       PROVISIONER                    RECLAIMPOLICY   VOLUMEBINDINGMODE      ALLOWVOLUMEEXPANSION   AGE
es-disks   kubernetes.io/no-provisioner   Delete          WaitForFirstConsumer   false                  62m

```

Verify that the **provisioner** was created, and that the **corresponding daemon sets** were created:
```
$ oc get all -n local-storage
NAME                                          READY   STATUS    RESTARTS   AGE
pod/es-disks-local-diskmaker-4k4p4            1/1     Running   0          3m28s
pod/es-disks-local-diskmaker-r78rk            1/1     Running   0          3m28s
pod/es-disks-local-diskmaker-ssl8h            1/1     Running   0          3m28s
pod/es-disks-local-provisioner-dvfqn          1/1     Running   0          3m28s
pod/es-disks-local-provisioner-jvbjz          1/1     Running   0          3m28s
pod/es-disks-local-provisioner-kwf5q          1/1     Running   0          3m28s
pod/local-storage-operator-7475485cff-vjlsk   1/1     Running   0          43m

NAME                             TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)     AGE
service/local-storage-operator   ClusterIP   172.30.165.104   <none>        60000/TCP   43m

NAME                                        DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR   AGE
daemonset.apps/es-disks-local-diskmaker     3         3         3       3            3           <none>          3m28s
daemonset.apps/es-disks-local-provisioner   3         3         3       3            3           <none>          3m28s

NAME                                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/local-storage-operator   1/1     1            1           43m

NAME                                                DESIRED   CURRENT   READY   AGE
replicaset.apps/local-storage-operator-7475485cff   1         1         1       43m

```
Verify that the persistent volumes were created:
```
$ oc get pv
NAME                    CAPACITY   ACCESS MODES   RECLAIM POLICY   STATUS      CLAIM                                             STORAGECLASS   REASON   AGE
local-pv-10fb56ba       1799Gi     RWO            Delete           Available                                                     es-disks                9m2s
local-pv-64d4bc56       1799Gi     RWO            Delete           Available                                                     es-disks                8m59s
local-pv-a634f3dd       1799Gi     RWO            Delete           Available                                                     es-disks                9m
```

Create the namespaces.

```
$ oc create -f eo-namespace.yaml
$ oc create -f eo-og.yaml
$ oc create -f eo-sub.yaml

$ oc create -f eo-namespace.yaml
namespace/openshift-operators-redhat created

$ oc create -f eo-og.yaml
operatorgroup.operators.coreos.com/openshift-operators-redhat created

$ oc create -f eo-sub.yaml
subscription.operators.coreos.com/elasticsearch-operator created
```

Verify elasticsearch operator installation.

```
$ oc get po -o wide -n openshift-operators-redhat
NAME                                     READY   STATUS    RESTARTS   AGE   IP            NODE                             NOMINATED NODE   READINESS GATES
elasticsearch-operator-cd864dc76-crrjr   1/1     Running   0          20m   10.128.6.10   czstllspc005227.prg-dc.dhl.com   <none>           <none>


$ oc get csv --all-namespaces
NAMESPACE                                          NAME                                           DISPLAY                  VERSION                 REPLACES   PHASE
default                                            elasticsearch-operator.4.5.0-202102041049.p0   Elasticsearch Operator   4.5.0-202102041049.p0              Succeeded
kube-node-lease                                    elasticsearch-operator.4.5.0-202102041049.p0   Elasticsearch Operator   4.5.0-202102041049.p0              Succeeded
kube-public                                        elasticsearch-operator.4.5.0-202102041049.p0   Elasticsearch Operator   4.5.0-202102041049.p0              Succeeded
kube-system                                        elasticsearch-operator.4.5.0-202102041049.p0   Elasticsearch Operator   4.5.0-202102041049.p0              Succeeded
local-storage                                      elasticsearch-operator.4.5.0-202102041049.p0   Elasticsearch Operator   4.5.0-202102041049.p0              Succeeded
local-storage                                      local-storage-operator.4.5.0-202101300210.p0   Local Storage            4.5.0-202101300210.p0              Succeeded
openshift-apiserver-operator                       elasticsearch-operator.4.5.0-202102041049.p0   Elasticsearch Operator   4.5.0-202102041049.p0              Succeeded
openshift-apiserver                                elasticsearch-operator.4.5.0-202102041049.p0   Elasticsearch Operator   4.5.0-202102041049.p0              Succeeded
....
....
....
```

Deploy the Logging Operator.

```
$ oc create -f clo-namespace.yaml
$ oc create -f clo-og.yaml
$ oc create -f clo-sub.yaml

$ oc create -f clo-namespace.yaml
namespace/openshift-logging created

$ oc create -f clo-og.yaml
operatorgroup.operators.coreos.com/cluster-logging created

$ oc create -f clo-sub.yaml
subscription.operators.coreos.com/cluster-logging created

$ oc get og -n openshift-logging
NAME              AGE
cluster-logging   64s

$ oc get po -o wide -n openshift-logging
NAME                                       READY   STATUS    RESTARTS   AGE   IP           NODE                             NOMINATED NODE   READINESS GATES
cluster-logging-operator-7d8cd7589-xbkgb   1/1     Running   0          24s   10.128.2.7   czstllspc005228.prg-dc.dhl.com   <none>           <none>
```

Edit the sample config file clusterlogging_instance.yaml specifying the right amount of nodes and limits

```
$ oc create -f clusterlogging_instance.yaml
clusterlogging.logging.openshift.io/instance created

```
**Validation:**
```
$ oc get po -o wide -n openshift-logging
NAME                                            READY   STATUS      RESTARTS   AGE    IP            NODE                             NOMINATED NODE   READINESS GATES
cluster-logging-operator-7d8cd7589-xbkgb        1/1     Running     0          110m   10.128.2.7    czstllspc005228.prg-dc.dhl.com   <none>           <none>
elasticsearch-cdm-7xi5lgxt-1-544cf7756b-mv5s8   2/2     Running     0          71m    10.129.2.6    czstllspc005207.prg-dc.dhl.com   <none>           <none>
elasticsearch-cdm-7xi5lgxt-2-68c54cdd95-dfxz8   2/2     Running     0          71m    10.129.4.6    czstllspc005208.prg-dc.dhl.com   <none>           <none>
elasticsearch-cdm-7xi5lgxt-3-86f694ccb4-c66cj   2/2     Running     0          71m    10.130.2.6    czstllspc005209.prg-dc.dhl.com   <none>           <none>
elasticsearch-delete-app-1613630700-z9zcn       0/1     Completed   0          13m    10.128.6.22   czstllspc005227.prg-dc.dhl.com   <none>           <none>
elasticsearch-delete-audit-1613630700-8sz7h     0/1     Completed   0          13m    10.128.2.14   czstllspc005228.prg-dc.dhl.com   <none>           <none>
elasticsearch-delete-infra-1613630700-2wgst     0/1     Completed   0          13m    10.128.6.23   czstllspc005227.prg-dc.dhl.com   <none>           <none>
elasticsearch-rollover-app-1613630700-ch6x7     0/1     Completed   0          13m    10.130.4.17   czstllspc005229.prg-dc.dhl.com   <none>           <none>
elasticsearch-rollover-audit-1613630700-s5rf9   0/1     Completed   0          13m    10.128.6.24   czstllspc005227.prg-dc.dhl.com   <none>           <none>
elasticsearch-rollover-infra-1613630700-89c2s   0/1     Completed   0          13m    10.130.4.18   czstllspc005229.prg-dc.dhl.com   <none>           <none>
fluentd-4w2jm                                   1/1     Running     0          71m    10.129.2.5    czstllspc005207.prg-dc.dhl.com   <none>           <none>
fluentd-6j7sl                                   1/1     Running     0          71m    10.128.4.4    czstllspc005205.prg-dc.dhl.com   <none>           <none>
fluentd-8jmcz                                   1/1     Running     0          71m    10.131.2.3    czstllspc005456.prg-dc.dhl.com   <none>           <none>
fluentd-c2dn9                                   1/1     Running     0          71m    10.131.0.4    czstllspc005206.prg-dc.dhl.com   <none>           <none>
fluentd-fjrls                                   1/1     Running     0          71m    10.130.0.42   czstlap0083.prg-dc.dhl.com       <none>           <none>
fluentd-jvp5k                                   1/1     Running     0          71m    10.129.6.3    czstllspc005455.prg-dc.dhl.com   <none>           <none>
fluentd-mxb8k                                   1/1     Running     0          71m    10.130.2.5    czstllspc005209.prg-dc.dhl.com   <none>           <none>
fluentd-nv6jt                                   1/1     Running     0          71m    10.130.4.11   czstllspc005229.prg-dc.dhl.com   <none>           <none>
fluentd-p9q8x                                   1/1     Running     0          71m    10.128.6.12   czstllspc005227.prg-dc.dhl.com   <none>           <none>
fluentd-qfjlq                                   1/1     Running     0          71m    10.129.0.46   czstlap0082.prg-dc.dhl.com       <none>           <none>
fluentd-sbdxs                                   1/1     Running     0          71m    10.129.4.5    czstllspc005208.prg-dc.dhl.com   <none>           <none>
fluentd-sdrxb                                   1/1     Running     0          71m    10.130.6.14   czstllspc005231.prg-dc.dhl.com   <none>           <none>
fluentd-ss84b                                   1/1     Running     0          71m    10.128.2.8    czstllspc005228.prg-dc.dhl.com   <none>           <none>
fluentd-tr8ct                                   1/1     Running     0          71m    10.128.0.22   czstlap0081.prg-dc.dhl.com       <none>           <none>
fluentd-wbq8w                                   1/1     Running     0          71m    10.131.6.8    czstllspc005230.prg-dc.dhl.com   <none>           <none>
fluentd-xxtkq                                   1/1     Running     0          71m    10.131.4.3    czstllspc005226.prg-dc.dhl.com   <none>           <none>
fluentd-zdq6d                                   1/1     Running     0          71m    10.128.8.3    czstllspc005225.prg-dc.dhl.com   <none>           <none>
kibana-68898b8c46-jgx96                         2/2     Running     0          71m    10.128.2.9    czstllspc005228.prg-dc.dhl.com   <none>           <none>

$ oc get route -n openshift-logging
NAME     HOST/PORT                                           PATH   SERVICES   PORT    TERMINATION          WILDCARD
kibana   kibana-openshift-logging.apps.czstlocp001.dhl.com          kibana     <all>   reencrypt/Redirect   None

```

Create custom route for kibana.
```
$  oc get route/kibana -o yaml -n openshift-logging > kibana_custom_route.yaml

[ans@czstllspc005204 EFK_local-storage]$ diff -Nrp kibana_custom_route_orig.yaml kibana_custom_route.yaml
*** kibana_custom_route_orig.yaml       2021-02-18 08:03:37.321790267 +0100
--- kibana_custom_route.yaml    2021-02-18 08:18:28.451240275 +0100
*************** metadata:
*** 47,68 ****
            f:name: {}
            f:weight: {}
          f:wildcardPolicy: {}
!     manager: elasticsearch-operator
      operation: Update
      time: "2021-02-18T05:47:24Z"
!   name: kibana
    namespace: openshift-logging
-   ownerReferences:
-   - apiVersion: logging.openshift.io/v1
-     controller: true
-     kind: Kibana
-     name: kibana
-     uid: 905898d8-c973-42d0-aa9e-28dee182c14a
-   resourceVersion: "6580156"
-   selfLink: /apis/route.openshift.io/v1/namespaces/openshift-logging/routes/kibana
-   uid: f30643ab-2f82-4d89-8d29-8000f29a9c30
  spec:
!   host: kibana-openshift-logging.apps.czstlocp001.dhl.com
    tls:
      caCertificate: |
        -----BEGIN CERTIFICATE-----
--- 47,59 ----
            f:name: {}
            f:weight: {}
          f:wildcardPolicy: {}
!     manager: oc
      operation: Update
      time: "2021-02-18T05:47:24Z"
!   name: kibana-custom
    namespace: openshift-logging
  spec:
!   host: kibana.apps.czstlocp001.dhl.com
    tls:
      caCertificate: |
        -----BEGIN CERTIFICATE-----
*************** spec:
*** 133,145 ****
      name: kibana
      weight: 100
    wildcardPolicy: None
- status:
-   ingress:
-   - conditions:
-     - lastTransitionTime: "2021-02-18T05:47:22Z"
-       status: "True"
-       type: Admitted
-     host: kibana-openshift-logging.apps.czstlocp001.dhl.com
-     routerCanonicalHostname: apps.czstlocp001.dhl.com
-     routerName: default
-     wildcardPolicy: None
--- 124,126 ----

$ oc create -f kibana_custom_route.yaml
route.route.openshift.io/kibana-custom created
```
Check the route status:

```
$ oc get route -n openshift-logging
NAME            HOST/PORT                                           PATH   SERVICES   PORT    TERMINATION          WILDCARD
kibana          kibana-openshift-logging.apps.czstlocp001.dhl.com          kibana     <all>   reencrypt/Redirect   None
kibana-custom   kibana.apps.czstlocp001.dhl.com                            kibana     <all>   reencrypt/Redirect   None
```
Edit SA kibana to have new route information

```
From: 

$  oc -n openshift-logging get sa kibana -o yaml | head
apiVersion: v1
imagePullSecrets:
- name: kibana-dockercfg-cctq5
kind: ServiceAccount
metadata:
  annotations:
    serviceaccounts.openshift.io/oauth-redirectreference.first: '{"kind":"OAuthRedirectReference","apiVersion":"v1","reference":{"kind":"Route","name":"kibana"}}'
  creationTimestamp: "2021-02-18T05:47:22Z"
  managedFields:
  - apiVersion: v1

TO:

$  oc -n openshift-logging get sa kibana -o yaml | head
apiVersion: v1
imagePullSecrets:
- name: kibana-dockercfg-cctq5
kind: ServiceAccount
metadata:
  annotations:
    serviceaccounts.openshift.io/oauth-redirectreference.first: '{"kind":"OAuthRedirectReference","apiVersion":"v1","reference":{"kind":"Route","name":"kibana"}}'
    serviceaccounts.openshift.io/oauth-redirectreference.second: '{"kind":"OAuthRedirectReference","apiVersion":"v1","reference":{"kind":"Route","name":"kibana-custom"}}'
  creationTimestamp: "2021-02-18T05:47:22Z"
  managedFields:
```
### Configuring local persistent volumes / claims for monitoring (Prometheus / Alertmanager)


Prerequisites described in [link](https://docs.openshift.com/container-platform/4.5/monitoring/cluster_monitoring/configuring-the-monitoring-stack.html#prerequisites-2)
Prometheus has two replicas, Alertmanager has three replicas. You will need 5 PVs ready to support monitoring stack.

Create a hosts group for monitoring nodes in ansible hosts file.

```
$ cat /etc/ansible/hosts | grep -iA3 prom
[prom]
czstllspc005207.prg-dc.dhl.com
czstllspc005208.prg-dc.dhl.com
czstllspc005209.prg-dc.dhl.com
```

Remove the LV and VG of the available disk /dev/sdc.

```
$ ansible prom -m shell -a "lvremove -y vg2/lv01"
czstllspc005209.prg-dc.dhl.com | CHANGED | rc=0 >>
  Logical volume "lv01" successfully removed
czstllspc005207.prg-dc.dhl.com | CHANGED | rc=0 >>
  Logical volume "lv01" successfully removed
czstllspc005208.prg-dc.dhl.com | CHANGED | rc=0 >>
  Logical volume "lv01" successfully removed
[ans@czstllspc005204 ~]$ ansible prom -m shell -a "vgremove -y vg2"
czstllspc005208.prg-dc.dhl.com | CHANGED | rc=0 >>
  Volume group "vg2" successfully removed
czstllspc005209.prg-dc.dhl.com | CHANGED | rc=0 >>
  Volume group "vg2" successfully removed
czstllspc005207.prg-dc.dhl.com | CHANGED | rc=0 >>
  Volume group "vg2" successfully removed
```  
  
Create a volume group using free disk. 
```
$ ansible prom -m shell -a "lsblk"
$ ansible prom -m shell -a "vgcreate -y monitoring /dev/sdc{}"

In my case it's /dev/sdc1

$ ansible prom -m shell -a "vgcreate -y monitoring /dev/sdc1"
czstllspc005208.prg-dc.dhl.com | CHANGED | rc=0 >>
  Volume group "monitoring" successfully created
czstllspc005209.prg-dc.dhl.com | CHANGED | rc=0 >>
  Volume group "monitoring" successfully created
czstllspc005207.prg-dc.dhl.com | CHANGED | rc=0 >>
  Volume group "monitoring" successfully created
```
Create logical volumes. 180G for Prometheous and remaining 19G for alertmanager.

ATTENTION: Potential bug. Using command "lvcreate -l 100%FREE" to create a LV with the rest of space causes the PVCs bound issue into "Pending" status.

```
$ ansible prom -m shell -a "lvcreate -L180G -n prometheus -y monitoring"
$ ansible prom -m shell -a "lvcreate -L19G -n alertmanager -y monitoring"

$ ansible prom -m shell -a "lvcreate -L180G -n prometheus -y monitoring"
czstllspc005208.prg-dc.dhl.com | CHANGED | rc=0 >>
  Wiping ext4 signature on /dev/monitoring/prometheus.
  Logical volume "prometheus" created.
czstllspc005207.prg-dc.dhl.com | CHANGED | rc=0 >>
  Wiping ext4 signature on /dev/monitoring/prometheus.
  Logical volume "prometheus" created.
czstllspc005209.prg-dc.dhl.com | CHANGED | rc=0 >>
  Wiping ext4 signature on /dev/monitoring/prometheus.
  Logical volume "prometheus" created.

$  ansible prom -m shell -a "lvcreate -L19G -n alertmanager -y monitoring"
czstllspc005209.prg-dc.dhl.com | CHANGED | rc=0 >>
  Logical volume "alertmanager" created.
czstllspc005208.prg-dc.dhl.com | CHANGED | rc=0 >>
  Logical volume "alertmanager" created.
czstllspc005207.prg-dc.dhl.com | CHANGED | rc=0 >>
  Logical volume "alertmanager" created.
```

Verify available LVs.

```
$ ansible prom -m shell -a lvscan | egrep "prometheus|alertmanager"
  ACTIVE            '/dev/monitoring/prometheus' [180.00 GiB] inherit
  ACTIVE            '/dev/monitoring/alertmanager' [19.00 GiB] inherit
  ACTIVE            '/dev/monitoring/prometheus' [180.00 GiB] inherit
  ACTIVE            '/dev/monitoring/alertmanager' [19.00 GiB] inherit
  ACTIVE            '/dev/monitoring/prometheus' [180.00 GiB] inherit
  ACTIVE            '/dev/monitoring/alertmanager' [19.00 GiB] inherit
```

Deploy new local volume objects for monitoring using sample config. This will create pods on the defined nodes and available PVs. Don't forget to set correct nodes and devicepaths values.

File you can get from [link](https://git.dhl.com/bimodal-coc/czstlocp001.dhl.com/tree/master/misc)

```
$ oc create -f localvolume-prom_disks.yaml
localvolume.local.storage.openshift.io/prom-disks created
$ oc create -f localvolume-alertmanager_disks.yaml
localvolume.local.storage.openshift.io/alertmanager-disks created
```
Verify the local storage operators pods are running and the new available PVs.
You can see 2 prom-disks and 3 alertmanager pods. You can see the storageclass as well.
You can see the new PV's in available state.

```
$ oc get po -o wide -n local-storage | egrep "alertmanager-disks|prom-disks"
alertmanager-disks-local-diskmaker-ck9lx     1/1     Running   0          2m52s   10.129.4.10   czstllspc005208.prg-dc.dhl.com   <none>           <none>
alertmanager-disks-local-diskmaker-nlb9f     1/1     Running   0          2m52s   10.129.2.9    czstllspc005207.prg-dc.dhl.com   <none>           <none>
alertmanager-disks-local-diskmaker-r2mjb     1/1     Running   0          2m52s   10.130.2.8    czstllspc005209.prg-dc.dhl.com   <none>           <none>
alertmanager-disks-local-provisioner-hzfps   1/1     Running   0          2m52s   10.129.4.9    czstllspc005208.prg-dc.dhl.com   <none>           <none>
alertmanager-disks-local-provisioner-mk2l2   1/1     Running   0          2m52s   10.129.2.10   czstllspc005207.prg-dc.dhl.com   <none>           <none>
alertmanager-disks-local-provisioner-mk6z8   1/1     Running   0          2m52s   10.130.2.7    czstllspc005209.prg-dc.dhl.com   <none>           <none>
prom-disks-local-diskmaker-qj4ht             1/1     Running   0          4m14s   10.129.2.8    czstllspc005207.prg-dc.dhl.com   <none>           <none>
prom-disks-local-diskmaker-zkdvn             1/1     Running   0          4m14s   10.129.4.8    czstllspc005208.prg-dc.dhl.com   <none>           <none>
prom-disks-local-provisioner-8zkjl           1/1     Running   0          4m14s   10.129.2.7    czstllspc005207.prg-dc.dhl.com   <none>           <none>
prom-disks-local-provisioner-ljtd5           1/1     Running   0          4m14s   10.129.4.7    czstllspc005208.prg-dc.dhl.com   <none>           <none>

$ oc get sc -n local-storage
NAME                 PROVISIONER                    RECLAIMPOLICY   VOLUMEBINDINGMODE      ALLOWVOLUMEEXPANSION   AGE
alertmanager-disks   kubernetes.io/no-provisioner   Delete          WaitForFirstConsumer   false                  4m8s
es-disks             kubernetes.io/no-provisioner   Delete          WaitForFirstConsumer   false                  6h45m
prom-disks           kubernetes.io/no-provisioner   Delete          WaitForFirstConsumer   false                  5m30s

$ oc get pv  | grep -i available
local-pv-46971e3d       180Gi      RWO            Delete           Available                                                                  prom-disks                    6m6s
local-pv-84657ed7       180Gi      RWO            Delete           Available                                                                  prom-disks                    6m5s
local-pv-8fc0dbb0       19Gi       RWO            Delete           Available                                                                  alertmanager-disks            4m44s
local-pv-f03b6cb6       19Gi       RWO            Delete           Available                                                                  alertmanager-disks            4m44s
local-pv-f17effc7       19Gi       RWO            Delete           Available                                                                  alertmanager-disks            4m44s
```

Its time to create configmap to create PVC.
Change accordingly the configmap sample file to create PVCs for Prometheus / Alertmanager.
File you can get from [link](https://git.dhl.com/bimodal-coc/czstlocp001.dhl.com/tree/master/misc)

```
$ oc create -f cluster-monitoring-configmap.yaml
configmap/cluster-monitoring-config created
```

Verify the Prometheus pods are recreated and PVCs status are "Bound" after the configMap creation completed..
```
$ oc get cm -n openshift-monitoring | grep cluster-monitoring-config
cluster-monitoring-config                             1      5m52s

$ oc get pvc -n openshift-monitoring
NAME                                   STATUS   VOLUME              CAPACITY   ACCESS MODES   STORAGECLASS         AGE
alertmanager-pvc-alertmanager-main-0   Bound    local-pv-8fc0dbb0   19Gi       RWO            alertmanager-disks   55s
alertmanager-pvc-alertmanager-main-1   Bound    local-pv-f03b6cb6   19Gi       RWO            alertmanager-disks   55s
alertmanager-pvc-alertmanager-main-2   Bound    local-pv-f17effc7   19Gi       RWO            alertmanager-disks   55s
prom-pvc-prometheus-k8s-0              Bound    local-pv-84657ed7   180Gi      RWO            prom-disks           45s
prom-pvc-prometheus-k8s-1              Bound    local-pv-46971e3d   180Gi      RWO            prom-disks           45s

[ans@czstllspc005204 EFK_local-storage]$ oc get pods  -n openshift-monitoring | egrep "alertmanager|prometheus-k"
alertmanager-main-0                            5/5     Running   0          4m11s
alertmanager-main-1                            5/5     Running   0          4m11s
alertmanager-main-2                            5/5     Running   0          4m11s
prometheus-k8s-0                               7/7     Running   1          4m1s
prometheus-k8s-1                               7/7     Running   1          4m1s

```

Modifying the retention time for Prometheus metrics data. (By default is 15days).

```
$ oc edit configmap/cluster-monitoring-config -n openshift-monitoring
configmap/cluster-monitoring-config edited

$ oc get configmap/cluster-monitoring-config -n openshift-monitoring -o yaml | grep -A2 prometheusK8s
    prometheusK8s:
      retention: 7d
      volumeClaimTemplate:
```
Substitute <time_specification> with a number directly followed by ms (milliseconds), s (seconds), m (minutes), h (hours), d (days), w (weeks), or y (years).

Moving monitoring components to different nodes.
Since we have specific nodes for the EFK/prometeus we can move all the prometheus compnents to run on those nodes.


```
$ oc edit configmap/cluster-monitoring-config -n openshift-monitoring
configmap/cluster-monitoring-config edited

$ oc -n openshift-monitoring get configmap cluster-monitoring-config -o yaml
apiVersion: v1
data:
  config.yaml: |
    alertmanagerMain:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
      volumeClaimTemplate:
        metadata:
          name: alertmanager-pvc
        spec:
          storageClassName: alertmanager-disks
          resources:
            requests:
              storage: 19Gi
    prometheusK8s:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
      retention: 7d
      volumeClaimTemplate:
        metadata:
          name: prom-pvc
        spec:
          storageClassName: prom-disks
          resources:
            requests:
              storage: 180Gi
    prometheusOperator:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
    kubeStateMetrics:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
    grafana:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
    telemeterClient:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
    k8sPrometheusAdapter:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
    openshiftStateMetrics:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
    thanosQuerier:
      nodeSelector:
        network: internal
        router: false
        zone: mgmt
kind: ConfigMap
metadata:
  creationTimestamp: "2021-02-18T11:14:12Z"
  managedFields:
  - apiVersion: v1
    fieldsType: FieldsV1
    fieldsV1:
      f:data:
        .: {}
        f:config.yaml: {}
    manager: oc
    operation: Update
    time: "2021-02-18T11:46:18Z"
  name: cluster-monitoring-config
  namespace: openshift-monitoring
  resourceVersion: "6918452"
  selfLink: /api/v1/namespaces/openshift-monitoring/configmaps/cluster-monitoring-config
  uid: 044ac747-6bfc-4ca7-8fb2-79984e0e771a
```

### Egress IPs

```
Assigning for the Prod_Internal_Egress

$ oc patch hostsubnet czstllspc005455.prg-dc.dhl.com --type=merge -p '{"egressCIDRs": ["2.253.94.128/25"]}'
hostsubnet.network.openshift.io/czstllspc005455.prg-dc.dhl.com patched
$ oc patch hostsubnet czstllspc005456.prg-dc.dhl.com --type=merge -p '{"egressCIDRs": ["2.253.94.128/25"]}'
hostsubnet.network.openshift.io/czstllspc005456.prg-dc.dhl.com patched

Assigning for the Prod_dmz_Egress
$ oc patch hostsubnet czstllspc005463.prg-dc.dhl.com --type=merge -p '{"egressCIDRs": ["2.253.93.128/25"]}'
hostsubnet.network.openshift.io/czstllspc005463.prg-dc.dhl.com patched
$ oc patch hostsubnet czstllspc005464.prg-dc.dhl.com --type=merge -p '{"egressCIDRs": ["2.253.93.128/25"]}'
hostsubnet.network.openshift.io/czstllspc005464.prg-dc.dhl.com patched



Validation:

$ oc get hostsubnet | egrep "czstllspc005455.prg-dc.dhl.com|czstllspc005456.prg-dc.dhl.com"
czstllspc005455.prg-dc.dhl.com   czstllspc005455.prg-dc.dhl.com   2.253.94.140    10.129.6.0/23   [2.253.94.128/25]
czstllspc005456.prg-dc.dhl.com   czstllspc005456.prg-dc.dhl.com   2.253.94.141    10.131.2.0/23   [2.253.94.128/25]

$ oc get hostsubnet | egrep "czstllspc005463.prg-dc.dhl.com|czstllspc005464.prg-dc.dhl.com"
czstllspc005463.prg-dc.dhl.com   czstllspc005463.prg-dc.dhl.com   2.253.93.140    10.129.10.0/23   [2.253.93.128/25]
czstllspc005464.prg-dc.dhl.com   czstllspc005464.prg-dc.dhl.com   2.253.93.141    10.131.8.0/23    [2.253.93.128/25]

```

### Test Egress IP
Testing on Prod_Internal_Egress

```
$ oc new-project test-internal
$ oc get project | grep test-internal
test-internal                                                     Active
$ oc get netnamespace | grep test-internal
test-internal                                      7260119

$ oc patch ns test-internal -p '{"metadata": {"annotations": {"openshift.io/node-selector": "stage=prod,network=internal,zone=app,router=false"}, "labels": {"net-zone": "prod-internal"}}}'
namespace/test-internal patched

$ oc describe project test-internal | egrep "net-zone|node-selector"
Labels:                 net-zone=prod-internal
                        openshift.io/node-selector=stage=prod,network=internal,zone=app,router=false

$ oc patch netnamespace test-internal --type=merge -p '{"egressIPs": ["2.253.94.148"]}'
netnamespace.network.openshift.io/test-internal patched

$ oc get hostsubnet | grep 2.253.94.148
czstllspc005456.prg-dc.dhl.com   czstllspc005456.prg-dc.dhl.com   2.253.94.141    10.131.2.0/23   [2.253.94.128/25]   [2.253.94.148]
$ oc get netnamespace | grep test-internal
test-internal                                      7260119    [2.253.94.148]

$ oc new-app openshift/httpd:latest  name=httpd -n test-internal
--> Found image e619386 (3 weeks old) in image stream "openshift/httpd" under tag "latest" for "openshift/httpd:latest"

    Apache httpd 2.4
    ----------------
    Apache httpd 2.4 available as container, is a powerful, efficient, and extensible web server. Apache supports a variety of features, many implemented as compiled modules which extend the core functionality. These can range from server-side programming language support to authentication schemes. Virtual hosting allows one Apache installation to serve many different Web sites.

    Tags: builder, httpd, httpd24


--> Creating resources ...
    imagestreamtag.image.openshift.io "httpd:latest" created
    deployment.apps "httpd" created
    service "httpd" created
--> Success
    Application is not exposed. You can expose services to the outside world by executing one or more of the commands below:
     'oc expose svc/httpd'
    Run 'oc status' to view your app.

$ oc exec -n test-internal httpd-7bd8d7fbc5-lczr9 -- curl -k https://whatismyip.dhl.com --noproxy whatismyip.dhl.com
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    13  100    13    0     0    197      0 --:--:-- --:--:-- --:--:--   200
2.253.94.148

$ oc get all -n test-internal
NAME                         READY   STATUS    RESTARTS   AGE
pod/httpd-7bd8d7fbc5-lczr9   1/1     Running   0          50m
pod/httpd-7bd8d7fbc5-rqlhr   1/1     Running   0          22m

NAME            TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)             AGE
service/httpd   ClusterIP   172.30.230.242   <none>        8080/TCP,8443/TCP   50m

NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/httpd   2/2     2            2           50m

NAME                               DESIRED   CURRENT   READY   AGE
replicaset.apps/httpd-7bd8d7fbc5   2         2         2       50m
replicaset.apps/httpd-8c64554cb    0         0         0       50m

NAME                                   IMAGE REPOSITORY                                                                      TAGS     UPDATED
imagestream.image.openshift.io/httpd   default-route-openshift-image-registry.apps.czstlocp001.dhl.com/test-internal/httpd   latest   50 minutes ago

NAME                             HOST/PORT                                                 PATH   SERVICES   PORT       TERMINATION   WILDCARD
route.route.openshift.io/httpd   httpd-test-internal.apps.czstlocp001.dhl.com ... 1 more          httpd      8080-tcp   edge          None
```


### Integration with Self Service Portal and Jenkins

```
$ oc new-project cloudmgmt
$ oc create sa svc-its-robot -n cloudmgmt
$ oc get clusterrolebinding | grep svc-its-robot
$ oc create -f cluster-role-svc-its-robot.yaml
$ oc create -f cluster_role_for_created_sa_by_svc-its-robot.yaml
$ oc get clusterrolebinding | grep svc-its-robot
$ oc adm policy add-cluster-role-to-user cluster_role_for_svc-its-robot -z svc-its-robot -n cloudmgmt
$ oc create -f create_project_role.yaml
$ oc adm policy add-cluster-role-to-user create_project_role -z svc-its-robot -n cloudmgmt
$ oc adm policy add-cluster-role-to-user cluster_role_for_created_sa_by_svc-its-robot  -z svc-its-robot -n cloudmgmt
$ oc adm policy add-cluster-role-to-user self-provisioner -z svc-its-robot -n cloudmgmt
$ oc get clusterrolebinding | grep svc-its-robot
$ oc get clusterroles | grep its-robot
$ oc serviceaccounts get-token svc-its-robot -n cloudmgmt
```

Add the new cluster in [SSP](https://multi-cloud-self-service.dhl.com/admin/clusters.xhtml)

Note: 
Even if you add the new cluster in the SSP, your cluster name wont be visible in the "Cluster" selection part while you are trying to do new AppBox Order.
In order to visible your cluster name you need to perform below mentioned tasks:
scaledown and scleup dc/wildfly-ocpcss which will help to sync the cluster name in SSP after that you can order new AppBox.

**This needs to be performed in PRG-PRD(ocp-3.11 Cluster)**

```
$ oc get project | grep -i ssp
its-internal-ocp-cssp-build                 Customer Self Service Portal (Build)   Active
its-internal-ocp-cssp-dev                   Customer Self Service Portal (Dev)     Active
its-internal-ocp-cssp-prod                  Customer Self Service Portal (Prod)    Active
its-internal-ocp-cssp-test                  Customer Self Service Portal (Test)    Active

$ oc get dc -n its-internal-ocp-cssp-prod
NAME             REVISION   DESIRED   CURRENT   TRIGGERED BY
mysql-ocpcss     5          1         1         config,image(mysql:5.7)
wildfly-ocpcss   59         1         1         config,image(wildfly-ocpcss:latest)

$ oc scale dc/wildfly-ocpcss  --replicas=0 -n its-internal-ocp-cssp-prod
deploymentconfig.apps.openshift.io/wildfly-ocpcss scaled

$ oc get po -n its-internal-ocp-cssp-prod
NAME                   READY     STATUS    RESTARTS   AGE
mysql-ocpcss-5-zsgkj   1/1       Running   0          18d

$ oc scale dc/wildfly-ocpcss  --replicas=1 -n its-internal-ocp-cssp-prod
deploymentconfig.apps.openshift.io/wildfly-ocpcss scaled

$ oc get po -n its-internal-ocp-cssp-prod
NAME                      READY     STATUS    RESTARTS   AGE
mysql-ocpcss-5-zsgkj      1/1       Running   0          19d
wildfly-ocpcss-59-d6z8r   1/1       Running   0          1h
```

 Request quotas on [SSP](https://multi-cloud-self-service.dhl.com/app/appbox_edit.xhtml) while new "AppBox Order"
 
 ```
- Openshift project name cicd-endtoend-monitoring
- Product ID - 1234
- Business unit- ITS
- Cluster- PRG-dr-version 4
- Sales order - 31000000
- Transition facilitator (contact mail) aneesh.vadakkoott-mohan@dhl.com
- AD Group (view)* - GAPDEITS-Bimodal-CoC	
- AD Group (edit)* - GAPDEITS-Bimodal-CoC		
- AD Group (admin) - GAPDEITS-Bimodal-CoC	
```

Add your cluster details Home page of ishare [ishare](https://isharenew.dhl.com/sites/itspaas/SitePages/Home.aspx)
Add your cluster details in to the ishare networking info link [ishare-networking](https://isharenew.dhl.com/sites/itspaas/OpenShift%20Wiki/Networking.aspx)
and in [wiki](https://container-platform-wiki.dhl.com/index.php?title=Network_Connections)


Create ticket [INC37960710](https://servicenow.dhl.com/nav_to.do?uri=%2Fincident.do%3Fsys_id%3Deeac9865db7aa4dc765d70a7f4961929%26sysparm_view%3D%26sysparm_domain%3Dnull%26sysparm_domain_scope%3Dnull) for Jenkins and assign it to global-ci.support.
Information needed API URL.

### Jenkins Pipeline

**First Pipeline**

Make sure you have access to https://jenkins.dhl.com/job/Openshift/job/Openshift-Monitoring/ before proceeding with the Pipeline creation.
Normally everyone those who have ldap account can login to Jenkins. However getting the project access you need to get necessary permission from those who manages that project.

First of all you need to get your cluster added in to the Jenkins via Jenkins team. In my I had raised a ticket to jenkins team  [INC37960710](https://servicenow.dhl.com/nav_to.do?uri=%2Fincident.do%3Fsys_id%3Deeac9865db7aa4dc765d70a7f4961929%26sysparm_view%3D%26sysparm_domain%3Dnull%26sysparm_domain_scope%3Dnull) for Jenkins and assign it to global-ci.support.
Once cluster added in to Jenkins the team will provide you label of the cluster which can be used in your environment creation in Jenkins. in my case they provided label name as **PRG-DR-V4**

Environment creation is only for creating namespaces in Openshift via Jenkins.
The first pipeline we are mainly using for creating following namespaces in Openshift via Jenkins.
```
its-cicd-endtoend-monitoring-build                                           Active
its-cicd-endtoend-monitoring-dmz-build                                       Active
its-cicd-endtoend-monitoring-dmz-prod                                        Active
its-cicd-endtoend-monitoring-dmz-test                                        Active
its-cicd-endtoend-monitoring-prod                                            Active
its-cicd-endtoend-monitoring-test                                            Active
```

How to create Environment for your project creation in openshift via Jenkins ?

Step 1:

Go to [Jenkins_Monitoring](https://jenkins.dhl.com/job/Openshift/job/Openshift-Monitoring/)
You can see a project "Env-creation-usmegocp001" which can be used as a template for your project creation.
On the Jenkins page, on left side click on "New Item" it will ask you to enter Item name, please provide the name according to your cluster so that easy to understand.
Enter an item name "Env-creation-czstlocp001"
at the bootom of the page, you can see "copy from" test box. Here you need to specify from where you wants to copy the contents. This is where you need to put the template name "Env-creation-usmegocp001" once done, click "OK" button which will give you a new window where you new environment can configure. 

Step 2:

Configure your Environment in the page.
There are no much things to configure as its copied from the template. You just need to update/configure the things of your cluster so that Jenkins will know about your new cluster settings.

a. 
In General tab, under "This project is Parameterised" section add your cluster label which you got from Jenkins team
In my case it was **PRG-DR-V4** add the label name un the Choices text box at the end. This is the place where mention the cluster details. You can see other cluster labels also here.

b. 
Under "String Parameter" section, specify the Project name which wanted to be created in Openshift.
in "Default Value" text box specify the project name, in my case it was "its-cicd-endtoend-monitoring". This name you will get when you order appbox from the SSP. You will receive mail regarding you appBox creation in that mail you can see the name.

c. 
Under Credentials Parameter section, in the "Default Value" text box click on "add" button to add your new token.
This is the section where you need to specify the token which will be used for the project creation in Openshift. This token also you can see the AppBox order mail.
Make sure you only use one Token which will be used for all the projects and the billing also be done based on that particular service name. In my case I used "svc-its-cicd-endtoend-monitoring-prod" token.

Tips: While adding token select:
kind "Openshift Token for Openshift client Plugin"
Token: "copy your token and paste it here" I used token of svc-its-cicd-endtoend-monitoring-prod.
ID: svc-its-cicd-endtoend-monitoring-prod-czstlocp001 (This is the name of token which will be displayed afterwards. so provide a name which you can recognise later)
Click "Add" button which will save your token.

Once completed, no more updating required as we are using the other parts as default selection.
d. Click "Save" button. which will return to old window where you can see "Build with Parameters" on left side of the window.


Click on "Build with Parameter"  which would let you to select the following:

```
Openshift_cluster: select your cluster. In my case it was **PRG-DR-V4**
Openshift_token: Make sure your token is correctly selected, if not set it correct one.
create_projects: Yes
Create_only_projects:Yes
Click "Build" button which will start building via jenkins pipeline. 
```
In order to see the logs, go to Bild history and select your new job.
Click on Console Output. in order to start build you need to provide your input here at the logs. Once you click and give your input the build will complete and will configure project in Openshift.

For the DMZ project creation reconfigure same Environment. The following things only need to modify:

```
1. Project name:
Default Value: its-cicd-endtoend-monitoring-dmz
2. Openshift Token add new token for DMZ. which you got for DMZ project. you can find this token in the same mail sent from SSP.
in my case : svc-its-cicd-endtoend-monitoring-dmz-prod-czstlocp001
```

```
$ oc get project | grep endtoend
its-cicd-endtoend-monitoring-build                                           Active
its-cicd-endtoend-monitoring-dmz-build                                       Active
its-cicd-endtoend-monitoring-dmz-prod                                        Active
its-cicd-endtoend-monitoring-dmz-test                                        Active
its-cicd-endtoend-monitoring-prod                                            Active
its-cicd-endtoend-monitoring-test                                            Active
````

Jenkins First Pipeline completed.

After the projects are created make sure to [add the roles to the build project for the dmz so that it can pull the image](https://docs.openshift.com/container-platform/4.5/authentication/understanding-and-creating-service-accounts.html#service-accounts-granting-roles_understanding-service-accounts)

```
$ oc get rolebinding -n its-cicd-endtoend-monitoring-dmz-prod -o wide
$ oc adm policy add-role-to-user view system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod -n its-cicd-endtoend-monitoring-dmz-prod
clusterrole.rbac.authorization.k8s.io/view added: "system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod"

$ oc adm policy add-role-to-user view system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod -n its-cicd-endtoend-monitoring-dmz-prod
clusterrole.rbac.authorization.k8s.io/view added: "system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod"


$ oc get rolebindings -n its-cicd-endtoend-monitoring-dmz-prod -o wide
NAME                    ROLE                               AGE    USERS                                                                       GROUPS                                                         SERVICEACCOUNTS
admin                   ClusterRole/admin                  22h    system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod
admin-0                 ClusterRole/admin                  22h                                                                                UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-admin
edit                    ClusterRole/edit                   22h                                                                                UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-edit
system:deployers        ClusterRole/system:deployer        22h                                                                                                                                               its-cicd-endtoend-monitoring-dmz-prod/deployer
system:image-builders   ClusterRole/system:image-builder   22h                                                                                                                                               its-cicd-endtoend-monitoring-dmz-prod/builder
system:image-puller     ClusterRole/system:image-puller    3m2s                                                                                                                                              cloudmgmt/svc-its-cicd-endtoend-monitoring-dmz-prod
system:image-pullers    ClusterRole/system:image-puller    22h                                                                                system:serviceaccounts:its-cicd-endtoend-monitoring-dmz-prod
view                    ClusterRole/view                   22h                                                                                UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-view
view-0                  ClusterRole/view                   42s                                                                                                                                               cloudmgmt/svc-its-cicd-endtoend-monitoring-dmz-prod

$ oc adm policy add-role-to-user system:image-puller system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod -n its-cicd-endtoend-monitoring-dmz-build
clusterrole.rbac.authorization.k8s.io/system:image-puller added: "system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod"
[ans@czstllspc005204 topaz-monitoring]$ oc adm policy add-role-to-user view system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod -n its-cicd-endtoend-monitoring-dmz-build
clusterrole.rbac.authorization.k8s.io/view added: "system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod"
[ans@czstllspc005204 topaz-monitoring]$ oc get rolebindings -n its-cicd-endtoend-monitoring-dmz-build -o wide
NAME                    ROLE                               AGE   USERS                                                                       GROUPS                                                          SERVICEACCOUNTS
admin                   ClusterRole/admin                  23h   system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod
admin-0                 ClusterRole/admin                  23h                                                                               UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-admin
edit                    ClusterRole/edit                   23h                                                                               UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-edit
system:deployers        ClusterRole/system:deployer        23h                                                                                                                                               its-cicd-endtoend-monitoring-dmz-build/deployer
system:image-builders   ClusterRole/system:image-builder   23h                                                                                                                                               its-cicd-endtoend-monitoring-dmz-build/builder
system:image-puller     ClusterRole/system:image-puller    23h                                                                                                                                               cloudmgmt/svc-its-cicd-endtoend-monitoring-dmz-prod
system:image-pullers    ClusterRole/system:image-puller    23h                                                                               system:serviceaccounts:its-cicd-endtoend-monitoring-dmz-build
view                    ClusterRole/view                   23h                                                                               UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-view
view-0                  ClusterRole/view                   23h                                                                                                                                               cloudmgmt/svc-its-cicd-endtoend-monitoring-dmz-prod


$ oc get rolebinding -n its-cicd-endtoend-monitoring-build -o wide
$ oc adm policy add-role-to-user system:image-puller system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod -n its-cicd-endtoend-monitoring-build
$ oc adm policy add-role-to-user view system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-dmz-prod -n its-cicd-endtoend-monitoring-build

$ oc get rolebinding -n its-cicd-endtoend-monitoring-build -o wide
NAME                    ROLE                               AGE   USERS                                                                   GROUPS                                                      SERVICEACCOUNTS
admin                   ClusterRole/admin                  25h   system:serviceaccount:cloudmgmt:svc-its-cicd-endtoend-monitoring-prod
admin-0                 ClusterRole/admin                  25h                                                                           UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-admin
edit                    ClusterRole/edit                   25h                                                                           UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-edit
system:deployers        ClusterRole/system:deployer        25h                                                                                                                                       its-cicd-endtoend-monitoring-build/deployer
system:image-builders   ClusterRole/system:image-builder   25h                                                                                                                                       its-cicd-endtoend-monitoring-build/builder
system:image-puller     ClusterRole/system:image-puller    25h                                                                                                                                       cloudmgmt/svc-its-cicd-endtoend-monitoring-prod
system:image-puller-0   ClusterRole/system:image-puller    18m                                                                                                                                       cloudmgmt/svc-its-cicd-endtoend-monitoring-dmz-prod
system:image-pullers    ClusterRole/system:image-puller    25h                                                                           system:serviceaccounts:its-cicd-endtoend-monitoring-build
view                    ClusterRole/view                   25h                                                                           UDLDHL-OCPTeam-its-cicd-endtoend-monitoring-view
view-0                  ClusterRole/view                   25h                                                                                                                                       cloudmgmt/svc-its-cicd-endtoend-monitoring-prod
view-1                  ClusterRole/view                   18m                                                                                                                                       cloudmgmt/svc-its-cicd-endtoend-monitoring-dmz-prod
```
Also make sure the projects are labelled properly in order to schedule the pods on correct nodes.

```
oc patch ns its-cicd-endtoend-monitoring-build -p '{"metadata": {"annotations": {"openshift.io/node-selector": "stage=prod,network=internal,zone=app,router=false"}, "labels": {"net-zone": "prod-internal"}}}'
oc patch ns its-cicd-endtoend-monitoring-prod -p '{"metadata": {"annotations": {"openshift.io/node-selector": "stage=prod,network=internal,zone=app,router=false"}, "labels": {"net-zone": "prod-internal"}}}'
oc patch ns its-cicd-endtoend-monitoring-test -p '{"metadata": {"annotations": {"openshift.io/node-selector": "stage=prod,network=internal,zone=app,router=false"}, "labels": {"net-zone": "prod-internal"}}}'
oc patch ns its-cicd-endtoend-monitoring-dmz-build -p '{"metadata": {"annotations": {"openshift.io/node-selector": "stage=prod,network=dmz,zone=app,router=false"}, "labels": {"net-zone": "prod-dmz"}}}'
oc patch ns its-cicd-endtoend-monitoring-dmz-prod -p '{"metadata": {"annotations": {"openshift.io/node-selector": "stage=prod,network=dmz,zone=app,router=false"}, "labels": {"net-zone": "prod-dmz"}}}'
oc patch ns its-cicd-endtoend-monitoring-dmz-test -p '{"metadata": {"annotations": {"openshift.io/node-selector": "stage=prod,network=dmz,zone=app,router=false"}, "labels": {"net-zone": "prod-dmz"}}}'

$ for i in $(oc get project | grep -i cicd | awk {'print $1'});do echo $i;oc describe project $i|egrep "net-zone|node-selector";done;
its-cicd-endtoend-monitoring-build
                        net-zone=prod-internal
                        openshift.io/node-selector=stage=prod,network=internal,zone=app,router=false
its-cicd-endtoend-monitoring-dmz-build
                        net-zone=prod-dmz
                        openshift.io/node-selector=stage=prod,network=dmz,zone=app,router=false
its-cicd-endtoend-monitoring-dmz-prod
                        net-zone=prod-dmz
                        openshift.io/node-selector=stage=prod,network=dmz,zone=app,router=false
its-cicd-endtoend-monitoring-dmz-test
                        net-zone=prod-dmz
                        openshift.io/node-selector=stage=prod,network=dmz,zone=app,router=false
its-cicd-endtoend-monitoring-prod
                        net-zone=prod-internal
                        openshift.io/node-selector=stage=prod,network=internal,zone=app,router=false
its-cicd-endtoend-monitoring-test
                        net-zone=prod-internal
                        openshift.io/node-selector=stage=prod,network=internal,zone=app,router=false
```

### Second pipeline.

Topaz-endtoend-monitoring - to create the apps. 
Copy from some older pipeline. the newest pipeline from TFs. Jenkins/Openshift/Environment creation for TFs into Jenkins/Openshift/Monitoring/Topaz. First add a folder for the new cluster into the [Git](https://git.dhl.com/bimodal-coc/topaz-monitoring) repo and update the Jenkinsfile and parameter files accordingly. Make sure into the pipline to change the Script Path in the end. Run Build Now. Your build will fail if you havelake of roles binded to the service account. So make sure you have sufficient rolebindings added as mentioned above.

###Third pipeline - Egress

[Repo][https://git.dhl.com/bimodal-coc/egress-monitor]

Create Egress on each namespace:

```
[ans@czstllspc005204 ~]$  oc get nodes -L zone -L network| grep egress
czstllspc005455.prg-dc.dhl.com   Ready    worker   32d   v1.18.3+65bd32d   egress   internal
czstllspc005456.prg-dc.dhl.com   Ready    worker   32d   v1.18.3+65bd32d   egress   internal
czstllspc005463.prg-dc.dhl.com   Ready    worker   8d    v1.18.3+c3b5327   egress   dmz
czstllspc005464.prg-dc.dhl.com   Ready    worker   8d    v1.18.3+c3b5327   egress   dmz
[ans@czstllspc005204 ~]$ oc get hostsubnet | grep 0054
czstllspc005455.prg-dc.dhl.com   czstllspc005455.prg-dc.dhl.com   2.253.94.140    10.129.6.0/23    [2.253.94.128/25]
czstllspc005456.prg-dc.dhl.com   czstllspc005456.prg-dc.dhl.com   2.253.94.141    10.131.2.0/23    [2.253.94.128/25]   [2.253.94.148]
czstllspc005463.prg-dc.dhl.com   czstllspc005463.prg-dc.dhl.com   2.253.93.140    10.129.10.0/23   [2.253.93.128/25]
czstllspc005464.prg-dc.dhl.com   czstllspc005464.prg-dc.dhl.com   2.253.93.141    10.131.8.0/23    [2.253.93.128/25]   [2.253.93.148]


$ oc patch  netnamespace its-cicd-endtoend-monitoring-prod --type=merge -p '{"egressIPs": ["2.253.94.149"]}'
netnamespace.network.openshift.io/its-cicd-endtoend-monitoring-prod patched

$ oc patch netnamespace its-cicd-endtoend-monitoring-dmz-prod --type=merge -p '{"egressIPs": ["2.253.93.149"]}'
netnamespace.network.openshift.io/its-cicd-endtoend-monitoring-dmz-prod patched

 oc get hostsubnet | grep 0054
czstllspc005455.prg-dc.dhl.com   czstllspc005455.prg-dc.dhl.com   2.253.94.140    10.129.6.0/23    [2.253.94.128/25]   [2.253.94.149]
czstllspc005456.prg-dc.dhl.com   czstllspc005456.prg-dc.dhl.com   2.253.94.141    10.131.2.0/23    [2.253.94.128/25]   [2.253.94.148]
czstllspc005463.prg-dc.dhl.com   czstllspc005463.prg-dc.dhl.com   2.253.93.140    10.129.10.0/23   [2.253.93.128/25]   [2.253.93.149]
czstllspc005464.prg-dc.dhl.com   czstllspc005464.prg-dc.dhl.com   2.253.93.141    10.131.8.0/23    [2.253.93.128/25]   [2.253.93.148]

$ oc get netnamespace | grep cicd
its-cicd-endtoend-monitoring-build                 3681025
its-cicd-endtoend-monitoring-dmz-build             3407508
its-cicd-endtoend-monitoring-dmz-prod              8168826    [2.253.93.149]
its-cicd-endtoend-monitoring-dmz-test              3920177
its-cicd-endtoend-monitoring-prod                  15011457   [2.253.94.149]
its-cicd-endtoend-monitoring-test                  13528219

```

### Login Screen with logo

Make login process straight forward by changing providers and login templates
Use files from
"https://git.dhl.com/bimodal-coc/czchooct002.dhl.com/blob/master/misc/".

Create secrets

```
$ oc -n openshift-config create secret generic providers-template --from-file=providers.html
$ oc -n openshift-config create secret generic login-template --from-file=login.html


Edit oauths configuration

$ oc edit oauths cluster
[...]
  templates:
    login:
      name: login-template
    providerSelection:
      name: providers-template


Wait for the oauth pods to restart

$ oc -n openshift-authentication get pods -w
```

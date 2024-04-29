# How to use OVN K layer2 and localnet type networks on OpenShift 4.14+ to implement a dynamic networking solution for Virtual Machines

* create a namespace
```
oc apply -f
```
* create the layer2 overlay network (this is the network where VMs are attached as well)
```
oc apply -f 01-layer2-no-subnet.yaml
```
* create ovs bridge **ovs-br1** on all the worker nodes and connect it to physical NIC **ens4f1**
```
oc apply -f
````
* create the localnet overlay (this is where the FRR pod connects for external connectvity)
```
oc apply -f 02-vlan-1105-br1-mlecki-no-subnets.yaml
```
* enable ip_forwarding on **ens4f1**
```
oc apply -f 
```
* create the FRR router pods (one per worker node)
```
oc apply -f
```


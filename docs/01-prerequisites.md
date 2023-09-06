# Prerequisites

## VM Hardware Requirements

1. 8 GB of RAM 
2. 50 GB Disk space

## Virtual Box

Download and Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) 

## Vagrant

We'll use Vagrant to automate the provisioning and management of Virtual Machines.

Download and Install [Vagrant](https://www.vagrantup.com/) 


## Virtual Machine Network

The network used by the Virtual Box virtual machines is `192.168.56.0/24`.
To edit the default network, set the new value for the network prefix at line 9 in [Vagrantfile](../vagrant/Vagrantfile)

## Pod Network

> It is *recommended* to leave the pod and service networks with the following defaults. If we change them then we will also need to edit one or both of the CoreDNS and Weave networking manifests to accommodate our change.

The network used to assign IP addresses to pods is `10.244.0.0/16`.

To change this, do a global search for `POD_CIDR=10.244.0.0/16` and edit accordingly.

## Service Network

The network used to assign IP addresses to Cluster IP services is `10.96.0.0/16`.

To change this, do a global search for `SERVICE_CIDR=10.96.0.0/16` and edit accordingly.

Additionally edit line 164 of [coredns.yaml](../deployments/coredns.yaml) to set the new DNS service address (should still end with `.10`)

## Running Commands in Parallel with tmux

> We can use any ssh client instead of tmux

[tmux](https://github.com/tmux/tmux/wiki) can be used to run commands on multiple compute instances at the same time. 

> Enable synchronize-panes by pressing `CTRL+B` followed by `"` to split the window into two panes. In each pane (selectable with mouse), ssh to the host(s) you will be working with. Next type `CTRL+X` at the prompt to begin sync. In sync mode, the dividing line between panes will be red. Everything you type or paste in one pane will be echoed in the other.<br>To disable synchronization type `CTRL+X` again.</br></br>Note that the `CTRL-X` key binding is provided by a `.tmux.conf` loaded onto the VM by the vagrant provisioner.

Next: [Compute Resources](02-compute-resources.md)

# Kubernetes The Hard Way - Local Setup

> This project draws inspiration and closely follows [kubernetes-the-hard-way](https://github.com/mmumshad/kubernetes-the-hard-way). The entire repository has been modified to align with my implementation and understanding of each concept.

The goal of this project is to bootstrap a Kubernetes cluster locally on our machine using Vagrant and VirtualBox. It offers an extensive learning experience by taking the long route to ensure understanding of every task required to establish a Kubernetes cluster.

The project focuses on minute details; missing even one tiny step along the way can lead to issues.

> Always execute the `cert_verify` script where it's suggested, and ensure that you are on the correct node when performing actions. If `cert_verify` displays anything in red, it indicates an error in a previous step. For master node checks, run the check on both `master-1` and `master-2`

## Cluster Details

This project bootstraps a highly available Kubernetes cluster with end-to-end encryption between components and RBAC authentication.

* [Kubernetes](https://github.com/kubernetes/kubernetes) 1.24.3
* [Container Runtime](https://github.com/containerd/containerd) 1.5.9
* [CNI Container Networking](https://github.com/containernetworking/cni) 0.8.6
* [Weave Networking](https://www.weave.works/docs/net/latest/kubernetes/kube-addon/)
* [etcd](https://github.com/coreos/etcd) v3.5.3
* [CoreDNS](https://github.com/coredns/coredns) v1.9.4

### Node Configuration

We will build the following components:

* Two control plane nodes (`master-1` and `master-2`) running control plane components as operating system services.
* Two worker nodes (`worker-1` and `worker-2`).
* One `loadbalancer` VM running HAProxy to balance requests between the two API servers.

## Implementation

* [Prerequisites](docs/01-prerequisites.md)
* [Provisioning Compute Resources](docs/02-compute-resources.md)
* [Installing the Client Tools](docs/03-client-tools.md)
* [Provisioning the CA and Generating TLS Certificates](docs/04-certificate-authority.md)
* [Generating Kubernetes Configuration Files for Authentication](docs/05-kubernetes-configuration-files.md)
* [Generating the Data Encryption Config and Key](docs/06-data-encryption-keys.md)
* [Bootstrapping the etcd Cluster](docs/07-bootstrapping-etcd.md)
* [Bootstrapping the Kubernetes Control Plane](docs/08-bootstrapping-kubernetes-controllers.md)
* [Installing CRI on Worker Nodes](docs/09-install-cri-workers.md)
* [Bootstrapping the Kubernetes Worker Nodes](docs/10-bootstrapping-kubernetes-workers.md)
* [TLS Bootstrapping the Kubernetes Worker Nodes](docs/11-tls-bootstrapping-kubernetes-workers.md)
* [Configuring kubectl for Remote Access](docs/12-configuring-kubectl.md)
* [Deploy Weave - Pod Networking Solution](docs/13-configure-pod-networking.md)
* [Kube API Server to Kubelet Configuration](docs/14-kube-apiserver-to-kubelet.md)
* [Deploying the DNS Cluster Add-on](docs/15-dns-addon.md)
* [Smoke Test](docs/16-smoke-test.md)
* [E2E Test](docs/17-e2e-tests.md)
* [Extra - Certificate Verification](docs/verify-certificates.md)

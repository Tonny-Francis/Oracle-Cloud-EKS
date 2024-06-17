# Kubernetes Oracle

### Computing Resources
- 3x Virtual Machine VM.Standard.A1.Flex 1 OCPU 7GB RAM
- 1x Virtual Machine VM.Standard.A1.Flex 1 OCPU 3GB RAM
- 1x LoadBalancer 10Mb/s
- 7x Block Volume of 50GB

### Resource Distribution

#### OKE - Oracle Kubernetes Engine
- 3x Virtual Machine VM.Standard.A1.Flex 1 OCPU 7GB RAM - Workers
- 3x Block Volumes of 50GB

#### Rancher - EKS Management
- 1x Virtual Machine VM.Standard.A1.Flex 1 OCPU 3GB RAM
- 1x Boot Volume of 50GB

#### Monitoring EKS
##### Prometheus
- 1x Block Volume of 50GB

##### Loki
- 1x Block Volume of 50GB

##### Grafana
- 1x Block Volume of 50GB

#### NGINX Ingress - Exporting Resource Access
- 1x LoadBalancer 10Mb/s

### Notice
Virtual Machine and Network resources are within Oracle's free tier package. However, the use of Block Volumes exceeds the free tier limits, costs are at your own risk when following this Git.

### Use Of Resources By Installing The Basic For The EKS
<div>
    <img src="https://github.com/Tonny-Francis/Oracle-Cloud-EKS/assets/81640351/ae98da2a-c0ac-4743-8b58-fc4a653fc80c"/>
</div>


### Notes Of Version
The version of EKS that I installed, v1.29.1, does not support the installation of Rancher within the cluster, which is why Rancher is in a separate VM. However, to optimize resources, I recommend installing compatible versions.

### Understanding How OKE Works and Creating It

- [Oracle](https://docs.oracle.com/pt-br/iaas/Content/ContEng/Concepts/contengoverview.htm)
- [Overview and Creation](https://docs.oracle.com/pt-br/iaas/Content/ContEng/Concepts/contengoverview.htm)

### Understanding PV and PVC in Kubernetes

- [Kubernetes](https://kubernetes.io/pt-br/docs/concepts/storage/persistent-volumes/)

### Understanding Storage Class

- [Kubernetes](https://kubernetes.io/docs/concepts/storage/storage-classes/)

### Understanding Ingress Controller and LoadBalancer and Creating It
Note: The Load Balancer part using MetalLB is just for understanding, Oracle already provides Load Balancer when using OKE
- [YouTube Video](https://youtu.be/k8bxtsWe9qw?si=ENxSe7YrFVZypENw)

### Understanding Cert Manger and Creating It

- [Youtube Video](https://youtu.be/Xv1bdeVnGGY?si=qV7BPeuOXq7OhHSr)

### Understanding Monitoring EKS
Note: In this git you can find custom values ​​for monitoring installation, such as data persistence and resource optimization.
- [Youtube Video](https://youtu.be/fzny5uUaAeY?si=gHp_KLl4SSFwWwk6)

### Understanding Helm

- [Article](https://circleci.com/blog/what-is-helm/)

### Installation Rancher in Docker

- [Rancher](https://www.rancher.com/quick-start)
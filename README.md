# Cluster Local K3S Orange PI Zero 2W

## Hardware

- 2x Orange Pi Zero 2 Quad-core 4GB
- 1x VMs Ampere A1 Duo-core 4GB
- 1x VM Ampere A1 Single-Core 4GB


## How To Start

### Install K3s Master
Run this command to install k3s as master

```sh
curl -sfL https://get.k3s.io | INSTALL_K3S_VERSION="v1.28.9+k3s1" sh -
```

It is possible to specify a specific [VERSION](https://docs.k3s.io/release-notes/v1.28.X) of k3s using the flag `INSTALL_K3S_VERSION`.

After running the above command, the K3s master cluster will be operational.

### Install K3s Workers

Run this command to install k3s as worker

```sh
curl -sfL https://get.k3s.io | INSTALL_K3S_VERSION="v1.28.9+k3s1" K3S_URL=https://<MASTER_IP>:6443 K3S_TOKEN=<NODE_TOKEN> sh -
```
To install a k3s worker we will need some details like MASTER_IP and NODE_TOKEN

#### Get MASTER_IP
Run this command in master

```sh
hostname -I
```

#### Get NODE_TOKEN

Run this command in master

```sh
sudo cat /var/lib/rancher/k3s/server/node-token
```

After completing the command line with the appropriate information about the master node, the worker will be installed and connected to the master node.
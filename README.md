# Kubernets Oracle

## Hardware

### Master
- 1x VM Ampere(Arm) A1 1 OCPU 8GB of Ram and 50GB of Storage

### Workers
- 1x VM Ampere(Arm) A1 3 OCPU 16GB of Ram and 200GB of Storage
- 2x VM AMD(x86) 1 OCPU 1GB of Ram and 25 of Storage

### Power Of Computer
- 5 OCPU 26GB of Ram and 300GB of Storage

### -> ALERT <-
The CPU and RAM configurations fall within Oracle's usual free policy, but the storage does not fall within the scope due to the use of 300GB and 3 blocks.

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
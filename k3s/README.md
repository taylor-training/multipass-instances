# K3s Server

Creates a K3s server in a Multipass server

```bash
multipass launch --name k3s --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/k3s/setup.yaml lts

# take note of IPv4 address
multipass info k3s

# Open browser to
#  http://<IPADDR>
```
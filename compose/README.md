# Docker Compose Server

Creates a server based on Docker Compose

```bash
multipass launch --name compose --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/compose/setup.yaml lts

# take note of IPv4 address
multipass info k3s

# Open browser to
#  http://<IPADDR>
```
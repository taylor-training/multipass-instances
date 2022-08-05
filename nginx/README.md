# Nginx Web Server

This sets up an Nginx web server (with default page) on an Ubuntu server

```bash
multipass launch --name web --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/nginx/nginx-simple-setup.yaml jammy

# take note of IPv4 address
multipass info web

# Open browser to
#  http://<IPADDR>
```
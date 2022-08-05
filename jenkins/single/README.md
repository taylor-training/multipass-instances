# Jenkins - Single Server

This is the simplist Jenkins setup - not recommended for production deployments. Just use for testing Jenkins basics only. Setup for running Jenkins server and builds on same VM.

```bash
multipass launch --name jenkins --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/jenkins/single/jenkins-lts-setup.yaml jammy

# take note of IPv4 address
multipass info jenkins

# Open browser to
#  http://<IPADDR>:8080

# Get temp password for setup wizard
multipass exec jenkins-server sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
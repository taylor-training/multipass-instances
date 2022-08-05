# Jenkins - Simple Server and Builder

This is a simple Jenkins setup - not recommended for production deployments. Just use for testing Jenkins basics only. Setup for running Jenkins server and builds on another VM.

```bash
# setup Jenkins server
multipass launch --name jenkins-server --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/jenkins/simple/jenkins-server-setup.yaml jammy

# take note of IPv4 address
multipass info jenkins

# Open browser to
#  http://<IPADDR>:8080

# Get temp password for setup wizard
multipass exec jenkins-server sudo cat /var/lib/jenkins/secrets/initialAdminPassword


# setup builder instance
multipass launch --name jenkins-builder --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/jenkins/simple/jenkins-builder-setup.yaml jammy


```
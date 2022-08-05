# Jenkins - Simple Server and Builder

This is a simple Jenkins setup - not recommended for production deployments. Just use for testing Jenkins basics only. Setup for running Jenkins server and builds on another VM.

```bash
# setup Jenkins server
multipass launch --name jenkins-server --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/jenkins/simple/jenkins-server-setup.yaml jammy

# take note of IPv4 address
multipass info jenkins-server

# Open browser to
#  http://<IPADDR>:8080

# Get temp password for setup wizard
multipass exec jenkins-server sudo cat /var/lib/jenkins/secrets/initialAdminPassword

# finish Jenkins setup wizard

# setup builder instance
multipass launch --name jenkins-builder --cloud-init https://raw.githubusercontent.com/taylor-training/multipass-instances/main/jenkins/simple/jenkins-builder-setup.yaml jammy


# Make note of builder IP addresses
multipass info jenkins-builder

# login to jenkins-builder
multipass shell jenkins-builder

# change/set ubuntu user password, make note of password
sudo passwd ubuntu

# exit jenkins-builder
exit

# Login to Jenkins server - add User with password credentials

# login to jenkins-server
multipass shell jenkins-server

# become jenkins user
sudo su jenkins

# attempt to login to jenkins-builder via ssh, accept fingerprint key
ssh ubuntu@IPADDR

# exit from jenkins-builder
exit

# exit as jenkins user
exit

# exit from jenkins-server
exit
```

Now, update Build-in build node - set executors to 0

Create new build node, ssh connection
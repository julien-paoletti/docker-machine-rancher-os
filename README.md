# Reference
Installation Documentation:
http://docs.rancher.com/os/running-rancheros/workstation/docker-machine/

# Create VM based on rancher OS (change the version to match the latest release)
'''docker-machine create -d virtualbox --virtualbox-boot2docker-url https://github.com/rancher/os/releases/download/v0.4.2/rancheros.iso RancherOsBox

'''
Running pre-create checks...
Creating machine...
Waiting for machine to be running, this may take a few minutes...
Machine is running, waiting for SSH to be available...
Detecting operating system of created instance...
Provisioning created instance...
Copying certs to the local machine directory...
Copying certs to the remote machine...
Setting Docker configuration on the remote daemon...
'''

# check that creation was succesful
'''docker-machine ls | grep RancherOsBox
RancherOsBox            -        virtualbox   Running   tcp://192.168.99.100:2376

# docker client configuration
'''eval $(docker-machine env RancherOsBox)

# smoke test
'''docker run hello-world
'''
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
b901d36b6f2f: Pulling fs layer
0a6ba66e537a: Pulling fs layer
0a6ba66e537a: Verifying Checksum
0a6ba66e537a: Download complete
b901d36b6f2f: Verifying Checksum
b901d36b6f2f: Download complete
b901d36b6f2f: Pull complete
0a6ba66e537a: Pull complete
Digest: sha256:8be990ef2aeb16dbcb9271ddfe2610fa6658d13f6dfb8bc72074cc1ca36966a7
Status: Downloaded newer image for hello-world:latest

Hello from Docker.
This message shows that your installation appears to be working correctly.

...
'''

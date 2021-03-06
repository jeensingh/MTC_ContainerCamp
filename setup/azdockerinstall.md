# Install Docker
We're going to install Docker on our Ubuntu server by pulling the appropriate bits from Docker's repository.  Run the following commands to install the pre-reqs:
```bash
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
Next, run the following to install the docker engine:
```bash
sudo apt-get update
sudo apt-get install docker-ce
```
Now for post-installation steps:
```bash
sudo usermod -aG docker $USER
````

Docker is now installed!  Before we can use it, we need to log out and log in:

```
exit
[disconnect]
```

Now ssh back into the server.

Let's test it:
```bash
docker info
```
This command will show you info about your docker configuration.  A sample:
```
adminuser@jumpbox:~$ docker info
Containers: 1
 Running: 0
 Paused: 0
 Stopped: 1
Images: 1
Server Version: 17.12.1-ce
Storage Driver: aufs
 Root Dir: /var/lib/docker/aufs
 Backing Filesystem: extfs
 Dirs: 3
 Dirperm1 Supported: true
Logging Driver: json-file
Cgroup Driver: cgroupfs
Plugins:
 Volume: local
 Network: bridge host macvlan null overlay
Swarm: inactive
Runtimes: runc
Default Runtime: runc
Init Binary: docker-init
containerd version: 9048e5e50717ea4497b757314bad98ea3763c145
runc version: 9c2d8d184e5da67c95d601382adf14862e4f2228
init version: 949e6fa
Security Options:
 apparmor
 seccomp
  Profile: default
Kernel Version: 4.4.0-71-generic
Operating System: Ubuntu 16.04.2 LTS
OSType: linux
Architecture: x86_64
CPUs: 1
Total Memory: 3.359GiB
Name: jumpbox
ID: IAP3:USVC:ZLBW:UZEL:RN5H:53K7:3KNZ:5O5B:I4IQ:D4SQ:KQB4:FWMH
Docker Root Dir: /var/lib/docker
Debug Mode (client): false
Debug Mode (server): false
Registry: https://index.docker.io/v1/
Experimental: false
Insecure Registries:
 127.0.0.0/8
Live Restore Enabled: false
```
## Continue
Next, [pull down this git repository](setup/gitclone.md)


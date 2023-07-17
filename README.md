```
# Docker-Installation-Guide
Docker installtion on ubuntu
1.sudo apt update

2.Certificate Package:
sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release -y

3.docker gpg key import:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

4.add the official Docker repository:
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

5.DockerCE install
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y

6.docker daemon status
sudo systemctl start docker
sudo systemctl status  docker
sudo systemctl enable docker
================
7.normal user docker run
docker run hello-world
sudo usermod -aG docker $USER

8.docker pull ubuntu (docker hub=ubuntu docker image pull)(check for local have file if you not have local=docker downlaod)
#docker run -it ubuntu
#docker ps (show continer run or no runcheck)

9.docker images
#docker pull ubuntu:latest
========================

uninstall for docker command
sudo apt-get purge docker-ce docker-ce-cli\containerd.io
sudo rm -rf /var/lib/docker
sudo rm -rf /var/lib/containerd
======================================================
Ref link=https://www.zdnet.com/article/docker-101-how-to-install-docker-on-ubuntu-server-22-04/
Ref link=https://www.linuxtechi.com/install-ubuntu-server-22-04-step-by-step/
Ref link=https://linuxconfig.org/how-to-configure-static-ip-address-on-ubuntu-18-10-cosmic-cuttlefish-linux
Ref link=https://stackoverflow.com/questions/37694987/connecting-to-postgresql-in-a-docker-container-from-outside
root@ubuntu-server-22-04:~# docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED              STATUS                        PORTS                                       NAMES
6a4fb088fd13   postgres      "docker-entrypoint.s…"   19 seconds ago       Up 14 seconds                 0.0.0.0:5432->5432/tcp, :::5432->5432/tcp   postgresql
15aabdbff783   postgres      "docker-entrypoint.s…"   About a minute ago   Up About a minute             5432/tcp                                    some-postgres
59d14ffc1bde   ubuntu        "bash"                   40 minutes ago       Exited (129) 31 minutes ago                                               elegant_perlman
f778c09bf067   hello-world   "/hello"                 43 minutes ago       Exited (0) 43 minutes ago                                                 thirsty_wing
root@ubuntu-server-22-04:~# docker start postgresqldb
Error response from daemon: No such container: postgresqldb
Error: failed to start containers: postgresqldb
root@ubuntu-server-22-04:~# docker start postgres
Error response from daemon: No such container: postgres
Error: failed to start containers: postgres
root@ubuntu-server-22-04:~# ^C
root@ubuntu-server-22-04:~# docker start 15aabdbff783
15aabdbff783
root@ubuntu-server-22-04:~# docker exec -it 15aabdbff783 bash
root@15aabdbff783:/# psql -U postgres
psql (15.1 (Debian 15.1-1.pgdg110+1))
Type "help" for help.

postgres=#

======================
docker postgres link=https://youtu.be/d0jvVno7oxU
===============================
change to root user
sudo -i
nano /etc/ssh/sshd_config
-----
#LoginGraceTime 2m
#PermitRootLogin prohibit-password
(change to)
PermitRootLogin yes



ctr+o
ctr+x
save changes and exit
Then restart SSH..
#service ssh restart
======================================
ubuntu server root paswd change Ref=https://www.names.co.uk/support/articles/changing-your-root-password-on-an-ubuntu-server/
Ref=https://www.cyberciti.biz/faq/change-root-password-ubuntu-linux/
=====================================
Netowrk configuration
Ref=https://www.makeuseof.com/configure-static-ip-address-settings-ubuntu-22-04/
Ref=https://www.liquidweb.com/kb/how-to-install-and-configure-nmcli/
===========================================
```





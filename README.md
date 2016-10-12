Debian 7/8 Install :

First the Docker-Engine (For More https://docs.docker.com/engine/installation/linux/debian/ )

apt-get update 
apt-get install apt-transport-https ca-certificates
apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D

Open the /// nano /etc/apt/sources.list.d/docker.list /// file in your favorite editor. (I use nano)
Remove any existing entries.

Add an entry for your Debian operating system.

The possible entries are:

On Debian Wheezy (7)

deb https://apt.dockerproject.org/repo debian-wheezy main
On Debian Jessie (8)

deb https://apt.dockerproject.org/repo debian-jessie main
On Debian Stretch/Sid

deb https://apt.dockerproject.org/repo debian-stretch main


apt-get update

sudo apt-get install docker-engine (If you have an Error with init-system-helpers make following)

For the error ONLY Leave it when you have no ERRORS!:

init-system-helpers (missing dependency) can be installed from backports repo.

Just add deb http://http.debian.net/debian wheezy-backports main

at the end of /etc/apt/sources.list and

apt-get update && apt-get install init-system-helpers && apt-get install docker-engine

sudo service docker start
sudo docker run hello-world

adduser tsbot
sudo usermod -aG docker tsbot
cd /home/tsbot/

wget https://github.com/danyrasta/ts3music-the-best/blob/master/master.zip
apt-get install unzip
unzip master.zip
chmod +x entrypoint.sh
docker build -t ts3soundboard098 /home/tsbot/sinusbot-master/
su tsbot
cd /home/tsbot/sinusbot-master/
START DOCKERS/SINUSBOT INSTANCES!

docker run --restart=always -d --name bot1 -p 8087:8087 ts3soundboard098

docker run --restart=always -d --name bot2 -p 8088:8087 ts3soundboard098

docker run --restart=always -d --name bot3 -p 8089:8087 ts3soundboard098

docker run --restart=always -d --name bot4 -p 8090:8087 ts3soundboard098

docker run --restart=always -d --name bot5 -p 8091:8087 ts3soundboard098


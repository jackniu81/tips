# docker pull from private registry push fail: server gave HTTP response to HTTPS client 

* Create or modify /etc/docker/daemon.json
```
{ "insecure-registries":["myregistry.example.com:5000"] }
```
* Restart docker daemon 
```
sudo service docker restart
```

# Delete all containers/images, volume
1) To delete all containers including its volumes use,
2 ) To delete all the images,
```
docker rm -vf $(docker ps -a -q)
docker rmi -f $(docker images -a -q)
```

delete all volume
```
docker volume prune
```

# proxy
https://stackoverflow.com/questions/23111631/cannot-download-docker-images-behind-a-proxy
https://docs.docker.com/config/daemon/systemd/

```
Create a systemd drop-in directory for the docker service:

sudo mkdir -p /etc/systemd/system/docker.service.d
Create a file named /etc/systemd/system/docker.service.d/http-proxy.conf that adds the HTTP_PROXY environment variable:

[Service]
Environment="HTTP_PROXY=http://proxy.example.com:80"
If you are behind an HTTPS proxy server, set the HTTPS_PROXY environment variable:

[Service]
Environment="HTTPS_PROXY=https://proxy.example.com:443"
Multiple environment variables can be set; to set both a non-HTTPS and a HTTPs proxy;

[Service]
Environment="HTTP_PROXY=http://proxy.example.com:80"
Environment="HTTPS_PROXY=https://proxy.example.com:443"
```

# Docker-compose
```
# under the docker-compose.yml folder, run:
$ docker-compose up -d
$ docker-compose down
```

# Install
## docker-compose
Install Extra Packages for Enterprise Linux
```
$ sudo yum install epel-release
```
Install python-pip
```
$ sudo yum install -y python-pip
```
Then install Docker Compose:
```
$ sudo pip install docker-compose
```
You will also need to upgrade your Python packages on CentOS 7 to get docker-compose to run successfully:
```
$ sudo yum upgrade python*
```

To verify a successful Docker Compose installation, run:
```
$ docker-compose version
```

If still see not found error, run
```
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```


# maintenance
## Clean unused docker images (e.g. for build server)
```
docker system prune -f
```

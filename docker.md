# docker pull from private registry push fail: server gave HTTP response to HTTPS client 

* Create or modify /etc/docker/daemon.json
```
{ "insecure-registries":["myregistry.example.com:5000"] }
```
* Restart docker daemon 
```
sudo service docker restart
```

# Delete all containers/images
1) To delete all containers including its volumes use,
2 ) To delete all the images,
```
docker rm -vf $(docker ps -a -q)
docker rmi -f $(docker images -a -q)
```

# proxy
https://stackoverflow.com/questions/23111631/cannot-download-docker-images-behind-a-proxy

#Install
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
or
```
sudo pip install docker-compose
```
You will also need to upgrade your Python packages on CentOS 7 to get docker-compose to run successfully:
```
$ sudo yum upgrade python*
```
To verify a successful Docker Compose installation, run:
```
$ docker-compose version
```

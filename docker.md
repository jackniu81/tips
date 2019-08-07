# docker pull from private registry push fail: server gave HTTP response to HTTPS client 

* Create or modify /etc/docker/daemon.json
```
{ "insecure-registries":["myregistry.example.com:5000"] }
```
* Restart docker daemon 
```
sudo service docker restart
```

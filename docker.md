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

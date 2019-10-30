### OS Info
#### Show private IP
```
$ hostname -I
```

#### Show Network
```
$ /sbin/ifconfig
```

#### Set/Show proxy
```
export http_proxy=http://your_proxy_ip.com:port/
export https_proxy=http://your_proxy_ip.com:port/
```

```
echo ${http_proxy}
```

# Environment Variable
## System/ local environment variables
sudo does not normally preserve local environment variables. You should use it with the -E switch to do so, i.e. sudo -E su will preserve $MYVAR for root.

Alternatively, to create persistent variables that are truly system-wide, you should set them in 
```
/etc/environment
```

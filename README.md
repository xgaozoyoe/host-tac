# host-tac

## 1. docker
   * a. configure daemon.json
```
$ sudo vim /etc/docker/daemon.json
```
```
{
  "registry-mirrors": [
    "https://hub-mirror.c.163.com",
    "https://mirror.baidubce.com"
  ]
}
```
  * b. restart docker
```
$ sudo systemctl daemon-reload 
$ sudo systemctl restart docker
$ sudo docker info
```
  * c. configure proxy
```
$ vim ~/.docker/config.json
```
```
{
 "proxies": {
   "default": {
     "httpProxy": "http://proxy.example.com:3128",
     "httpsProxy": "https://proxy.example.com:3129",
     "noProxy": "*.test.example.com,.example.org,127.0.0.0/8"
   }
 }
}
```

# 2. github
```
git config --global http.proxy http://proxyaddress:port
```

Or for a specific domain, something like:
```
git config --global http.https://domain.com.proxy http://proxyaddress:port
git config --global http.https://domain.com.sslVerify false
```

## 👋 Welcome to ubuntu 🚀  

ubuntu README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update ubuntu
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/ubuntu/rootfs"
git clone "https://github.com/dockermgr/ubuntu" "$HOME/.local/share/CasjaysDev/dockermgr/ubuntu"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/ubuntu/rootfs/." "$HOME/.local/share/srv/docker/ubuntu/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdev-ubuntu \
--hostname ubuntu \
-e TZ=${TIMEZONE:-America/New_York} \
casjaysdev/ubuntu:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdev/ubuntu
    container_name: casjaysdev-ubuntu
    environment:
      - TZ=America/New_York
      - HOSTNAME=ubuntu
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdev/ubuntu
```
  
OR
  
```shell
git clone "https://github.com/casjaysdev/ubuntu" "$HOME/Projects/github/casjaysdev/ubuntu"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdev/ubuntu"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdev: [Github](https://github.com/casjaysdev) [Docker](https://hub.docker.com/u/casjaysdev) ⛵  

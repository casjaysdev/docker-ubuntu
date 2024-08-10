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
--name casjaysdevdocker-ubuntu \
--hostname ubuntu \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-ubuntu/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-ubuntu/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/ubuntu:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/ubuntu
    container_name: casjaysdevdocker-ubuntu
    environment:
      - TZ=America/New_York
      - HOSTNAME=ubuntu
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-ubuntu/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-ubuntu/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/ubuntu
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/ubuntu" "$HOME/Projects/github/casjaysdevdocker/ubuntu"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/ubuntu"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  

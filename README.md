## 👋 Welcome to it-tools 🚀  

it-tools README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update it-tools
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/it-tools/rootfs"
git clone "https://github.com/dockermgr/it-tools" "$HOME/.local/share/CasjaysDev/dockermgr/it-tools"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/it-tools/rootfs/." "$HOME/.local/share/srv/docker/it-tools/rootfs/"
```

## via command line  

```shell
docker pull casjaysdevdocker/it-tools:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-it-tools \
--hostname casjaysdev-it-tools \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/it-tools/rootfs/data:/data:z \
-v $HOME/.local/share/srv/docker/it-tools/rootfs/config:/config:z \
-p 80:80 \
casjaysdevdocker/it-tools:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  it-tools:
    image: casjaysdevdocker/it-tools
    container_name: it-tools
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-it-tools
    volumes:
      - $HOME/.local/share/srv/docker/it-tools/rootfs/data:/data:z
      - $HOME/.local/share/srv/docker/it-tools/rootfs/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  

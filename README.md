# Installation

Pull [Wowza image](https://hub.docker.com/r/wowzamedia/wowza-streaming-engine-linux/)

```
docker pull wowzamedia/wowza-streaming-engine-linux
```

Run image with mount `VHost.xml` into container

```
docker run -it --name wowza --restart always --expose 1935/tcp --expose 8086/tcp --expose 8087/tcp --expose 8088/tcp --publish 1935:1935 --publish 8086:8086 --publish 8087:8087 --publish 8088:8088 --volume $(pwd)/VHost.xml:/usr/local/WowzaStreamingEngine/conf/VHost.xml --entrypoint /sbin/entrypoint.sh --env WSE_MGR_USER=[username] --env WSE_MGR_PASS=[password] wowzamedia/wowza-streaming-engine-linux
```

More detail

https://www.wowza.com/docs/how-to-set-up-wowza-streaming-engine-using-docker

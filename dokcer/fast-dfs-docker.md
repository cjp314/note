1. 创建容器

```shell
docker network create fastdfs-net
docker run -dit -p 9065:22122 -p 9066:8080 --network=fastdfs-net --name tracker -v /opt/cjp/fdfs/tracker:/opt/cjp/fdfs ygqygq2/fastdfs-nginx:latest tracker
docker run -dit --network=fastdfs-net --name storage0 -e TRACKER_SERVER=tracker:22122 -v /opt/cjp/fdfs/storage0:/opt/cjp/fdfs ygqygq2/fastdfs-nginx:latest storage
docker run -dit --network=fastdfs-net --name storage1 -e TRACKER_SERVER=tracker:22122 -v /opt/cjp/fdfs/storage1:/opt/cjp/fdfs ygqygq2/fastdfs-nginx:latest storage

```


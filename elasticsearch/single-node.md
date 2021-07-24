#### 启动es和kibana
```
docker run -d -v /mnt/elasticsearch/data:/usr/share/elasticsearch/data --name elasticsearch --net host -e "discovery.type=single-node" -e "TAKE_FILE_OWNERSHIP=true" elasticsearch:7.12.0
docker run -d --name kibana --net host kibana:7.12.0
```
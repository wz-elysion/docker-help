#### 启动es
```
docker run -d -v /mnt/elasticsearch/node1/data:/usr/share/elasticsearch/data -v /mnt/elasticsearch/node1/config/elasticsearch.yml:/usr/share/elasticsearch/config/elasticsearch.yml --name elasticsearch-node1 --net host -e "TAKE_FILE_OWNERSHIP=true" elasticsearch:7.12.0
docker run -d -v /mnt/elasticsearch/node2/data:/usr/share/elasticsearch/data -v /mnt/elasticsearch/node2/config/elasticsearch.yml:/usr/share/elasticsearch/config/elasticsearch.yml --name elasticsearch-node2 --net host -e "TAKE_FILE_OWNERSHIP=true" elasticsearch:7.12.0
docker run -d -v /mnt/elasticsearch/node3/data:/usr/share/elasticsearch/data -v /mnt/elasticsearch/node3/config/elasticsearch.yml:/usr/share/elasticsearch/config/elasticsearch.yml --name elasticsearch-node3 --net host -e "TAKE_FILE_OWNERSHIP=true" elasticsearch:7.12.0
```
#### 启动kibana
```
docker run -d -v /mnt/kibana/config/kibana.yml:/usr/share/kibana/config/kibana.yml --name kibana-es-cluster --net host kibana:7.12.0
```
#### 开启es监控
```
PUT /_cluster/settings
{
    "persistent": {
        "xpack": {
            "monitoring": {
                "collection": {
                    "enabled": "true"
                }
            }
        }
    }
}
```

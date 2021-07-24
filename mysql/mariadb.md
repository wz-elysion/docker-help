#### 启动mariadb
```
docker run --name mariadb10.5 --net host -v /mnt/mariadb/data:/var/lib/mysql -e MARIADB_ROOT_PASSWORD=root -d mariadb:10.5
```
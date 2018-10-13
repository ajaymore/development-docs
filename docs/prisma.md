## Development 

### Create Network
```
docker network create --driver bridge reverse-proxy
```
### Run MySQL Container
```
docker run -p 3306:3306 --name mysql-container --net reverse-proxy -v /Users/mystical//mysql-data:/var/lib/mysql --restart always -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:latest
```

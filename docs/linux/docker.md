# Docker

## Dockerfile
[Documentation](https://docs.docker.com/engine/reference/builder/)

## commands
```

# Remove untagged images
docker rmi -f $(docker images | grep "<none>" | awk "{print \$3}")
docker build -t mysticalaj/node-web-app -f prod/Dockerfile . # -t for tagname
docker images
docker run -p 8000:8000 -d mysticalaj/node-web-app -e PORT=8000
docker ps
docker logs <container id>
docker exec -it <container id> /bin/bash
docker stop container_id
docker rm container_id
docker image rm image_name
# remove all stopped containers
docker rm $(docker ps --filter status=exited -q)
```

## docker-compose commands
```
sudo chown -R $USER:$USER . # Setting volume permissions
docker-compose build # also to rebuild
docker-compose up # Run all containers
docker-compose run web npm install cors
```

## Copy files from host to running container
```
docker cp foo.txt mycontainer:/foo.txt
docker cp mycontainer:/foo.txt foo.txt

# Multiple files contained by the folder src can be copied into the target folder using:

docker cp src/. mycontainer:/target
docker cp mycontainer:/src/. target
```

## Run command inside running container
`docker exec -it container_id bash`

## SCP
```
scp -i parallel-learning.pem -r ec2-user@12.23.33.33:/home/ec2-user/mongo/ /home/ubuntu/keys/data

scp -i parallel-learning.pem -r /home/ubuntu/keys/data/mongo/12-15-17/parallel-learning-video-services/ ubuntu@12.23.33.33:/home/ubuntu/parallel-learning-video-services/
```

## MongoDB
```
sudo mongodump --db parallel-learning-video-services --out /home/ec2-user/mongo/`date +"%m-%d-%y"` --username dineshsune --password "2439789fdseold98954"

mongo --port 27017 -u "dineshsune" -p "2439789fdseold98954" --authenticationDatabase "parallel-learning-video-services"

sudo mongorestore --db parallel-learning-video-services --drop /home/ubuntu/parallel-learning-video-services/parallel-learning-video-services/
```


docker run -it image_id /bin/bash
apt update
exit
docker commit container_id newimage_name
firebase login --no-localhost


server ---

express, graphql, reactjs, mongodb -- +++

react-native
-- mobile auth -> firebase | any other
-- 

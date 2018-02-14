# Docker

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
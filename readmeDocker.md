**3hr docker at 1:12**
docker hub > mongo > check if mongo has an offical image to pull, copy the pull command and image name as per docker hub documentation;

1: login docker desktop;
2: open new terminal
k:\app folder>$ `docker pull mongo`
*sha256:c165af1a407eefce644877bf5a59ba3d9ca762e62b4f1723c919dc08dc32f4d0*
k:\app folder>$ `docker pull mongo-express`
*sha256:1b23d7976f0210dbec74045c209e52fbb26d29b2e873d6c6fa3d3f0ae32c2a64*
3: run both mongo & mongo-express containers to make mongoDB available for apps;
   connect mongo-express to mongoDB container;
 ![alt text](image.png) 
 4: `docker network ls` => docker by default already provided some network;
 ![alt text](image-1.png)
 5: `docker network create [networkname];
 6: mongo run port:27017 inside a container; 
 `docker run -p 27017:27017 -d mongo` 
 `MONGO_INITDB_ROOT_USERNAME` -e for env var, you need root user+password to connect to Mongo; 
 `docker run -d -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo`  OR
 `docker run -d \` 
 `-p 27017:27017 \`
 `-e MONGO_INITDB_ROOT_USERNAME=admin \`
 `-e MONGO_INITDB_ROOT_PASSWORD=password \`
 `--name mongodb \`
 `--net mongo-network \` 
 `mongo`
 7: log in the container with this code `docker logs [containerID generated]`;
 8: docker run for Express `docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express` OR
 `docker run -d \`
 `-p 8081:8081 \`
 `-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \`
 `-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \`
 `--net mongo-network \`
 `--name mongo-express \`
 `-e ME_CONFIG_MONGODB_SERVER=mongodb \`
 `mongo-express`
do a log in the container with this code `docker logs [containerID generated]`;
![alt text](image-2.png)

9: goto browser type localhost:8081 > admin > password;
type DB name at + Create Database to create a database;
this created database can be connected from nodejs;

10: connecting nodejs to the DB
protocol => .env > 
mongodb: ;
username: admin;
password: password;
;

 stopped at 1:30
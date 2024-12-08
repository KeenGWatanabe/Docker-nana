# running a few dockers and comms each container,
# docker compose.yaml for docker run cmd for mongo:

version:'3'
services:
  mongodb:
    image: mongo
    ports:
      -27017:27017
    environment:
      -MONGO_USERNAME=admin

# docker compose.yaml for docker run cmd for mongo-express:

version:'3'
services:
  mongodb:
    image: mongo
  mongo-express:
    image: mongo-express  
    ports:
      -8080:8081
    environment:
      -ME_CONFIG_MONGODB_ADMINUSERNAME=admin
      ...

# docker compose takes care creating a common network!

version:'3'
services:
  mongodb:
    image: mongo
    ports:
      - 27017:27017
    environment:
      - MONGO_INITDB_ROOT_USERNAME=admin
      - MONGO_INITDB_ROOT_PASSWORD=password
  mongo-express:
    image: mongo-express  
    ports:
      - 8080:8081
    environment:
      - ME_CONFIG_MONGODB_ADMINUSERNAME=admin    
      - ME_CONFIG_MONGODB_ADMINPASSWORD=password
      - ME_CONFIG_MONGODB+SERVER=mongodb

# command to start docker-compose (`mongo-express` has to wait for `mongo` to start b4 it can establish a connection)
## `docker-compose -f`<file> <filename.yaml> `up`<start>

file>app>$ `docker-compose -f mongo.yaml up`  

start at 1:34
<<check node.js file for errors, especially in mongo references>>
stopped at 1:42      


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

stopped at 1:34

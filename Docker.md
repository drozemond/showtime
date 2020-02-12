```
git clone https://github.com/drozemond/showtime.git
```
```
cd showtime
```
```
docker pull rabbitmq:3.7.15-management 
```
```
docker images
```
```
docker run -p "5672:5672" -p "15672:15672" -d rabbitmq:3.7.15-management  
```
```
docker container ls
```
```
docker container stop 
```
```
docker container ls
```
```
docker-compose up -d
```
```
docker images
```
```
docker container ls
```
```
docker-compose down
```
```
docker container ls
```
```
az login
```
```
 az acr login --name fortia
```
```
docker build -t fortia.azurecr.io/showtime:<firstname> app    
```
```
docker images
```
```
docker run -p 8080:8080 fortia.azurecr.io/showtime:<firstname>
```
```
docker push fortia.azurecr.io/showtime:<firstname>
```
```
showtime:
  build: ./app
  image: showtime:<yournamehere>
  hostname: showtime
  container_name: showtime
  ports: 
  - "8080:8080"
```
```
docker compose build showtime
```
```
 docker system prune 
```
```
docker volume prune
```
```
docker swarm init --advertise-addr <your-ip-address>
```
```
docker stack deploy --compose-file docker-compose.yml showtime
```
```
docker stack services showtime
```


```
git clone https://github.com/drozemond/showtime.git
```
```
cd showtime
```
```
docker pull mcr.microsoft.com/mssql/server:latest
```
```
docker images
```
```
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=fortia' -p 1433:1433 -d mcr.microsoft.com/mssql/server:latest
```
```
docker container ls
```
```
docker-compose up rabbitmq 
```
```
docker images
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

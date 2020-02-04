```
docker pull mcr.microsoft.com/mssql/server:latest
```
```
docker images
```

```
docker run \
-e 'ACCEPT_EULA=Y' \
-e 'SA_PASSWORD=fortia' \
-p 1433:1433 \
-d mcr.microsoft.com/mssql/server:latest
```

```
docker container ls
```

```
version: '3.7'
services:

    mssql: 
        image: mcr.microsoft.com/mssql/server
        container_name: mssql
        ports:
            - "1433:1433"
        environment:
            - ACCEPT_EULA=Y
            - SA_PASSWORD=fortia

rabbitmq:
image: rabbitmq:3.7.15-management
       	hostname: rabbitmq
       	container_name: rabbitmq
       	ports:
           - "5672:5672"
           - "15672:15672"

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

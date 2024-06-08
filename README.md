### Prerequisites

Docker

### Windows Docker volume location

\\wsl$\docker-desktop-data\version-pack-data\community\docker\volumes

#

### MYSQL Server Commands

Refer to https://hub.docker.com/_/mysql

#### Getting image

```shell
$   docker pull mysql:latest
```

#### Creating instance with data volume attached

```shell
 $  docker run --name lets-go-mysql -p 33060:3306 -v /c/Development/TutorialsDev/lets-go/mysql/:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:latest
```

#### Docker container start

```shell
$   docker container start lets-go-mysql
```

#### Connecting to container

```shell
$  docker exec -it lets-go-mysql bash 
```

#### Accessing MYSQL 

```shell
$   mysql -u root -p
$   my-secret-pw
```

```shell
$   mysql -D snippetbox -u web -p
$   pass
```

### SQL Commands

```shell
$   SELECT * FROM snippets;
```

### GO Commands

#### Start server

```shell
$   go run ./cmd/web
```

#### To generate TLS self-signed certificate

adjust based on go directory location

```shell
$   go run /c/'Program Files'/Go/src/crypto/tls/generate_cert.go --rsa-bits=2048 --host=localhost
```

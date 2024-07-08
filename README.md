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
 $  docker run --name go-webserver-mysql -p 33060:3306 -v go-webserver-mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:latest
```

#### Docker container start

```shell
$   docker container start go-webserver-mysql
```

#### Connecting to container

```shell
$  docker exec -it go-webserver-mysql bash 
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

#### To build binary and copy existing TLS certificate

```shell
$   go build -o ./tmp/web ./cmd/web/
$   cp -r ./tls ./tmp/
$   cd ./tmp/
$   ./web
```


### GO Test Commands

#### Run all short tests

```shell
$   go test -short ./...
```

#### Run specific test

```shell
$   go test -v -run="^TestPing$" ./cmd/web/
```

#### Run specific sub-test

```shell
$   go test -v -run="^TestHumanDate$/^UTC$" ./cmd/web
```

#### Skip specific test and not cache if ran multiple times

```shell
$   go test -v -skip="^TestHumanDate$" -count=1 ./cmd/web/
```

#### Check test coverage

```shell
$   go test -cover ./...
```

#### Save test coverage

```shell
$   go test -coverprofile=./tmp/profile.out ./...
```

#### Read test coverage

```shell
$   go tool cover -html=/tmp/profile.out
```
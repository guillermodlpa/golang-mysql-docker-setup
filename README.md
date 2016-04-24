# Docker: Golang web + MySQL

Reusable docker setup to start writing web apps with the [Go Programing Language](https://golang.org/). Generates a web container with Go and a db container with MySQL.

Requirements: Go, [Docker](https://www.docker.com/) and a [Go workspace](https://golang.org/doc/code.html#Workspaces).

Steps:

```
# cd into workspace directory
cd $GOPATH

# Clone the project
go get github.com/gpuenteallott/golang-mysql-docker-setup

# cd into project directory
cd src/github.com/gpuenteallott/golang-mysql-docker-setup

# Run containers
docker-compose build
docker-compose up -d

# Confirm it all went up correctly. Exit with Ctrl+C
docker-compose logs
```

The host machine workspace folder will be mounted in the web container in `/go`.

### Starting a Revel app

With [Revel](https://revel.github.io/), a web framework for Go, you can start your app by simply doing:

```
docker ssh -ti golangmysqldockersetup_web_1 bash

revel run github.com/[your user]/[your repo name] dev 9000
```

TODO: Solve the problem of hot code reloading when modyfing files on the host machine. VirtualBox doesn't propagate file change events to the guest.

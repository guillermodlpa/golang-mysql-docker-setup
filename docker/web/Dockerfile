# Telling to use Docker's golang ready image
FROM golang

MAINTAINER Guillermo de la Puente <g.puente.allott@gmail.com>

EXPOSE 8080 80 443

# Set pwd to the go folder
WORKDIR ${GOPATH}

RUN apt-get update -y && \
	apt-get install -y \
	vim

# Install and build binaries revel for this server
RUN go get github.com/revel/revel
RUN go get github.com/revel/cmd/revel

# Copy the entrypoint file
ADD /docker/web/infinite_loop.sh /infinite_loop.sh
RUN chmod +x /infinite_loop.sh

# Start process
ENTRYPOINT ["/infinite_loop.sh"]
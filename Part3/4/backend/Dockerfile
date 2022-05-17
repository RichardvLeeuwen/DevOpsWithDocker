FROM ubuntu:20.04

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

ENV PATH=$PATH:/usr/local/go/bin

RUN apt-get update &&\
apt-get install wget -y &&\
wget https://golang.org/dl/go1.16.5.linux-amd64.tar.gz &&\
tar -xzf go1.16.5.linux-amd64.tar.gz -C /usr/local/ &&\
go build &&\
rm -rf go1.16.5.linux-amd64.tar.gz &&\
apt-get purge -y --auto-remove curl &&\
    rm -rf /var/lib/apt/lists/* &&\
    useradd -m reguser


USER reguser

ENV PORT=8080
ENV REQUEST_ORIGIN=http://localhost:5000


CMD ./server 
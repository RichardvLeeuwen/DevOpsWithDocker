FROM golang:1.16

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build
RUN useradd -m reguser

USER reguser

ENV PORT=8080
ENV REQUEST_ORIGIN=http://localhost:5000


CMD ./server 
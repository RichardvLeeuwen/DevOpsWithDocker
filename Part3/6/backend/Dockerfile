FROM golang:1.16 as build-stage

WORKDIR /usr/src/app

COPY . .

RUN CGO_ENABLED=0 go build

FROM scratch

EXPOSE 8080

COPY --from=build-stage /usr/src/app/server /usr/src/app/server

ENV PORT=8080
ENV REQUEST_ORIGIN=http://localhost:5000


ENTRYPOINT ["/usr/src/app/server"] 
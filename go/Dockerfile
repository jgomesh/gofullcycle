FROM golang:latest as buildGO

WORKDIR /go/src/app

COPY . .

RUN go mod init
RUN go build -o /fc_rocks

FROM scratch

WORKDIR /

COPY --from=buildGO /fc_rocks /fc_rocks

ENTRYPOINT [ "/fc_rocks" ]
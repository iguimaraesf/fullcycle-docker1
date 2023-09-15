FROM golang:1.21 as gohello

WORKDIR /go/src

COPY . .
RUN go build
RUN mv ./oifullcycle /go/bin

ENTRYPOINT [ "/go/bin/oifullcycle" ]

FROM scratch

COPY --from=gohello /go/bin/oifullcycle /app/oifullcycle

ENTRYPOINT [ "/app/oifullcycle" ]

FROM golang:alpine AS builder

WORKDIR $GOPATH/src/app

COPY . .

RUN CGO_ENABLED=0 go build -o /app hello.go

FROM scratch

COPY --from=builder /app .

CMD ["/app"]
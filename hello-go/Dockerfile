FROM golang:1.21 AS builder

WORKDIR /usr/src/app
COPY . .
RUN go build -v -o /usr/local/bin/hello-go ./...
CMD ["hello-go"]

FROM scratch
COPY --from=builder /usr/local/bin/hello-go /hello-go
CMD [ "/hello-go" ]
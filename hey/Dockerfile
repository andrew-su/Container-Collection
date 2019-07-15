FROM golang:latest as build-env

RUN go get -u github.com/rakyll/hey
RUN go build -o /go/bin/app github.com/rakyll/hey

FROM gcr.io/distroless/base
COPY --from=build-env /go/bin/app /
CMD ["/app"]

FROM golang:1.7-alpine AS builder
RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories \
    && apk --update add glide git \
    && git clone https://github.com/ContainerSolutions/prometheus-swarm-discovery.git /go/src/github.com/ContainerSolutions/prometheus-swarm-discovery/ \
    && cd /go/src/github.com/ContainerSolutions/prometheus-swarm-discovery/ \
    && mkdir -p /app \
    && glide install \
    && CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o /app/main /go/src/github.com/ContainerSolutions/prometheus-swarm-discovery/swarm.go

FROM alpine:3.6
COPY --from=builder /app/main /promswarm
ENTRYPOINT ["/promswarm", "discover"]

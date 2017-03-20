FROM alpine
RUN apk add --no-cache ca-certificates wget && \
    RELEASE=$(wget -qO- https://storage.googleapis.com/kubernetes-release/release/stable.txt) && \
    URL="https://storage.googleapis.com/kubernetes-release/release/${RELEASE}/bin/linux/amd64/kubectl" && \
    wget "$URL" -O /usr/bin/kubectl && \
    chmod 755 /usr/bin/kubectl
ENTRYPOINT ["/bin/sh"]

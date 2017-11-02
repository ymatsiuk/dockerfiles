FROM alpine:3.6
RUN apk add --no-cache --virtual build-dependencies ca-certificates wget \
    && RELEASE=$(wget -qO- https://storage.googleapis.com/kubernetes-release/release/stable.txt) \
    && URL="https://storage.googleapis.com/kubernetes-release/release/${RELEASE}/bin/linux/amd64/kubectl" \
    && wget "$URL" -O /usr/bin/kubectl \
    && chmod 755 /usr/bin/kubectl \
    && apk del build-dependencies
ENTRYPOINT ["/usr/bin/kubectl"]

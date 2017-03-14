FROM alpine
RUN apk --no-cache add curl && \
    RELEASE=$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt) && \
    curl -L https://storage.googleapis.com/kubernetes-release/release/$RELEASE/bin/linux/amd64/kubectl -o /usr/bin/kubectl && \
    chmod 755 /usr/bin/kubectl
ENTRYPOINT ["/bin/sh"]

# Run kafka-cli to check/troubleshoot you environment
#
# Kubernetes:
# kubectl run --rm --image=ymatsiuk/kafka-cli -i --tty bash -n $NAMESPACE 
#
# Docker:
# docker run --rm ymatsiuk/kafka-cli  -i 
#

FROM java:8-jdk-alpine

# check versions here -> https://kafka.apache.org/downloads
ENV SCALA_VER 2.12
ENV KAFKA_VER 0.10.2.0

RUN apk --no-cache add curl && \
    curl -L http://apache.40b.nl/kafka/$KAFKA_VER/kafka_$SCALA_VER-$KAFKA_VER.tgz -o kafka_$SCALA_VER-$KAFKA_VER.tgz  && \
    tar xzf kafka_$SCALA_VER-$KAFKA_VER.tgz && \
    rm kafka_$SCALA_VER-$KAFKA_VER.tgz && \
    find /kafka_$SCALA_VER-$KAFKA_VER/bin/ -name \*.sh  -exec ln -s {} /bin/ \;

ENTRYPOINT ["/bin/sh"]

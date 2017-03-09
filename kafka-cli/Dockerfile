# Run kafka-cli to check/troubleshoot you environment
#
# Kubernetes:
# kubectl run --rm --image=ymatsiuk/kafka-cli -i --tty bash -n $NAMESPACE 
#
# Docker:
# docker run --rm --image=ymatsiuk/kafka-cli  -i --tty bash
#

FROM java:8-jdk-alpine

# check versions here -> https://kafka.apache.org/downloads
ENV SCALA_VER 2.12
ENV KAFKA_VER 0.10.2.0

RUN apk --no-cache add curl vim bash bind-tools iproute2 iputils ca-certificates wget

RUN wget -q http://www-eu.apache.org/dist/kafka/$KAFKA_VER/kafka_$SCALA_VER-$KAFKA_VER.tgz && \
 tar xzf kafka_$SCALA_VER-$KAFKA_VER.tgz && \
 rm kafka_$SCALA_VER-$KAFKA_VER.tgz && \
 find /kafka_$SCALA_VER-$KAFKA_VER/bin/ -name \*.sh  -exec ln -s {} /bin/ \;

CMD bash

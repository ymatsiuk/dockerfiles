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
ENV SCALA_VER="2.11" \
    KAFKA_VER="0.10.1.1" \
    APACHE_URL="apache.40b.nl"

RUN apk --no-cache add curl \
    && curl -sL http://${APACHE_URL}/kafka/${KAFKA_VER}/kafka_${SCALA_VER}-${KAFKA_VER}.tgz -o kafka_${SCALA_VER}-${KAFKA_VER}.tgz \
    && tar xzf kafka_${SCALA_VER}-${KAFKA_VER}.tgz \
    && rm kafka_${SCALA_VER}-${KAFKA_VER}.tgz \
    && find /kafka_${SCALA_VER}-${KAFKA_VER}/bin/ -name \*.sh  -exec ln -s {} /bin/ \;

CMD ["tail", "-f", "/dev/null"]

FROM alpine:3.6

ENV CASSANDRA_VERSION=3.11.0 \
    CASSANDRA_HOME=/opt/cassandra

RUN apk add --update --no-cache --virtual=build-dependencies wget ca-certificates tar && \
    mkdir -p ${CASSANDRA_HOME} && \
    wget http://artfiles.org/apache.org/cassandra/${CASSANDRA_VERSION}/apache-cassandra-${CASSANDRA_VERSION}-bin.tar.gz -P /tmp && \
    tar -xvzf /tmp/apache-cassandra-${CASSANDRA_VERSION}-bin.tar.gz && \
    mv /apache-cassandra-${CASSANDRA_VERSION}/* ${CASSANDRA_HOME} && \
    rm -rf /apache-cassandra-${CASSANDRA_VERSION} && \
    apk del build-dependencies && \
    apk add python && \
    rm -rf ${CASSANDRA_HOME}/javadoc && \
    rm -rf ${CASSANDRA_HOME}/doc && \
    rm -rf /tmp/*

CMD ["tail", "-f", "/dev/null"]

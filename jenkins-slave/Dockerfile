# docker run --rm -it -p 50000:50000 ymatsiuk/jenkins-slave -username USER -password PASSWORD -master JENKINS_URL -name NAME -labels LABEL

# kubectl run --rm -it IMAGE_NAME --image=ymatsiuk/jenkins-slave -n NAMESPACE -- -username USER -password PASSWORD -master JENKINS_URL -name NAME -labels LABEL

FROM java:8-jre-alpine

ENV SWARM_VERSION=3.3
ENV SWARM_CLIENT_URL="https://repo.jenkins-ci.org/releases/org/jenkins-ci/plugins/swarm-client/${SWARM_VERSION}/swarm-client-${SWARM_VERSION}.jar"

RUN apk add --no-cache ca-certificates wget && \
	wget -q "${SWARM_CLIENT_URL}" -O swarm-client.jar

# where OPT_SWARM_ARGS could be found here:
# https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin
# example: OPT_SWARM_ARGS="-username slave_user -password slave_password -label slave_label"

ENTRYPOINT ["java", "-jar", "swarm-client.jar"]

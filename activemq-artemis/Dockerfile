FROM openjdk:8-jre-alpine

LABEL MAINTAINER nmahoude@gmail.com

ENV ARTEMIS_VERSION=1.5.2

#update image
RUN apk update && apk upgrade

# get artemis package
RUN wget http://www-us.apache.org/dist/activemq/activemq-artemis/${ARTEMIS_VERSION}/apache-artemis-${ARTEMIS_VERSION}-bin.tar.gz -P /var/opt/
RUN cd /var/opt && \
    tar xzf apache-artemis-${ARTEMIS_VERSION}-bin.tar.gz && \
    mv apache-artemis-${ARTEMIS_VERSION} apache-artemis

# create broker
RUN cd /var/opt/apache-artemis && \
    ./bin/artemis create broker --user admin --password admin --role admin --allow-anonymous

# run broker
ENTRYPOINT ["/var/opt/apache-artemis/broker/bin/artemis", "run"]

EXPOSE 8161 61616 5445 5672 1883 61613
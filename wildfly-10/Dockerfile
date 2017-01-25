FROM nmahoude/java

MAINTAINER nmahoude@gmail.com

ENV INSTALL_DIR=/opt
ENV WILDFLY_HOME=${INSTALL_DIR}/wildfly-10.0.0.Final

RUN curl -O http://download.jboss.org/wildfly/10.0.0.Final/wildfly-10.0.0.Final.zip
RUN unzip wildfly-10.0.0.Final.zip -d ${INSTALL_DIR}

RUN chmod a+x ${WILDFLY_HOME}/bin/standalone.sh

#clean up
RUN rm wildfly-10.0.0.Final.zip

# to deploy applications !
ENV DEPLOYMENT_DIR ${WILDFLY_HOME}/standalone/deployments/

# with admin console exposed {NOT SAFE}
ENTRYPOINT ${WILDFLY_HOME}/bin/standalone.sh -b=0.0.0.0 -bmanagement=0.0.0.0
EXPOSE 8080
EXPOSE 9990

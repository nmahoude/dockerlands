FROM nmahoude/wildfly

LABEL maintainer nmahoude@gmail.com

#add admin user
RUN ${WILDFLY_HOME}/bin/add-user.sh admin admin --silent


ENTRYPOINT ${WILDFLY_HOME}/bin/standalone.sh -b=0.0.0.0 -bmanagement=0.0.0.0
EXPOSE 9990

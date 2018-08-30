FROM jboss/keycloak:4.3.0.Final
LABEL maintainer "OpenStandia"

# Set to Japan time
USER root
RUN unlink /etc/localtime && ln -s /usr/share/zoneinfo/Japan /etc/localtime
USER jboss

# add cli files
ADD cli /opt/jboss/keycloak/cli
# Run standalone-ha-configuration.cli
RUN cd /opt/jboss/keycloak && bin/jboss-cli.sh --file=cli/standalone-ha-configuration.cli && rm -rf /opt/jboss/keycloak/standalone/configuration/standalone_xml_history

ENV JBOSS_HOME /opt/jboss/keycloak

EXPOSE 8080
EXPOSE 9990

CMD ["-b", "0.0.0.0", "-c", "standalone-ha.xml"]
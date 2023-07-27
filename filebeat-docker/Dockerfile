ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/beats/filebeat:${ELASTIC_VERSION}

USER root

#ARG COMPOSE_PROJECT_NAME

COPY filebeat.yml /usr/share/filebeat/filebeat.yml
COPY modules.d/*  /usr/share/filebeat/modules.d

#RUN sed -i "s/\${COMPOSE_PROJECT_NAME}/$COMPOSE_PROJECT_NAME/g" /usr/share/filebeat/filebeat.yml


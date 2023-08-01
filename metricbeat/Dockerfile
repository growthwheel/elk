ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/beats/metricbeat:${ELASTIC_VERSION}

USER root

#ARG COMPOSE_PROJECT_NAME

COPY metricbeat.yml /usr/share/metricbeat/metricbeat.yml
#COPY modules.d/*  /usr/share/metricbeat/modules.d

#RUN sed -i "s/\${COMPOSE_PROJECT_NAME}/$COMPOSE_PROJECT_NAME/g" /usr/share/filebeat/filebeat.yml


FROM ubuntu:20.04

ARG USER_UID
ARG USER_GID

RUN apt-get update && apt-get install -y rsyslog && apt-get install -y logrotate

COPY rsyslog/100-cron.conf /etc/rsyslog.d/100-cron.conf

RUN adduser logrotate

RUN usermod -u ${USER_UID} logrotate
RUN groupmod -g ${USER_GID} logrotate

COPY cron/logrotate /tmp/logrotate

COPY logrotate/* /etc/logrotate.d/

#USER logrotate
#USER root

RUN /usr/bin/crontab < /tmp/logrotate

COPY start.sh /start.sh
RUN chmod +x /start.sh

CMD ["/start.sh"]

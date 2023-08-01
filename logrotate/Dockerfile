FROM ubuntu:20.04

ARG USER_UID
ARG USER_GID

RUN apt-get update && apt-get install -y rsyslog && apt-get install -y logrotate

COPY rsyslog/100-cron.conf /etc/rsyslog.d/100-cron.conf


COPY cron/logrotate /tmp/logrotate

COPY logrotate/* /etc/logrotate.d/
RUN chmod 600 /etc/logrotate.d/*

RUN /usr/bin/crontab < /tmp/logrotate

COPY start.sh /start.sh
RUN chmod +x /start.sh

CMD ["/start.sh"]

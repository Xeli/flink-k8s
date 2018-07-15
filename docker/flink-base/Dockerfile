FROM flink:1.5.0

COPY config /opt/flink/conf

COPY docker-entrypoint.sh /opt/
RUN chmod +x /opt/docker-entrypoint.sh

RUN chown flink:flink /opt/*

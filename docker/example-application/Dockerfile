FROM flink-base:1.0

COPY deployable.jar /opt/deployable.jar
RUN chown flink:flink /opt/deployable.jar

COPY start-job /opt/start-job
RUN chown flink:flink /opt/start-job
RUN chmod +x /opt/start-job

ENTRYPOINT ["/opt/start-job"]

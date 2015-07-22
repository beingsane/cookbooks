FROM npalm/java:oracle-java8
MAINTAINER Bruno Wego <brunowego@gmail.com>

ENV SONAR_VERSION 5.1.1

RUN echo "deb http://downloads.sourceforge.net/project/sonar-pkg/deb binary/" >> /etc/apt/sources.list \
    && apt-get update && apt-get clean \
    && apt-get install -y --force-yes sonar=${SONAR_VERSION} \
    && rm -rf /var/lib/apt/lists/*

COPY init /sonar/init
COPY conf/* /sonar/conf/

RUN chmod 755 /sonar/init

VOLUME /opt/sonar/extensions /opt/sonar/logs /opt/sonar/conf

EXPOSE 80

ENTRYPOINT ["/sonar/init"]

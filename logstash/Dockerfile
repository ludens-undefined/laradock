ARG ELK_VERSION
FROM logstash:${ELK_VERSION}

USER root
RUN rm -f /usr/share/logstash/pipeline/logstash.conf
RUN curl -L -o /usr/share/logstash/lib/mysql-connector-java-8.0.28.jar https://repo1.maven.org/maven2/mysql/mysql-connector-java/8.0.28/mysql-connector-java-8.0.28.jar
ADD ./pipeline/ /usr/share/logstash/pipeline/
ADD ./config/ /usr/share/logstash/config/

RUN logstash-plugin install logstash-input-beats


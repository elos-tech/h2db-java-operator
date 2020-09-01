FROM fabric8/java-centos-openjdk8-jre:latest

ENV URL https://h2database.com/h2-2019-10-14.zip

RUN curl ${URL} -o /tmp/h2.zip \
    && gunzip /tmp/h2.zip -d /opt/ \
    && rm /tmp/h2.zip 

EXPOSE 8081 1521

VOLUME ["/opt/h2-data"]

CMD java -cp /opt/h2/bin/h2*.jar org.h2.tools.Server \
 	-web -webAllowOthers -webPort 8081 \
 	-tcp -tcpAllowOthers -tcpPort 1521 \
 	-baseDir /opt/h2-data
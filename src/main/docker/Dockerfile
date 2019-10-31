FROM openjdk:11-jre-slim-stretch

ENV SPRING_OUTPUT_ANSI_ENABLED=ALWAYS \
    JHIPSTER_SLEEP=0 \
    JAVA_OPTS=""

# Add a jhipster user to run our application so that it doesn't need to 
RUN adduser -D -s /bin/sh jhipster
WORKDIR /home/jhipster

ADD entrypoint.sh entrypoint.sh
RUN chamod 755 entrypoint.sh && chown jhipster:jhipster entrypoint.sh
USER jhipster

ENTRYPOINT [ "./entrypoint.sh" ]

EXPOSE 8080

ADD *.war app.war

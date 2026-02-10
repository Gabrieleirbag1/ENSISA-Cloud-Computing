FROM tomcat:9-jdk17-temurin
RUN rm -rf $CATALINA_HOME/webapps/*
RUN apt-get update && apt-get install -y curl
COPY *.war $CATALINA_HOME/webapps/ROOT.war
EXPOSE 80
HEALTHCHECK --interval=5s --timeout=2s --retries=3 CMD curl -f http://localhost || exit 1
CMD ["catalina.sh", "run"]
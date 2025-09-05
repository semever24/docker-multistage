FROM tomcat:8.0.43-jre8

COPY ./target/helloworld.war /usr/local/tomcat/webapps/

EXPOSE 8080

RUN chmod +x /usr/local/tomcat/bin/catalina.sh

CMD ["catalina.sh", "run"]
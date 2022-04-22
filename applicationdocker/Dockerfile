FROM ubuntu:20.04
ENV JAVA_HOME=/app/middleware/openjdk-11+28_linux-x64_bin/jdk11
ENV TOMCAT_HOME=/app/middleware/apache-tomcat-9.0.62
ENV PATH=${PATH}:${JAVA_HOME}/bin:${TOMCAT_HOME}/bin
RUN mkdir -p /app/middleware
WORKDIR /app/middleware
ADD https://download.java.net/openjdk/jdk11/ri/openjdk-11+28_linux-x64_bin.tar.gz
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.62/bin/apache-tomcat-9.0.62.tar.gz
RUN tar -xvf openjdk-11+28_linux-x64_bin.tar.gz
RUN tar -xvf apache-tomcat-9.0.62.tar.gz
WORKDIR /sample_application
COPY /target/applicationdocker.war tomcat-9.0.62/webapps/
EXPOSE 8080
CMD [ "catalina.sh" ]

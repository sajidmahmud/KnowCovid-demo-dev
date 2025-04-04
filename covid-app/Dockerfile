FROM mizzouceri/tomcat-mvn-java11:V1
MAINTAINER Songjie Wang "wangso@missouri.edu"

# Fix Debian repository issues
RUN sed -i 's|deb.debian.org/debian buster|deb.debian.org/debian oldoldstable|g' /etc/apt/sources.list && \
    sed -i 's|security.debian.org/debian-security buster|security.debian.org/debian-security oldoldstable|g' /etc/apt/sources.list

RUN apt-get -y update && apt-get -y install lsb-release net-tools nano
RUN apt-get -y install default-mysql-server maven

WORKDIR /root 
ADD Covid19-website /root/Covid19-website

WORKDIR /root/Covid19-website


# RUN mvn clean package
# RUN cp /root/Covid19-website/target/*.war /usr/local/tomcat/webapp/Covid-19.war
COPY Covid19-website/src/main/resources/static/js/ng-table.js /usr/local/tomcat/webapps/ROOT/js/

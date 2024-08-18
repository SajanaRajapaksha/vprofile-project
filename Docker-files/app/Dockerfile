FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt-get install maven -y
RUN git clone https://github.com/SajanaRajapaksha/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11
LABEL "Project" = "vprofile"
LABEL "Author" = "sajana"
#remove default tomcat application
RUN rm -rf /usr/local/tomcat/webapps/*
#copy the artfact created from mvn install to tomcat default web app location
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
#run the default tomcat server
CMD ["catalina.sh", "run"]



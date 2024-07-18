FROM openjdk:11 AS BUILD_NAME
RUN apt update && apt install maven -y
RUN git clone https://github.com/prashantriyal/vprofile-project.git

#goes to vprofile folder changes the branch  and install mvn
RUN cd vprofile-project && git checkout docker && mvn install  

FROM tomcat:9-jre11
LABEL "Project"="Vprofile"
LABEL "Author"="Prashant"

#remove the default artifacts from dafault location
RUN rm -rf /usr/local/tomcat/webapps/*  

#copies the openjdk artifact from 1st to 2nd path
COPY --from=BUILD_NAME vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
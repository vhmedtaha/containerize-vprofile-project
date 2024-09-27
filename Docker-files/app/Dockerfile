FROM openjdk:11 AS build

RUN apt update && apt install maven -y

RUN git clone https://github.com/vhmedtaha/containerize-vprofile-project.git 

RUN cd containerize-vprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11 

RUN rm -rf /usr/local/tomcat/webapps/*

COPY --from=build /containerize-vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080 

CMD ["catalina.sh", "run"]


#app dockerfile
# Stage 1: Build the application
FROM maven:3.9.9-eclipse-temurin-21-jammy AS BUILD_IMAGE

# Clone the repository and build the project
RUN git clone https://github.com/Aamir-033/vprofile-project-1.git
WORKDIR /vprofile-project-1
RUN git checkout containers && mvn install

# Stage 2: Create the deployment image
FROM tomcat:10-jdk21

# Clean default Tomcat webapps and deploy the built WAR file
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE /vprofile-project-1/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# Expose port 8080 and run Tomcat
EXPOSE 8080
CMD ["catalina.sh", "run"]

FROM maven:3.6-jdk-8-slim AS build
COPY src /home/app/src
COPY pom.xml /home/app
RUN cd /home/app && mvn -f /home/app/pom.xml clean test package
RUN cp -R /home/app/lib /home/app/target/
RUN cd /home/app/target
WORKDIR /home/app/target

expose 8081
CMD java -jar /home/app/target/ChatBroadcastSSE-1.0.jar de.affinitas.chat.service.ChatBroadcastSSEService

FROM openjdk:8-jdk-alpine

RUN mkdir -p /opt/build 
ADD ./ /opt/build
WORKDIR /opt/build

RUN chmod +x gradlew


RUN ./gradlew build -x test \
    && cp ./build/libs/customer-service-0.0.1-SNAPSHOT.jar customer-service-0.0.1-SNAPSHOT.jar

EXPOSE 8074
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","./customer-service-0.0.1-SNAPSHOT.jar"]
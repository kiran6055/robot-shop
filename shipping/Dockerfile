FROM    almalinux as build
RUN     yum update -y && yum install maven -y
WORKDIR /opt/shipping
COPY    pom.xml /opt/shipping
COPY    src* /opt/shipping
RUN mvn dependency:resolve
RUN     mvn package

FROM openjdk:8-jre-alpine
EXPOSE 8080
WORKDIR /opt/shipping
ENV DB_HOST=mysql
ENV CART_ENDPOINT=cart:8080
COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar
CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]


#FROM debian:10 AS build
#RUN apt-get update && apt-get -y install maven
#WORKDIR /opt/shipping
#COPY pom.xml /opt/shipping/
#RUN mvn dependency:resolve
#COPY src /opt/shipping/src/
#RUN mvn package

#FROM openjdk:8-jdk
#EXPOSE 8080
#WORKDIR /opt/shipping
#ENV CART_ENDPOINT=cart:8080
#ENV DB_HOST=mysql
#COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar
#CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]

FROM lwieske/java-8
VOLUME /tmp
ADD registerserver-1.0.jar /app.jar
EXPOSE 8761
ENTRYPOINT ["java", "-jar", "/app.jar"]

FROM lwieske/java-8
VOLUME /var/jenkins_home/workspace/registerserver/target/
ADD registerserver-1.0.jar /app.jar
EXPOSE 8761
ENTRYPOINT ["java", "-jar", "/app.jar"]

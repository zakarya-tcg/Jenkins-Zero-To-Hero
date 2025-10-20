FROM openjdk:21-jdk-slim
ARG artifact=target/spring-boot-web.jar
WORKDIR /opt/app
COPY ${artifact} app.jar
RUN test -f /opt/app/app.jar && echo "✅ Fichier vérifié avec succès" || (echo "❌ Fichier manquant" && exit 1)
ENTRYPOINT ["java","-jar","app.jar"]

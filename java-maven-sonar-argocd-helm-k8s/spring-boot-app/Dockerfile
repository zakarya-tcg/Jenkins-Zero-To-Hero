FROM openjdk:21-jdk-slim
WORKDIR /opt/app

# Solution générique - copie TOUS les fichiers JAR
COPY target/*.jar app.jar

# Vérification
RUN ls -la /opt/app/app.jar && echo "✅ Build réussi!"

ENTRYPOINT ["java","-jar","app.jar"]

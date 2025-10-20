FROM openjdk:21-jdk-slim

WORKDIR /opt/app

# Debug du build context
RUN echo "=== DEBUG DOCKER ===" && \
    find . -name "*.jar" -type f 2>/dev/null || echo "Aucun JAR trouvé"

# Copie avec vérification
COPY java-maven-sonar-argocd-helm-k8s/spring-boot-app/target/*.jar app.jar

# Vérification finale
RUN if [ -f /opt/app/app.jar ]; then \
        echo "✅ SUCCÈS: Fichier JAR copié" && \
        ls -lh /opt/app/app.jar; \
    else \
        echo "❌ ÉCHEC: Aucun JAR copié" && \
        find /opt/app -type f && \
        exit 1; \
    fi

ENTRYPOINT ["java","-jar","app.jar"]

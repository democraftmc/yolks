FROM container-registry.oracle.com/graalvm/jdk:25-ol10

# Chemin du vrai keystore Java
ENV CACERTS_PATH=/usr/lib64/graalvm/graalvm-java25/lib/security/cacerts

# Copier ton certificat
COPY lycee.crt /tmp/lycee.crt

# Importer le certificat dans cacerts
RUN keytool -importcert \
    -noprompt \
    -trustcacerts \
    -alias lycee \
    -file /tmp/lycee.crt \
    -keystore $CACERTS_PATH \
    -storepass changeit

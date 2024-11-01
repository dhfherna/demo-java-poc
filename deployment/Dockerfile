FROM amazoncorretto:17-alpine@sha256:d7ac7ae33ee93cd88703611c59596e3e30c87c78eae2b1f8f2f81ed5c89b2cf3
VOLUME /tmp
COPY *.jar demo-java-poc.jar
ENV JAVA_OPTS=" -Xshareclasses:name=cacheapp,cacheDir=/cache,nonfatal -XX:+UseContainerSupport -XX:MaxRAMPercentage=70 -Djava.security.egd=file:/dev/./urandom"
# Replace with a non-root user to avoid running the container with excessive privileges
USER appuser
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS  -jar demo-java-poc.jar" ]

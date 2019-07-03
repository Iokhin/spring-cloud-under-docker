FROM java:8
ADD ./target/config-0.0.1.jar .
EXPOSE 8888
ENTRYPOINT exec /usr/bin/java -jar ./config-0.0.1.jar
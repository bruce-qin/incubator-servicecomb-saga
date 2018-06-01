FROM java:openjdk-8-jre-alpine
VOLUME /tmp
ADD alpha-server-exec.jar app.jar
#RUN bash -c 'touch /app.jar'
RUN touch /app.log
#暴露容器端口
EXPOSE 8899
EXPOSE 8989
ENTRYPOINT ["nohup","java","-Djava.security.egd=file:/dev/./urandom","-Djava.net.preferIPv4Stack=true","-server", "-Xms512m","-Xmx1g","-XX:MetaspaceSize=256m","-XX:MaxMetaspaceSize=256m","-Xmn128m","-Xss256k","-XX:+DisableExplicitGC","-XX:+UseConcMarkSweepGC","-XX:+CMSParallelRemarkEnabled","-XX:LargePageSizeInBytes=128m","-XX:+UseFastAccessorMethods","-XX:+UseCMSInitiatingOccupancyOnly","-XX:CMSInitiatingOccupancyFraction=70","-jar","/app.jar","> /app.log 2>&1 &"]

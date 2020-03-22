FROM jdk1.8
VOLUME /tmp
ADD docker-demo-0.0.1-SNAPSHOT.jar app.jar
ENV JAVA_OPTS="\
-server \
-Xmx256m \
-Xms256m \
-Xmn128m \
-XX:SurvivorRatio=8 \
-XX:MetaspaceSize=56m \
-XX:MaxMetaspaceSize=56m \
-XX:+UseParallelGC \
-XX:ParallelGCThreads=4 \
-XX:+UseParallelOldGC \
-XX:+UseAdaptiveSizePolicy \
-XX:+PrintGCDetails \
-XX:+PrintTenuringDistribution \
-XX:+PrintGCTimeStamps \
-XX:+HeapDumpOnOutOfMemoryError \
-XX:HeapDumpPath=/ \
-Xloggc:/gc.log \
-XX:+UseGCLogFileRotation \
-XX:NumberOfGCLogFiles=5 \
-XX:GCLogFileSize=10M"

#ENTRYPOINT ["java","$JAVA_OPTS -Djava.security.egd=file:/dev/./urandom","-jar","app.jar"]

ENTRYPOINT java ${JAVA_OPTS} -Djava.security.egd=file:/dev/./urandom -jar  app.jar
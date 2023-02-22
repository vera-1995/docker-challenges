#use image base regarding the version of JAVA used in pom.xml
FROM eclipse-temurin:11

#copy the jar file to this image
COPY java_helloworld.jar .

# execute .jar
CMD [ "java", "-jar", "java_helloworld.jar" ]
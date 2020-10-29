# SpringProfile
Sample spring project using Spring Profiles, automation Test and deploy in Cloud, through Docker image. 

# Import Step for Configuration Docker image. 

1- Create a sample file "Dockerfile" and need to pass the parameters bellow

*FROM openjdk:8-jdk-alpine
*RUN addgroup -S spring && adduser -S spring -G spring
*USER spring:spring
*ARG JAR_FILE=target/*.jar
*COPY ${JAR_FILE} app.jar
*ENTRYPOINT ["java","-Xmx512m","-Dserver.port=${PORT}","-jar","/app.jar"]

*if do deploy heroky need to pass the values "ENTRYPOINT" inside heroku app, instead of command line, have options settings inside your application where you can write the values

2- Follow the steps to create a image for the project, for create a docker image the project need to be .jar application and not .war 

# Challenge 4
### Run “Hello World” Java Project and push image to Docker Hub

In this challenge we'll learn how to
- Create an image to run a `.jar`
- Connect to [Docker Hub](https://hub.docker.com/)
- Publish images to [Docker Hub](https://hub.docker.com/)

Note: The provided HelloWorld maven project is only illustrative of what is present in the 
`.jar`, there is no need to know how to compile/package/run it

### Create and run a jar file in Docker challenge
- Create an image which runs the provided `.jar` file
  - How to run a `.jar` file: `java -jar <.jar path>.jar`
    - Create a Dockerfile with the needed steps (check with version of java we need -> pom.xml)
- Run the image of the previous step
  - Output expected: `Hello world!`
  `docker build -t java11 .  ` (don't forget you have to be in the 'challengeX' folder to run this one)
  `docker run java11`

### Push an image to Docker Hub
- Publish the image of the previous challenge/step to Docker Hub to your repository with the tag 1.0
 1º Register to doocker hub if you dont have an account
 2º Create a new repo
 3º `docker login --username=yourhubusername` or `docker login` (if login is automatically done on PC)
 4º Tag the image: `docker image tag <yourImageName:yourImageTag> <yourHubUsername/repositoryName:NewTag>` -> in owr case `docker image tag java11:latest anykeila/challenge4:1.0`
 5º check `docker images` to see the created tag in the list
 6º push the image to your repo `docker push yourHubUsername/repositoryName:NewTag` -> in owr case `docker push anykeila/challenge4:1.0`
- Remove the published image from your machine and run the image by fetching it from Docker Hub
 '1º `docker image rm -f <image_id>` or `docker -rmi <image_id>` (if it is not being used by any container)
 '2º Go to 'Tags' tab, in docker hub, copy the 'Pull command' on the right side to your command line.
 '3º check `docker images` to confirm that image is created again 
 Another easier way to have the image after deleting it is just to try to run it, if you dont have it locally docker will download it!
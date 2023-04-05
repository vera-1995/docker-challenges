# Challenge 5
### Run “Hello World” REST Service

In this challenge we'll learn how to
- Run a REST Service 
- Name containers 
- Provide environment variables to a container 
- View detached container's logs

Notes: The provided `rest_helloworld` maven project is only illustrative of what is present in the `.jar`, there is no need to know how to compile/package/run it

### Create an image to run a REST service in Docker challenge
- Create an image which runs the provided `.jar` file
  - How to run a `.jar` file: `java -jar <.jar path>.jar`
  -> Build the dockerfile with the from image that can the java version on the pom file.
  -> go to challenge folder and run 'docker build -t challenge5 .'
- Run the image of the previous step detached and give the container a name 
  -> 'docker run -d --name challenge5_container challenge5'
- View the logs of the container to confirm if the application is up 
 -> 'docker logs challenge5_container'
- Do an HTTP request to the endpoint `GET /hello-world`
  - Output expected: `Hello world!`
  -> docker run -d --name challenge5_container -p 8080:8080 challenge5
  -> go to postman and create a get request with http://0.0.0.0:8080/hello-world

### Provide the missing env vars
- The response returned by `GET /hello-world` has two env values missing provide them:
  - Provide the first value through an option of the docker command
  ->docker run -e ORG_EXAMPLE_USER_NAME='any' -d --name challenge5_container -p 8080:8080 challenge5
  - Provide the second value through a file
  ->'docker run -e ORG_EXAMPLE_USER_NAME='any' --env-file ./envvar -d --name challenge5_container -p 8080:8080 challenge5'

### Provide the missing env vars
- The REST service exposes the port 8080, expose this port at port 8095

-> 'docker run -e ORG_EXAMPLE_USER_NAME='any' --env-file ./envVar -d --name challenge5_container -p 8095:8080 challenge5'
## Activity 1: (Online Playground) - https://killercoda.com/playgrounds/scenario/kubernetes
1. Use Play with Docker/kubernetes, a browser-based Docker playground. https://killercoda.com/playgrounds/scenario/kubernetes
2. Access Play with Docker.
3. Visit Play with Docker.
4. Sign in using your Docker Hub/Google account (or create one if you don’t have an account).
5. Start a New Session:
6. Click on “Start” to begin a new session. This will give you a free virtual machine (VM) where Docker is pre-installed.
7. Once the VM is running, you'll be provided with a terminal interface in your browser.
Test Docker Installation:
8. In the Play with Docker terminal, run the following command to verify Docker is working:bash
docker run hello-world 
9. If successful, you will see the same message, "Hello from Docker!", confirming Docker is functioning correctly.

## Activity 2: Pull and Run a Basic Containerized Application
1. Understanding Docker Hub:
    Docker Hub is a public repository for Docker images.
    You can find official and community images on Docker Hub.
2. Pulling a Docker Image:
Pull a simple containerized application from Docker Hub. For this activity, we'll use the nginx web server as an example.
3. In your terminal, run the following command:bash, Copy code
4. docker pull nginx 
5. This command will download the nginx image (a popular lightweight web server) from Docker Hub.
6. Running the Docker Container:
7. Once the image is downloaded, run the container using the following command:bash
8. docker run -d -p 8080:80 nginx 
9. Explanation:
10. -d: Runs the container in detached mode (in the background).
11. -p 8080:80: Maps port 8080 on your host machine to port 80 inside the container (the default HTTP port).
12. nginx: The name of the Docker image you are running.
13. Accessing the Web Application:
14. Open your browser and go to http://localhost:8080 (or http://<your_VM_IP>:8080 if using Play with Docker).
15. You should see the default "Welcome to nginx!" page, confirming that the Nginx web server is running inside the Docker container.


## Activity 3: Pull and Run a Basic Containerized Application
1. List Containers: docker ps
2. Check the logs of the container: docker logs <containerID>
3. Stop the running container: docker stop <containerID>

## Activity 4: Build a container using Dockerfile
1. copy this into Dockerfile
```
FROM alpine
CMD ["echo", "Hello World!"]
```
2. Build using the command in the location where the Dockerfile is created
```
docker build -t my-hello-world .
```

3. Execute the container to see the output
```
docker run my-hello-world
```

4. Check for built images:
```
docker images
```
## Activity 4: Clean-up
1. Remove the container: docker rm <containerID>




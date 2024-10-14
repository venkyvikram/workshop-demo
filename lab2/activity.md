
## 1: (Online Playground)
https://killercoda.com/playgrounds/scenario/kubernetes

## 2: Review the Dockerfile in the lab2 for security best practices
1. Add the below in Dockerfile
```
# Use Base Image
FROM alpine
# Add new user and group
RUN addgroup -S app && adduser -S app -G app
WORKDIR /app
USER app
CMD ["echo", "Hello World!"]
```
2. Build the container using the below command.
```
docker build -t hello-world-without-root-user .
```

3. Execute the container and see for appropriate output "Hello-World"

```
docker run hello-world-without-root-user
```

4. Clear the activities as learned from the previous lab.
```
docker ps
docker stop <container-id>
docker rm <container-id>
```

## 2: Set the resource limit for nginx application
```
docker run --memory=512m --cpus=1 nginx
```
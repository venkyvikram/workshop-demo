# Use Base Image
FROM alpine
# Add new user and group
RUN addgroup -S app && adduser -S app -G app
WORKDIR /app
USER app
CMD ["echo", "Hello World!"]
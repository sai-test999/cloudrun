# Use an appropriate base image for your application.
# This example uses a basic Alpine Linux image.
FROM alpine:latest

# Set the working directory
WORKDIR /app

# Copy your application files (if any)
# For illustrative purposes, we'll use a simple script
COPY hello.sh .

# Expose port 8080
EXPOSE 8080

# Set the user and permissions for the script
RUN adduser -D myuser
USER myuser

# What the container should run when it is started.
CMD ["sh", "-c", "chmod +x hello.sh && ./hello.sh"]

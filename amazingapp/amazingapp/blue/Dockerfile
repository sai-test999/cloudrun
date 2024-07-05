# Stage 1: Build the Go application
FROM golang:1.13 as builder

WORKDIR /app

# Copy the entire source code
COPY . .

# Build the Go application
RUN CGO_ENABLED=0 GOOS=linux go build -o server

# Stage 2: Create a minimal runtime image
FROM alpine:3

# Install certificates needed for HTTPS
RUN apk add --no-cache ca-certificates

# Copy the built binary from the builder stage
COPY --from=builder /app/server /server

# Expose port 8080
EXPOSE 8080

# Command to run the server
CMD ["/server"]

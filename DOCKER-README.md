# Simple Counter - Docker Setup

This document explains how to build and run the Simple Counter React application using Docker.

## Prerequisites

- Docker installed on your machine
- Docker Hub account (if you want to push the image to a public registry)

## Building the Docker Image

1. Build the Docker image:
   ```bash
   docker build -t simple-counter .
   ```

2. Run the container locally:
   ```bash
   docker run -p 3000:80 simple-counter
   ```
   The app will be available at http://localhost:3000

## Pushing to Docker Hub

1. Log in to Docker Hub:
   ```bash
   docker login
   ```

2. Tag your image (replace `yourusername` with your Docker Hub username):
   ```bash
   docker tag simple-counter yourusername/simple-counter:latest
   ```

3. Push the image to Docker Hub:
   ```bash
   docker push yourusername/simple-counter:latest
   ```

## Pulling and Running from Docker Hub

Others can run your public image using:
```bash
docker run -p 3000:80 yourusername/simple-counter:latest
```

## Environment Variables

If your app needs environment variables, you can pass them using the `-e` flag:
```bash
docker run -p 3000:80 -e REACT_APP_API_URL=your_api_url yourusername/simple-counter:latest
```

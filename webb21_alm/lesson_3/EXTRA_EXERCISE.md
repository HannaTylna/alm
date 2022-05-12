# Extra Exercises

## Docker

### Apache httpd

In this extra exercise you should create a dockerfile for apache httpd [Apache httpd official images](https://hub.docker.com/_/httpd)

1. Modify the config or html so the server print your own page. You can extract the default config and html page with your docker client. You can i.e use [docker cp](https://docs.docker.com/engine/reference/commandline/cp/) or [docker exec](https://docs.docker.com/engine/reference/commandline/exec/)
2. Upload the image to GitLab Container Registry.

### Docker images size

Depending on how you build your image, the size will differ. If you follow the best practices and use the correct base image your deploys will be faster and you will consume less disk space.

1. You can use the [python official images](https://hub.docker.com/_/python), read the docs page for more information. Create your Dockerfiles based on the following images:

- python:3.9-buster
- python:3.9-slim
- python:3.9-alpine

1. Run the different official images for Python:

   ```bash
    docker run --rm python:3.9-buster
    docker run --rm python:3.9-slim
    docker run --rm python:3.9-alpine

    # then check the image sizes with
    docker images python
    ```

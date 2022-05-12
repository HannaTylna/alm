# Exercise 3

## Building your own docker image

### Docker Build - Part 1

- You should fork the GitLab project [webb21_alm_nginx](https://gitlab.com/robert-alfwar/webb21_alm_nginx).

You can see a picture of where to click in the [gitlab guide how to create a fork](https://docs.gitlab.com/ee/user/project/repository/forking_workflow.html#creating-a-fork)

1. Clone your forked project
2. Build your Container Image
   1. Make sure your terminal is in the same folder as the `Dockerfile`
   2. Build the Container Image with the [docker build](https://docs.docker.com/engine/reference/commandline/build/) command.

    ```bash
    # Don't forget the . to point out which folder to search for the Dockerfile
    docker build -t <name> .
    ```

3. Test to run locally a Container Instance based of your Container Image

    ```Bash
    # run docker images to make sure your build went successful
    docker images <name> # This should list your newly built container image
    docker run -d -P <name>
    ```

4. Open the nginx page in a browser `localhost:<your port>`

    ```bash
    docker container ls # To find out which port it uses
    ```

5. Modify the body in `index.html` so it prints your username
6. Build the container image again, so the image is updated with your new file
7. Test to run your newly created Container Image locally

    ```Bash
    # run docker images to make sure your build went successful
    docker images <name> # This should list your newly built container image
    docker run -d -P <name>
    ```

8. Open the new nginx page in a browser `localhost:<your port>` make sure it prints your username

    ```bash
    docker container ls # To find out which port it uses
    ```

### GitLab Container Registry - Part 2

1. Login to GitLab Container Registry
    - You find your registry link in GitLab -> Your project -> Packages & Registries -> Container Registry

    - To login you may need to setup a user [password](https://gitlab.com/-/profile/password/edit) if you have signed up with i.e github, gmail. Another alternative is to setup a [personal access token](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html#creating-a-personal-access-token) with the scope `read_registry` and `write_registry`

        ```bash
        docker login registry.gitlab.com
        ```

2. In your application directory, you will need to build the image again with the full repository name.
  
    ```bash
    docker build -t registry.gitlab.com/<your username>/webb21_alm_nginx/<name> .
    docker images # This should list your newly built container image
    ```

3. Finally push your image to GitLab Container Registry:

    ```bash
    docker push registry.gitlab.com/<your username>/webb21_alm_nginx/<name>
    ```

4. Make sure you can see the image in your gitlab container registry <https://gitlab.com/your-username/webb21_alm_nginx/container_registry>

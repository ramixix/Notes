# Dockerfile
A Dockerfile is a text file that contains a set of instructions for building a Docker image. It serves as a blueprint or recipe for creating a reproducible and automated process to build Docker images consistently. Dockerfiles are written using a specific syntax and a predefined set of instructions, allowing developers to define the configuration and dependencies of the desired image.

![](/imgs/dockerfile.png)

In a Dockerfile, you define the steps necessary to build the image, starting from a base image and specifying additional configuration, package installations, environment variables, file copies, and more. The Dockerfile provides a declarative approach to define the desired state of the image and how it should be constructed.

> Here are the key elements and features of a Dockerfile:

1. Base Image: The Dockerfile starts with specifying a base image, which provides the starting point for your image. It can be an official image from the Docker Hub registry or a custom image based on your requirements.

2. Instructions: Dockerfiles consist of various instructions, each performing a specific action. Some commonly used instructions include `FROM`, `RUN`, `COPY`, `ADD`, `WORKDIR`, `ENV`, `EXPOSE`, `CMD`, and `ENTRYPOINT`. Each instruction is responsible for a particular task, such as installing packages, copying files, setting environment variables, or defining the default command to run.

3. Layered Approach: Docker utilizes a layered file system for images. Each instruction in the Dockerfile creates a new layer, representing a specific modification to the image. Layers are cached, and Docker can efficiently reuse them if subsequent builds use the same instructions. This promotes faster and more efficient image building.

4. Build Process: Docker builds an image by executing the instructions defined in the Dockerfile sequentially. Each instruction is executed in its own layer, forming a stack of read-only layers, with the final layer being a writable container layer. The final container layer represents the runtime state of the image.

5. Reproducibility: Dockerfiles ensure reproducibility by capturing the entire build process as a series of instructions. This enables consistent and predictable image creation, ensuring that the resulting image can be recreated across different environments and by different developers.

---

## Commonly Used Instructions in a Dockerfile
```Dockerfile
    FROM: Specifies the base image for the subsequent instructions. Example:
    FROM ubuntu:latest

    RUN: Executes a command during the image build process. Example:
    RUN apt-get update && apt-get install -y package1 package2

    CMD: Defines the default command to run when a container is started. Example:
    CMD ["npm", "start"]

    ENTRYPOINT: Sets the primary command for the container and allows it to be invoked like an executable. Example:
    ENTRYPOINT ["java", "-jar", "app.jar"]

    WORKDIR: Sets the working directory for subsequent instructions. Example:
    WORKDIR /app

    COPY: Copies files or directories from the build context to the image. Example:
    COPY app.js /app/app.js

    ADD: Similar to COPY, but also supports URLs and extracting local archives. Example:
    ADD https://example.com/file.tar.gz /app/

    EXPOSE: Documents the ports that the container listens on at runtime. Example:
    EXPOSE 8080

    ENV: Sets environment variables within the image. Example:
    ENV MY_VAR=value

    ARG: Defines build-time variables that can be passed with the docker build command. Example:
    ARG VERSION

    LABEL: Adds metadata to an image in the form of key-value pairs. Example:
    LABEL version="1.0" maintainer="John Doe"

    VOLUME: Creates a mount point for a volume to persist data. Example:
    VOLUME /data

    USER: Sets the user that will run subsequent commands in the Dockerfile. Example:
    USER myuser

    SHELL: Specifies the default shell used by the shell form of the CMD, RUN, and ENTRYPOINT instructions. Example:
    SHELL ["/bin/bash", "-c"]
```

---

## Difference Between `RUN`, `CMD` and `ENTRYPOIT`
The RUN, CMD, and ENTRYPOINT instructions in a Dockerfile have distinct purposes and are used at different stages of building and running a container. Here's an explanation of each instruction and their differences:

1. RUN:
    - The `RUN` instruction is used to execute commands during the image build process. It allows you to install dependencies, perform configurations, and run any command that modifies the image's filesystem.
    - The commands specified with `RUN` are executed once at build time, and their results are committed to a new layer in the image. These changes become part of the image's filesystem.
    - Multiple `RUN` instructions can be included in a Dockerfile, and each one creates a new layer in the image.
    - Example: `RUN apt-get update && apt-get install -y package1 package2`

2. CMD:
    - The `CMD` instruction sets the default command or parameters that are executed when a container is launched.
    - It is often used to specify the main command of the application running inside the container. The `CMD` instruction can be overridden by providing arguments when starting the container when running `docker run`. (means that when user build an image using docker file, when it comes to run a container from the image users can overwrite the `CMD` command if they give arguments to `docker run`)
    - Only the last `CMD` instruction in the Dockerfile takes effect. If multiple `CMD` instructions are present, the last one overwrites the previous ones.
    - Example: `CMD ["npm", "start"]` 

3. ENTRYPOINT:
    - The `ENTRYPOINT` instruction sets the primary command for the container and allows the container to be invoked like an executable.
    - It provides a way to define the entry point of the application and any default arguments that should be passed.
    - Unlike CMD, the `ENTRYPOINT` command and its arguments are not overridden when providing additional arguments to the `docker run` command.
    - `ENTRYPOINT` is commonly used when you want to enforce a specific command or executable as the main process inside the container, without allowing it to be easily overridden.
    - It is useful for defining a container that acts like an executable, where the primary command is fixed, and additional arguments are expected.
    - Example: `ENTRYPOINT ["java", "-jar", "app.jar"]` (Here the primary command for the container is set to run a Java application using the specified JAR file. Any arguments provided when starting the container will be appended to this command.)

In summary, the key differences between RUN, CMD, and ENTRYPOINT are:
- `RUN` executes commands during the image build process to modify the image's filesystem.
- `CMD` specifies the default command to run when a container is launched, and it can be overridden.
- `ENTRYPOINT` sets the primary command for the container, and its arguments are not overridden.

While RUN and CMD are often used together in a Dockerfile to build the image and define its default behavior, ENTRYPOINT provides a more rigid way to define the primary command of the container. In some cases, combining ENTRYPOINT and CMD can be useful. You can use ENTRYPOINT to define the main executable, and CMD to provide default arguments that can be overridden. This approach allows you to enforce a primary command while still allowing flexibility for users to modify its behavior when necessary.

### Dockerfile example:
```Dockerfile
# Use a base image
FROM ubuntu:latest

# Set metadata labels
LABEL maintainer="John Doe <john@example.com>"
LABEL version="1.0"

# Set build arguments
ARG ENVIRONMENT=production

# Set environment variables
ENV APP_HOME=/app
ENV PATH="${APP_HOME}/bin:${PATH}"

# Set the working directory
WORKDIR ${APP_HOME}

# Copy files from the build context to the image
COPY . ${APP_HOME}

# Install dependencies and perform additional setup
RUN apt-get update \
    && apt-get install -y build-essential \
    && make install \
    && chmod +x ${APP_HOME}/script.sh

# Expose a port
EXPOSE 8080

# Set the default command and arguments
CMD ["./start.sh"]

# Set the entrypoint
ENTRYPOINT ["python3", "-u"]

# Specify a volume
VOLUME /data

# Switch to a non-root user
USER myuser

# Run a command during the build process
RUN echo "Build completed."

# Define a shell to use for executing commands
SHELL ["/bin/bash", "-c"]
```

---

## How Build Dockerfile
To build a Dockerfile and create a Docker image, you can use the docker build command. Here's the general syntax:
```bash
docker build [OPTIONS] PATH_TO_DOCKERFILE
```

Here's a step-by-step guide to building a Dockerfile:
1. Open a terminal or command prompt.
2. Navigate to the directory containing the Dockerfile or provide the absolute path to the Dockerfile.
3. Run the `docker build` command, specifying the build options and the path to the Dockerfile:
```bash
    docker build -t IMAGE_NAME:TAG .
```
- Above :
    - `-t` or `--tag` allows you to specify the name and optional tag for the image.
    - `IMAGE_NAME` is the desired name for the image.
    - `TAG` is an optional tag to differentiate different versions of the image.
    - `.` refers to the current directory as the build context. The build context includes the Dockerfile and any files or directories referenced in the Dockerfile's instructions.

4. Docker will start building the image based on the instructions in the Dockerfile. Each instruction will be executed sequentially, creating layers in the image.
5. During the build process, Docker may download any necessary base images or dependencies defined in the Dockerfile.
6. Once the build is complete, Docker will output the image ID and other relevant information.
7. After building the Dockerfile, you can run containers from the newly created image using the docker run command.

---

## Understanding `VOLUME` Insturction
The `VOLUME` instruction in a Dockerfile is used to create a mount point or declare a volume in a Docker image. It does not create the volume or bind mount itself, but rather provides information to Docker about where the volume should be mounted when running a container based on that image.

When you build an image from the Dockerfile, the `VOLUME` instruction is recorded as metadata in the image. It informs Docker that the specified paths should be mount points for volumes when running a container based on that image. At runtime, when you run a container from the image, Docker creates the volume or bind mount at the specified paths if they don't exist already. If the paths refer to an existing directory or file on the host, Docker treats them as bind mounts and maps them to the corresponding paths inside the container. If the paths don't exist on the host, Docker creates a new volume specifically for that container and mounts it at the specified paths. This volume is managed by Docker and can be shared across multiple containers if desired.

In the Dockerfile, you specify the VOLUME instruction followed by a path or multiple paths where you want to declare volumes. 
```Dockerfile
VOLUME /data
VOLUME /config
VOLUME /logs

# same as
VOLUME /data /config /data
```
If you provide multiple paths to the VOLUME instruction in a Dockerfile, Docker treats each path as a separate mount point or volume declaration. When you run a container based on that image, Docker will create individual volumes or bind mounts at each specified path. When you run a container based on this image, Docker will create separate volumes or bind mounts at each of these paths. If the paths do not exist on the host, Docker will create new volumes for each path. If the paths refer to existing directories or files on the host, Docker will treat them as bind mounts and map them to the corresponding paths inside the container.

For example, if you run the container with the following command:
```sh
    > docker run -v /host/data:/data -v /host/config:/config -v /host/logs:/logs <image_name>
```
Docker will create volumes or bind mounts at /data, /config, and /logs in the container, mapping them to the corresponding paths /host/data, /host/config, and /host/logs on the host.


# What is Docker Hub
Docker Hub is a cloud-based registry service provided by Docker that allows developers, organizations, and the Docker community to store, share, and distribute Docker images. It serves as a centralized platform where users can access a vast collection of pre-built Docker images for various software applications, services, and tools.

Here are some key features and functionalities of Docker Hub:

1. Image Hosting: Docker Hub acts as a repository for Docker images, allowing users to upload and store their own images. It provides a secure and reliable infrastructure to host the images.

2. Image Distribution: Docker Hub enables easy distribution of Docker images across different environments, making it simple to share images with colleagues, teammates, or the broader Docker community.

3. Public and Private Repositories: Docker Hub supports both public and private repositories. Public repositories are accessible to anyone and can be searched and downloaded by other users. Private repositories, on the other hand, provide more control and privacy, allowing image sharing within specific teams or organizations.

4. Versioning and Tagging: Docker Hub supports versioning and tagging of images. Different versions or variations of an image can be tagged and organized within the repository, making it easy to manage and track changes.

5. Automated Builds: Docker Hub offers a feature called Automated Builds, which allows you to automatically build Docker images from source code repositories, such as GitHub or Bitbucket. With this feature, whenever changes are pushed to the repository, Docker Hub triggers a new image build, simplifying the image creation and update process.

6. Collaboration and Sharing: Docker Hub fosters collaboration and knowledge-sharing among Docker users. It provides a platform for developers to share their images, contribute to open-source projects, and learn from others' work.

7. Official Images: Docker Hub hosts a collection of Official Images, which are curated and maintained by the Docker team or trusted partners. Official Images are popular and widely-used images for various software, databases, programming languages, and tools. They are thoroughly tested, ensuring a reliable and secure starting point for building containers.

---

## Additional Repositories That Users Can Store, Share, and Distribute Docker Images:
In addition to Docker Hub, there are several other repositories and registries where users can store, share, and distribute Docker images. These repositories provide alternative options for hosting and accessing Docker images. Some popular ones include:

1. Amazon Elastic Container Registry (ECR): Amazon ECR is a fully managed container registry service provided by Amazon Web Services (AWS). It integrates with other AWS services and offers secure and scalable storage for Docker images. ECR is commonly used by organizations deploying Docker containers on AWS.

2. Google Container Registry (GCR): Google Container Registry is a private Docker image storage service provided by Google Cloud Platform (GCP). It offers seamless integration with other GCP services and supports secure image hosting and distribution.

3. Azure Container Registry (ACR): Azure Container Registry is a private Docker registry service provided by Microsoft Azure. It enables developers to store and manage Docker images securely, integrating well with other Azure services for containerized deployments.

4. Quay.io: Quay.io is a public and private container registry owned by Red Hat. It provides a platform for storing, building, and distributing container images. Quay.io offers additional features like vulnerability scanning, access control, and automation capabilities.

5. Harbor: Harbor is an open-source container registry that can be self-hosted. It offers a secure and scalable platform for storing and distributing Docker images. Harbor supports role-based access control, vulnerability scanning, and replication features.

6. GitLab Container Registry: GitLab Container Registry is integrated within the GitLab platform and provides a built-in registry for storing Docker images. It simplifies the development workflow by offering version control, CI/CD pipelines, and image hosting in one platform.

---

## Searching Docker Images Using CLI `docker search`
The `docker search` command allows you to explore available Docker images (Specifically for in Docker Hub) and find the ones that match your requirements. You can search for specific images by name, application, or any relevant keywords. Additionally, you can use filters or specific search options to refine your search results if needed.
```sh
    > docker search IMAGE_NAME
```
- Docker will display a list of matching Docker images available in Docker Hub or other registries. The output will include information such as the image name, description, stars, and official status.

To filter and search for a specific Docker image, you can use the `docker search` command along with filters. Here's how to do it:
```sh
    > docker search --filter=NAME_FILTER IMAGE_NAME
```
- Replace NAME_FILTER with the filter option based on your search criteria. Some commonly used filters are `is-official`, `is-automated`, `stars`, `pulls`, `updated`, etc. You can use multiple filters separated by commas.

Example :
```sh
    > docker search --filter=is-official=true nginx
```

---

## Log in to a Registry
```sh
    > docker login [OPTIONS] [SERVER]
```

Log  in  to a Docker Registry located on the specified SERVER.  You can specify a URL or a hostname for the SERVER value. If you do not specify a SERVER, the command uses Docker's public registry located at  https://registry-1.docker.io/  by  default.   To  get  a  user‐name/password for Docker's public registry, create an account on Docker Hub.

As said Docker will prompt you to enter your credentials. Provide your username and password for the remote registry when prompted. If the registry supports authentication using an access token, you may need to provide a token instead of a password. After successfully logging in, Docker will create or update a configuration file on your machine that stores your credentials securely. You are now logged in to the remote registry and can perform actions like pulling, pushing, or searching for images within that registry.


---

## How to Pull Docker Images From Public, Private, and Other Repositories Using CLI

#### **1. Pulling an image from Docker Hub (Public Repository):**
To pull an image from a public repository on Docker Hub, you can use the `docker pull` command followed by the image name and optionally the tag. Note that, When pulling an image from Docker Hub, you don't need to specify the repository server or the username of the repository. Docker Hub is the default registry, and the image name, along with the optional tag, is sufficient to identify and pull the image.
```bash
    > docker pull <image_name>:<tag>

    # Example:
    > docker pull nginx:latest
```
To specifically pull image from someone else repository:
```bash
    > docker pull <DockerHub_Username>/<Repository_Name>:<image_name>:<tag>
    # or more common
    > docker pull <Repository_Name>/<image_name>:<tag>
```

#### **2. Pulling an image from Docker Hub (Private Repository):**
To pull an image from a private repository on Docker Hub, you need to log in to Docker Hub first using the `docker login` command. After successful login, you can use the `docker pull` command as usual. Here's an example:
```bash
    > docker login
    > docker pull myusername/my-private-image:latest
```

#### **3. Pulling an image from another repository (e.g., GitHub Container Registry):**
To pull an image from a repository other than Docker Hub, the process may vary depending on the registry provider. Here's an example using GitHub Container Registry:
```bash
    > docker login docker.pkg.github.com
    > docker pull docker.pkg.github.com/username/repo/image:tag
```
Replace username with your GitHub username, repo with the name of your repository, image with the name of the image, and tag with the desired version or tag.

---

## How to Push Docker Images To Public, Private, and Other Repositories Using CLI
Pushing an image to a public, private and to a repository other than Docker Hub have similar steps. But in repositories other than docker hub pecific commands and requirements may vary depending on the registry provider. Generally to push an image to a repository (public, private, ...) you need to follow :
- First, ensure that you have logged in to Docker Hub (or any other repository provider) using the `docker login` command. It will ask for your Docker Hub (or other repository provider) account credentials.
- Tag your image with the appropriate repository name using the `docker tag` command. For example:
```bash
    > docker tag local_image:tag dockerhub_username/repository:<desired_tag>
```
- Push the tagged image to Docker Hub (or other repositories) using `docker push`:
```bash
    > docker push dockerhub_username/repository:<desired_tag>
```

Example :
Let's say you have two local image with names and tags as follow : "left:21: and "right:21" and you wnat to push it to your repository which is called "ripo" and your docker user name is "doky", to push both local images to your repository you should:
- First login with `docker login`
- Tag you local images with the repository name and a desired tag, and then push them as you like :
```bash
    # tag the first image to ripo with a tag name of left-21
    > docker tag left:21 doky/ripo:left-21
    # tag the second image to ripo with a tag name of right-21
    > docker tag right:21 doky/ripo:right-21

    # At last push them
    > docker push doky/ripo:left-21
    > docker push doky/ripo:right-21
```

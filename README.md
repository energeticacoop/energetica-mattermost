
# Mattermost Installation for Energética Coop

This repository contains the Docker-based installation of **Mattermost** tailored for **Energética Coop**.

### Install & Usage

For detailed instructions on how to install and use Mattermost in this setup, please refer to the [Mattermost Docker deployment guide](https://docs.mattermost.com/install/docker.html). 

This repository offers a ready-to-use **Docker Compose** setup to deploy Mattermost. To get started, follow the steps below:

1. Clone this repository to your local machine.
2. Copy `.env.example` to `.env` and modify the environment variables according to your configuration.
3. Run the following command to start Mattermost with Docker Compose:

   ```bash
   docker-compose up -d
   ```

Access Mattermost through your browser at http://localhost:8065 (or the host URL you've set).

### TODO: Update the Mattermost Deployment

This section outlines important future improvements for this Mattermost Docker installation to follow modern best practices.

- **Dockerfile Creation**:
  A dedicated Dockerfile should be created to define a custom image for Mattermost that is tailored to Energética Coop's needs. The current setup uses Docker Compose with pre-built images, but creating a custom Dockerfile will give us better control over the environment, dependencies, and optimizations for our use case.

- **Image Building & Pushing**:
  After creating the Dockerfile, we will build the custom Mattermost Docker image and push it to a Docker registry (such as Docker Hub, AWS ECR, or GitHub Container Registry). This will streamline deployment, as it allows us to pull the latest image version from a trusted registry instead of rebuilding the image each time.

  Example steps:
  - Build the image:
  
  ```bash
  docker build -t <your-registry>/mattermost:latest .
  ```
  - Push the image to a registry:
  
  ```bash
  docker push <your-registry>/mattermost:latest
  ```

- **Automated CI/CD**:
  Consider setting up continuous integration (CI) pipelines using platforms like GitHub Actions, GitLab CI, or CircleCI to automate the process of building, testing, and pushing the Mattermost image to a registry whenever changes are made to the code.



# Argocd Deployment Repository
[Full Tutorial](https://medium.com/@sameeradissanayaka/complete-ci-cd-pipeline-gitops-project-with-docker-kubernetes-githubactions-and-argocd-step-by-step-cebf766c9d42)

This repository serves as a central hub for managing deployment configurations using ArgoCD. The primary objective is to facilitate efficient monitoring and deployment of applications defined within the `deployment.yml` file.

## Deployment Strategy

The deployment process hinges on the Docker image hosted on `devopswithsam/argodemo:latest`. This image is dynamically updated whenever changes occur within the associated GitHub repository at [iam-sameera/argocd-docker](https://github.com/iam-sameera/argocd-docker). This synchronization is orchestrated through a robust GitHub Actions workflow integrated into the repository.

### Workflow Overview

1. **GitHub Actions Build**: Upon changes in the source repository, GitHub Actions orchestrates the build process.
2. **Image Tagging**: The resulting Docker image is tagged with the latest build number, ensuring versioning consistency.
3. **Registry Update**: The tagged image is then pushed to the Docker Hub registry, making it available for deployment.
4. **Arbitrary Deployment**: ArgoCD monitors the repository for changes, allowing seamless deployment based on the updated image tag.

By leveraging this setup, we ensure a streamlined and automated deployment pipeline, promoting consistency and reliability in our application deployments.

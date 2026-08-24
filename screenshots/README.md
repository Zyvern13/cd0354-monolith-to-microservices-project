# Screenshots
To help review your infrastructure, please include the following screenshots in this directory::

## Deployment Pipeline
* DockerHub showing containers that you have pushed
* GitHub repository’s settings showing your Travis webhook (can be found in Settings - Webhook)
* Travis CI showing a successful build and deploy job


### DockerHub
- **docker-images.png** - DockerHub showing all pushed container images (udagram-api-feed, udagram-api-user, udagram-frontend, reverseproxy)

### CI/CD Pipeline
Travis CI no longer offers a free tier for new accounts — it now requires a paid plan to trigger any builds. Multiple attempts were made to use Travis CI (including creating a new GitHub account as suggested in the course material), but all were met with a mandatory paid plan selection screen with no free option available.

As an alternative, **GitHub Actions** was used as an equivalent CI/CD pipeline to build and push Docker images to DockerHub. The pipeline performs the same functions as the intended Travis CI setup:
- Builds all Docker images (feed, user, frontend, reverseproxy)
- Tags and pushes images to DockerHub

The `.travis.yml` file is included in the repository to demonstrate the intended Travis CI configuration.

- **Github-workflow.png** - GitHub Actions successful build and push to DockerHub

## Kubernetes
* To verify Kubernetes pods are deployed properly
```bash
kubectl get pods
```
* To verify Kubernetes services are properly set up
```bash
kubectl describe services
```
* To verify that you have horizontal scaling set against CPU usage
```bash
kubectl describe hpa
```
* To verify that you have set up logging with a backend application
```bash
kubectl logs {pod_name}
```

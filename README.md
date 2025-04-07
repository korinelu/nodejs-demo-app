Steps I Followed:
Started with a Node.js App
I created a simple Node.js app with a basic app.js file and a package.json using npm init. I also added a test script inside package.json.

Created a Dockerfile
I wrote a Dockerfile that installs dependencies, copies the app files, and runs the app inside a container.

Pushed Everything to GitHub
I created a new GitHub repo called nodejs-demo-app and pushed all the project files including app.js, package.json, Dockerfile, etc.

Created a DockerHub Repository
I created a public repo on DockerHub with the same name (nodejs-demo-app) so that my GitHub Actions workflow could push Docker images to it.

Added GitHub Secrets for DockerHub Login
In my GitHub repo settings, I added:

DOCKER_USERNAME: my DockerHub username

DOCKER_PASSWORD: my DockerHub password or access token

Set Up the CI/CD Workflow
Inside my GitHub repo, I created a workflow file at .github/workflows/main.yml. This workflow:

Runs on every push to the master branch

Installs dependencies

Runs tests

Builds a Docker image

Logs in to DockerHub

Pushes the image to DockerHub

Added File Filters
I added path filters to the workflow so it only runs when important files (like .js, Dockerfile, or package.json) are changed. This prevents the workflow from running for small changes like README.md edits.


![Workflow Success](assets/workflow-success.png)

https://hub.docker.com/r/korinelu/nodejs-demo-app

# CI/CD Pipeline

### CI/CD Pipeline Environment:

Our CI/CD pipeline operates on a cloud-based infrastructure utilizing GitHub Actions for automation. With Linux as the operating system, it ensures compatibility with our Flutter web application stack. Leveraging Docker containers ensures consistent builds across environments. GitHub Actions dynamically allocates resources, providing scalability, while encryption and access controls ensure security. 

#### CI/CD Pipeline Tools:

We've set up a GitHub Actions workflow named `build.yml` in the `.github/workflows` directory of our repository.

The tools chosen for our CI/CD pipeline, namely Git and GitHub Actions, were selected for their robust features, tight integration, and community support. Git serves as our version control system, offering powerful branching and merging capabilities along with distributed architecture for resilience. Despite its steep learning curve and complexities in managing branching strategies, Git's widespread adoption and open-source nature make it an industry standard.

GitHub Actions complements Git by enabling workflow automation directly within our GitHub repository. Its extensibility through pre-built actions and integrations, along with features like matrix builds and secrets management, enhances our CI/CD processes. While GitHub Actions' YAML syntax may pose challenges in writing and maintaining workflows, its tight integration with GitHub, scalability, and generous free tier make it an attractive choice for automating our development and deployment workflows.

In summary, the combination of Git and GitHub Actions provides a comprehensive solution for version control and CI/CD automation. Despite their respective limitations, their strengths in flexibility, scalability, and community support make them well-suited for streamlining our development processes and ensuring the quality and reliability of our Flutter web application.

#### Workflow Steps:

1. **Clone Repository**: The workflow starts by cloning the repository containing the source code of our Flutter web application.

2. **Dependency Verification**:
   - We check if the runner environment has the necessary Flutter dependencies installed.
   - Additionally, we ensure that the required Flutter application dependencies are present. If not, we provide instructions on how to install them.

3. **Test Execution**:
   - The workflow runs any available Flutter tests present in the repository.
   - It reports the test results, providing developers with immediate feedback.

4. **Build Flutter Application**:
   - Using appropriate commands, the workflow builds the Flutter web application.
   - It ensures that the build process completes successfully without errors.

#### Environment Variables:

We've set up necessary environment variables such as the Flutter SDK path in our workflow to facilitate the build process.

## Deployment Stage

### Workflow Overview

For the deployment stage, we aim to automatically deploy our Flutter web application to GitHub Pages using GitHub Actions.

### Selection Considerations

#### GitHub Pages Deployment:

GitHub Pages offers a straightforward and convenient solution for hosting static websites, making it an excellent choice for deploying our Flutter web application. Some key considerations for selecting GitHub Pages include:

- **Ease of Setup**: GitHub Pages integrates seamlessly with GitHub repositories, simplifying the deployment process. By configuring the repository settings and specifying the `gh-pages` branch or `docs` folder, we can publish our application with minimal setup.

- **Free Hosting**: GitHub Pages provides free hosting for static websites, making it a cost-effective option for projects with budget constraints. This allows us to showcase our application without incurring additional hosting expenses.

- **Custom Domain Support**: GitHub Pages supports custom domains, enabling us to use our own domain name for the deployed application. This enhances brand identity and provides a professional appearance for our web application.

### Workflow Setup: GitHub Pages Deployment

#### Workflow Configuration:

We've set up a deployment workflow named `deploy.yml` specifically tailored for deploying our Flutter web application to GitHub Pages.

#### Deployment Steps:

1. **Build Artifact Creation**: Before deployment, we ensure that the Flutter web application is built successfully. This step involves compiling source code, resolving dependencies, and generating the necessary build artifacts.

2. **Deployment Setup**:
   - We configure the deployment workflow to deploy the built application to GitHub Pages.
   - This involves specifying the target branch (`gh-pages`) or folder (`docs`) where the deployment artifacts will be published.

3. **Deployment Execution**:
   - The workflow automatically triggers deployment upon successful completion of the build stage.
   - It copies the built application files to the designated branch or folder, making the application accessible via the GitHub Pages URL.

4. **Domain Configuration**:
   - We configured the GitHub Pages settings to use a custom domain for our deployed application. This involves updating DNS records and verifying domain ownership.

### Challenges and Solutions:

Setting up GitHub Pages deployment encountered few challenges, primarily related to configuring custom domains and ensuring smooth workflow execution. To address these challenges, we:

- **Secured GitHub Token**: To enable the deployment workflow to access the repository and publish changes to GitHub Pages, we securely managed the GitHub token using GitHub Secrets. This ensured that sensitive credentials are protected and not exposed in the workflow file.

- **Domain Configuration**: Configuring custom domains required updating DNS records and configuring GitHub Pages settings. We carefully followed the documentation provided by GitHub and domain registrar to ensure proper configuration and seamless domain mapping.

# Comprehensive Report on CI/CD Pipeline for Flutter Web Application Development

## Introduction: Overview of CI/CD Pipelines

Continuous Integration (CI) and Continuous Deployment (CD) pipelines are essential components of modern software development workflows. CI checks code regularly to ensure it works well with other pieces and CD automatically sends finished code to where it needs to be. These pipelines automate the process of integrating code changes, testing them, and deploying them to production environments. CI/CD pipelines ensure faster and more reliable delivery of software, enabling teams to iterate quickly and respond to user feedback efficiently.

## DevContainer Environment: Docker Configuration for Flutter Development

A DevContainer is like a ready-to-use workspace for developers. It has all the tools and settings you need, so you can start coding without setting things up yourself. For my Flutter development environment, I selected a Docker image explicitly designed for Flutter. This image includes the Flutter SDK, Dart and for our Flutter development environment, I selected a Docker image explicitly designed for Flutter. I specifically used Ubuntu for the DevContainer.json with the Jammmy based image.

Our DevContainer seamlessly integrates with Visual Studio Code (VS Code), providing a unified development experience. Some extensions I used were the DevContainers extension that uses a Docker container as a full-featured development environment. I also used Github Repositories and GitHub Codespaces so that I can work wiht my Github codespace from VS code.

For you to run this container on your own the usgae would be the steps that followed:

Clone the Flutter project repository from GitHub.

Open the project folder in Visual Studio Code.

VS Code detects the DevContainer configuration and prompts to reopen the project in a DevContainer. Accept the prompt to start the development environment within the configured Docker container.

Use the integrated terminal in VS Code to execute Flutter commands, such as running the application or running tests. Specifially use: flutter run -d web-server to run your app on the web (make sure you are in the app before you do this)

When Setting up my DevContainer environment I ran into the issue of adding my own container and setting up in my Github Repository. To set up my container I had to apply the DevContainer extension to use Ubuntu and use the post create command: sudo chown -R vscode /flutter/.pub-cache/". After this I learned to commit my chages through command line to github so that I can process my finished container on Github.

Utilizing a DevContainer for our Flutter project offers several advantages. It ensures a consistent and reproducible environment, facilitates collaboration, and streamlines the onboarding process. The insights gained from configuring and using the DevContainer contribute to an efficient and scalable development process.


## Source Code Version Control Tools: Git Version Control

Version control keeps track of all the changes made to a project over time. If something goes wrong, you can go back to a previous version to fix it. It also allows multiple people work on the same project without overwriting each other's work. This helps teams collaborate and keeps code organized.

Git is used as the version control system for managing the source code of the Flutter web application. Git allows for efficient collaboration among team members, tracks changes to the codebase, and enables easy rollback to previous versions if needed. The source code is hosted on a remote repository (e.g., GitHub, GitLab) to facilitate code sharing and version control.

Common Commands and Usage
git clone <repository-url>: Clone the repository to your local machine.
git add .: Stage all changes for commit.
git commit -m "Your commit message here": Commit staged changes with a descriptive message.
git pull origin main: Pull the latest changes from the remote repository.
git push origin main: Push local commits to the remote repository.
Pull Requests: Facilitate code reviews and change proposals.

If a team used this as their version control then developers can clone the repository, make changes, and push them back to the remote repository. Regular pulls ensure local versions are up-to-date with the remote repository.

The adoption of Git as the version control system has greatly enhanced the development workflow. It has provided me with a robust framework for managing code changes and ensuring the integrity of the project. 

## CI/CD Pipeline Environment: Setup Description

The CI/CD pipeline is set up using a combination of local and cloud-based environments. We utilize cloud services such as GitHub Actions or GitLab CI/CD to automate the build, test, and deployment processes. Additionally, local development environments are used for testing changes before merging them into the main codebase.

Each of these tools are used for devloping Flutter web applications

Docker is a platform for developing and running applications in containers. It provides a platform to allow the deployment of applications inside containers.

GitHub is a platform that provides hosting for software development and version control using Git. Git is a version control system that allows multiple developers to work on a project.

Flutter is a platform that allows you to build applications for various platforms, including mobile, web, and desktop, using a single codebase. For this project we are using a web application.

We have set up a Github repository containing our flutter project then we designed our dev container by setting up an ubuntu container in our codespace.

In this codespace we set up our flutter application in our container.

To run commands after the container is created. I edited the "postCreateCommand": "sudo chown -R vscode /flutter/.pub-cache/" to allow us to use our flutter commands and run our application.

## CI/CD Tools: GitHub Actions

GitHub Actions is selected as the CI/CD tool for this project due to its seamless integration with GitHub repositories and its powerful workflow customization capabilities. GitHub Actions are configured to trigger on specific events, such as code pushes or pull requests, and execute predefined workflows for building, testing, and deploying the Flutter web application.

Build phase: Cloning the repository, verifying dependencies, running tests, and compiling the code.
Deployment phase: Deploying to GitHub Pages for hosting.

## Build Phase
The build phase automates compiling the Flutter web application code, verifying dependencies, and executing tests to ensure code integrity and functionality.

### Workflow Overview
The build.yml workflow file is in the `.github/workflows` directory. Key steps include:
- Cloning the repository.
- Verifying dependencies.
- Running unit tests to validate the functionality of individual components.
- (Optional) Integration tests to validate component interactions.
- Compiling the Flutter web application code to generate build artifacts.

## Deployment Environment: GitHub Pages

GitHub Pages is chosen as the deployment environment for the Flutter web application. GitHub Pages provides a simple and straightforward way to host static websites directly from GitHub repositories. It offers free hosting with a custom domain support, making it an ideal choice for hosting Flutter web applications. Setup configurations include configuring GitHub Pages to serve the Flutter web application and setting up custom domains for production deployment.

We are able to deploy due to having our ac

 - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:  
          github_token: ${{ secrets.GH_PAGES_TOKEN }}
          publish_dir: ./app/build/web
   
A secret token is a secure, private value used to authenticate and authorize actions in a CI/CD pipeline. It is typically stored in a way that only authorized jobs can access it. In GitHub Actions, secrets are stored in the repository or organization settings and can be accessed securely within the workflow.

In GitHub Actions, you don't want to share your password with everyone. So, GitHub lets you keep it hidden in a "secret" section. This way, when your workflow needs to deploy, it can use the secret token without exposing it to anyone who shouldn't see it.

This token is important because it gives your workflow permission to upload your project to GitHub Pages. Without it, the workflow doesn't have the authority to deploy, and you'd get an error.

Using secrets keeps your pipeline safe and ensures that only authorized people can make changes to your project. It’s like a security guard for your deployment process.

## Flutter Web Application: Development Overview

Docker: Install Docker
Git: Install Git
Flutter: Install Flutter
Each of these tools are used for devloping Flutter web applications

Docker is a platform for developing and running applications in containers. It provides a platform to allow the deployment of applications inside containers.

GitHub is a platform that provides hosting for software development and version control using Git. Git is a version control system that allows multiple developers to work on a project.

Flutter is a platform that allows you to build applications for various platforms, including mobile, web, and desktop, using a single codebase. For this project we are using a web application.

We have set up a Github repository containing our flutter project then we designed our dev container by setting up an ubuntu container in our codespace.

In this codespace we set up our flutter application in our container.

To run commands after the container is created. I edited the "postCreateCommand": "sudo chown -R vscode /flutter/.pub-cache/" to allow us to use our flutter commands and run our application.

Right now our application contains builds for android, ios, macos, web, windows and linux for now we will focus on web applications

To run our contsinerized development enviroment we go into our application using 'cd app' Then we run our 'flutter run -d web-server' to run our application on our web server. A link would appear in our bash terminal displaying our application.

At this point in our project we have a clicker web application which is the base Flutter app we have containerized.

Running the original Flutter Web app in my codespace:

<img width="1440" alt="Screenshot_2024-04-20_at_7 09 55_PM" src="https://github.com/amroabua/CSC325/assets/136997766/370531f4-fc17-4284-87a1-d8f1e76e5659">

Demo:
<img width="1440" alt="Screenshot 2024-04-20 at 7 09 34 PM" src="https://github.com/amroabua/CSC325/assets/136997766/f1d27e0b-f753-4a46-86e2-4a849b1f564b">



## Challenges and Reflections

Throughout the project, several challenges were encountered, mainly the one I recieved at near the end of the project in which whenever I would deploy my flutter web application and head to my website at https://amroabua.github.io/CSC325/ I would recieve the error message shown:

<img width="1440" alt="Screenshot_2024-04-20_at_7 50 12_PM" src="https://github.com/amroabua/CSC325/assets/136997766/192036e1-7e69-4cc9-9158-685f474aff47">

To fix this I worked with Mr. Munday only to find my mainline.yml file had the issue of having two jobs. And the reason this caused the issue was due to the fact that in most CI/CD systems, jobs are isolated from each other. This means they don't share files, data, or environment variables. If the build job creates a build then the deploy job won't have access to those variables unless you explicitly set up a way to share them. Which is the problem I ran into, so to fix this I updated my mainline.yml to run with one job to build and deploy my app.

<img width="1440" alt="Screenshot 2024-04-23 at 10 25 10 PM" src="https://github.com/amroabua/CSC325/assets/136997766/ca368006-29a8-4b54-ba9a-94fd9e3aaba4">


## Conclusion

In conclusion, the implementation of a CI/CD pipeline for Flutter web application development has significantly improved the efficiency and reliability of the software delivery process. Leveraging Docker containers, Git version control, GitHub Actions, Firebase Hosting, and other tools has enabled seamless automation of build, test, and deployment processes. Reflecting on the project, valuable lessons have been learned, and there is room for continuous improvement in both the pipeline and the application itself.

Reflecting on this project, there's room for continuous improvement and innovation, with a commitment to delivering high-quality software products.

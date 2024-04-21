# Comprehensive Report on CI/CD Pipeline for Flutter Web Application Development

## Introduction: Overview of CI/CD Pipelines

Continuous Integration (CI) and Continuous Deployment (CD) pipelines are essential components of modern software development workflows. These pipelines automate the process of integrating code changes, testing them, and deploying them to production environments. CI/CD pipelines ensure faster and more reliable delivery of software, enabling teams to iterate quickly and respond to user feedback efficiently.

## DevContainer Environment: Docker Configuration for Flutter Development

For Flutter development, we have configured a Docker container environment to ensure consistency across different development machines and to streamline the setup process for new team members. The Docker container includes all necessary dependencies and tools required for Flutter development, such as the Flutter SDK, Android SDK, and any additional libraries or packages.

## Source Code Version Control Tools: Git Version Control

Git is used as the version control system for managing the source code of the Flutter web application. Git allows for efficient collaboration among team members, tracks changes to the codebase, and enables easy rollback to previous versions if needed. The source code is hosted on a remote repository (e.g., GitHub, GitLab) to facilitate code sharing and version control.

Common Commands and Usage
git clone <repository-url>: Clone the repository to your local machine.
git add .: Stage all changes for commit.
git commit -m "Your commit message here": Commit staged changes with a descriptive message.
git pull origin main: Pull the latest changes from the remote repository.
git push origin main: Push local commits to the remote repository.

#### Git facilitates collaboration through features such as:

Pull Requests: Propose and review changes before merging them into the main branch.
Code Reviews: Discuss and provide feedback on code changes within pull requests.
Conflict Resolution: Resolve conflicts that arise when merging branches with overlapping changes.

## CI/CD Pipeline Environment: Setup Description

The CI/CD pipeline is set up using a combination of local and cloud-based environments. We utilize cloud services such as GitHub Actions or GitLab CI/CD to automate the build, test, and deployment processes. Additionally, local development environments are used for testing changes before merging them into the main codebase.

## CI/CD Tools: GitHub Actions

GitHub Actions is selected as the CI/CD tool for this project due to its seamless integration with GitHub repositories and its powerful workflow customization capabilities. GitHub Actions are configured to trigger on specific events, such as code pushes or pull requests, and execute predefined workflows for building, testing, and deploying the Flutter web application.

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

![Running the original Flutter Web app in my codespace]([https://example.com/image.png](https://media.discordapp.net/attachments/797178691163652117/1231381394282905711/Screenshot_2024-04-20_at_7.09.55_PM.png?ex=6636c04a&is=66244b4a&hm=aa2b002106a59382209ad1cd3c882e002c418a1b664697188c895c422bb8711b&=&format=webp&quality=lossless&width=1100&height=688))

![Flutter Demo]([https://example.com/image.png](https://media.discordapp.net/attachments/797178691163652117/1231381348246093864/Screenshot_2024-04-20_at_7.09.34_PM.png?ex=6636c03f&is=66244b3f&hm=ac92acce9d38470bcebc52e4e0cd70204264c98da8faccc2cf0e7b471dea55c4&=&format=webp&quality=lossless&width=1620&height=1012))


## Challenges and Reflections

Throughout the project, several challenges were encountered, including [mention specific challenges]. However, these challenges were overcome through collaboration and problem-solving within the team. Lessons learned from this project include [mention lessons learned]. Moving forward, potential improvements for the pipeline or application include [mention potential improvements].

![Error Message I Got]([<img width="1440" alt="Screenshot 2024-04-19 at 6 16 29 PM" src="https://github.com/amroabua/CSC325/assets/136997766/afc288c8-7129-4450-999b-688bd25177b4">](https://media.discordapp.net/attachments/797178691163652117/1231381394282905711/Screenshot_2024-04-20_at_7.09.55_PM.png?ex=6636c04a&is=66244b4a&hm=aa2b002106a59382209ad1cd3c882e002c418a1b664697188c895c422bb8711b&=&format=webp&quality=lossless&width=1620&height=1012))

## Conclusion


In conclusion, the implementation of a CI/CD pipeline for Flutter web application development has significantly improved the efficiency and reliability of the software delivery process. Leveraging Docker containers, Git version control, GitHub Actions, Firebase Hosting, and other tools has enabled seamless automation of build, test, and deployment processes. Reflecting on the project, valuable lessons have been learned, and there is room for continuous improvement in both the pipeline and the application itself.

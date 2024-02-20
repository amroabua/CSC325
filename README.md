# CSC325
Containers are an enviroment that develpors use to run code. This environment is used to develop an application to deploy. With DevContainers, we can have a controlled base that can set up production environments for our Flutter web application.
I have set up a containerized development environment that supports developing Flutter web applications, I did so by creating a container image that contains all the necessary tools required for developing Flutter web applications. 

To be able to run this enviroment ensure that you have the following installed on your machine:

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Git: [Install Git](https://docs.github.com/en/desktop/installing-and-authenticating-to-github-desktop/installing-github-desktop)
- Flutter: [Install Flutter](https://flutter.dev/docs/get-started/install)

Each of these tools are used for devloping Flutter web applications

Docker is a platform for developing and running applications in containers. It provides a platform to allow the deployment of applications inside containers.

GitHub is a platform that provides hosting for software development and version control using Git. Git is a version control system that allows multiple developers to work on a project.

Flutter is a platform that allows you to build applications for various platforms, including mobile, web, and desktop, using a single codebase. For this project we are using a web application.

We have set up a Github repository containing our flutter project then we designed our dev container by setting up an ubuntu container in our codespace.

In this codespace we set up our flutter application in our container.

To run commands after the container is created.
I edited the "postCreateCommand": "sudo chown -R vscode /flutter/.pub-cache/" to allow us to use our flutter commands and run our application.

Right now our application contains builds for android, ios, macos, web, windows and linux for now we will focus on web applications

To run our contsinerized development enviroment we go into our application using 'cd app'
Then we run our 'flutter run -d web-server' to run our application on our web server.
A link would appear in our bash terminal displaying our application.

At this point in our project we have a clicker web application which is the base Flutter app we have containerized.
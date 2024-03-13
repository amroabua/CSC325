# DevContainer Environment

## Introduction 
A Development Container (DevContainer) serves as the backbone of a consistent and reproducible development environment. It ensures that all team members work with the same dependencies, tools, and configurations. In the context of Flutter application development, the DevContainer streamlines the setup process and fosters collaboration.

## Configuration
For my Flutter development environment, I selected a Docker image explicitly designed for Flutter. This image includes the Flutter SDK, Dart and for our Flutter development environment, I selected a Docker image explicitly designed for Flutter. I specifically used Ubuntu for the DevContainer.json with the Jammmy based image.

## Integration with VS code
Our DevContainer seamlessly integrates with Visual Studio Code (VS Code), providing a unified development experience. Some extensions I used were the DevContainers extension that uses a Docker container as a full-featured development environment. I also used Github Repositories and GitHub Codespaces so that I can work wiht my Github codespace from VS code.

## Usage
For you to run this container on your own the usgae would be the steps that followed:

Clone the Flutter project repository from GitHub.

Open the project folder in Visual Studio Code.

VS Code detects the DevContainer configuration and prompts to reopen the project in a DevContainer.
Accept the prompt to start the development environment within the configured Docker container.

Use the integrated terminal in VS Code to execute Flutter commands, such as running the application or running tests. 
Specifially use: flutter run -d web-server to run your app on the web (make sure you are in the app before you do this)

## Challenges and Solutions
When Setting up my DevContainer enviroment I ran into the issue of adding my own container and setting up in my Github Repository. To set up my container I had to apply the DevContainer extension to use Ubuntu and use the post create command: sudo chown -R vscode /flutter/.pub-cache/". After this I learned to commit my chages through command line to github so that I can process my finished container on Github. 

## Conclusion
Utilizing a DevContainer for our Flutter project offers several advantages. It ensures a consistent and reproducible environment, facilitates collaboration, and streamlines the onboarding process. The insights gained from configuring and using the DevContainer contribute to an efficient and scalable development process.

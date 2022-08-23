# DevContainers
This repository was created for download the proper setup to be used with Visual Studio Code per technology/environment

The usage is intendend to be a dev environment running in a container, installing all the necesary toolset without the limitation of the OS host running locally. 
Doing it in this way, you can run and work with your code independently your local envineront. Despite that you don't need to worry about install tools.

Here is the arquitecture

<img src="./docs/img/architecture-containers.png">

This repository will help you with the following list of readt to use dev environments.

* nodejs
* react
* python 3x
* C++

If you need to use any of these  dev environemnts, you just need to copy the .devcontainer folder into your root project folder and use The <b>Visual Studio Code Remote - Containers extension</b>. You can download from <a href="https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers" >Here</a>

The extension starts (or attaches to) a development container running a well defined tool and runtime stack. Workspace files can be mounted into the container from the local file system, or copied or cloned into it once the container is running. Extensions are installed and run inside the container where they have full access to the tools, platform, and file system.

You then work with VS Code as if everything were running locally on your machine, except now they are separated inside a container.

<img src="./docs/img/remote-containers-readme.gif">
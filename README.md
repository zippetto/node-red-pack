# node-red-pack
Node-RED package in snap format that includes useful nodes for industrial scenarios

## Build

If you want to run the latest code from git, here's how to get started:

1. Clone the code:

        git clone https://github.com/zippetto/node-red-pack.git
        cd node-red-pack

2. Build the snap

        snapcraft

3. Install on your system

        snap install <package>.snap --devmode

## Docker inside Node-RED (Ubuntu Core 16)

If you want to manage docker containers inside a flow (for example, exec node) you need:

        snap connect node-red-pack:privileged :docker-support
        snap connect node-red-pack:support :docker-support
        snap connect node-red-pack:docker-cli docker:docker-daemon
        snap connect node-red-pack:docker-executables docker:docker-executables


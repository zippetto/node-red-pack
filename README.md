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

Test flow

        [{"id":"8336cb81.926da8","type":"exec","z":"ba0ca96d.57d278","command":"docker-wrapper docker version","addpay":false,"append":"","useSpawn":"false","timer":"","oldrc":false,"name":"docker wrapper","x":337,"y":605,"wires":[["2a49e83a.b415b8"],[],[]]},{"id":"d58766b2.ffadc8","type":"inject","z":"ba0ca96d.57d278","name":"","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"x":140,"y":600,"wires":[["8336cb81.926da8"]]},{"id":"2a49e83a.b415b8","type":"debug","z":"ba0ca96d.57d278","name":"","active":true,"console":"false","complete":"false","x":570,"y":600,"wires":[]}]

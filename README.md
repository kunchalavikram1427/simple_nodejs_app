# Simple Nodejs Application

### About node.js
```
https://nodejs.org/en/about/
```
NPM stores dependencies in two files — package.json and package-lock.json. If you use package.json, the build is not reproducible. When you run npm install the package manager puts the last minor release for not strict dependencies. To fix the dependency tree, we use the package-lock.json file. All versions of packages are strictly specified there.

### Install node.js in AWS EC2
```
https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-up-node-on-ec2-instance.html
```

### Install node.js in ubuntu 18.04
```
https://www.geeksforgeeks.org/installation-of-node-js-on-linux/
```
```
sudo apt update -y
sudo apt install -y nodejs npm
npm -v
node -v
```
### Install docker
```
https://docs.docker.com/engine/install/ubuntu/
```

### Build and run locally
`npm install` command will download all the dependencies that are written in the package.json file in the current directory under `node_modules` folder.

```
npm install 
node server.js
```
### Build Image
```
docker build . -t node-web-app:1.0
```
### Run the Image
```
docker run -d --name app -p 8080:8080 node-web-app:1.0
```
### GitLab CI Basic Template
```yaml

# default:
#     image: node:latest

# cache: 
#     key: nodemodules
#     paths:
#         - node_modules/

stages: 
    - build
    - deploy

build:
    stage: build
    script:
        - apt update -y
        - apt install -y npm
        - npm -v
        - npm install
    cache: # job level or put globally
        key: nodemodules
        paths:
            - node_modules/

deploy:
    stage: deploy
    script:
        - apt update -y
        - apt install -y nodejs
        - node -v
        - node server.js &
    cache:
        key: nodemodules
        paths:
            - node_modules/
```
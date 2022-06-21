# Simple nodejs Application

### About node.js
```
https://nodejs.org/en/about/
```

### Install node.js in AWS EC2
```
https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-up-node-on-ec2-instance.html
```

### Install node.js in ubuntu
```
https://www.geeksforgeeks.org/installation-of-node-js-on-linux/
```
```
sudo apt install -y nodejs npm

```
https://www.geeksforgeeks.org/installation-of-node-js-on-linux/

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
    cache:
        key: nodemodules
        path:
            - node_modules/

deploy:
    stage: deploy
    script:
        - apt update -y
        - apt install -y nodejs
        - node -v
    cache:
        key: nodemodules
        path:
            - node_modules/
```
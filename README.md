# Simple nodejs Application

### About node.js
```
https://nodejs.org/en/about/
```

### Install node.js in AWS EC2
```
https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-up-node-on-ec2-instance.html
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

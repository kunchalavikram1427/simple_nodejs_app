# Simple nodejs Application

### Build Image
```
docker build . -t node-web-app:1.0
```

### Run the Image
```
docker run -d --name app -p 8080:8080 node-web-app:1.0
```

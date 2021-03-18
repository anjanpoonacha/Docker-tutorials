# Docker Node Project

#### Project Flow
![Project Flow](1.png)

#### Docker run with port mapping
```
sudo docker run -p 8080:8080 <image id | image name> 
```
- ![Port Mapping](2.png)

#### Avoid copying files to the root directory (add to the dockerfile)
- `WORKDIR /usr/app` (before `COPY`)

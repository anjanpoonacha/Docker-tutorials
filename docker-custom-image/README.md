# Creating a Custom Image

#### Process and Flow  
- ![Process]('1.png')
- ![Flow]('2.png')

#### Dockerfile
- ![Dockerfile]('3.png')
- ![Dockerfile Teardown]('4.png')


1.  `FROM` Specify the dock or image that we want to use as a base to run instruction 
    - `apline` base image from alpine should be used

2. `RUN` Execute some command while we are preparing out custom image
3. `CMD` Specifies what should be executed when our image is used to start up a brand new container.

##### docker build
```
docker build .
```
1. Gives the dockerfile off to the CLI
2. `build` takes the dockerfile and generates an image 
3. `.` (build context) - set of files and folders that belongs to our project that we want to encapsulate or wrap in this container.

#### Run command explained
1. ![RUN command explained]('5.png')
2. ![RUN command explained-2]('5_1.png')

#### CMD command explained
![CMD command explained]('6.png')
![CMD command explained-2]('6_1.png')

- `CMD` doesn't actually execute the command, but it sets as the primary command.

> With every step along the way we take the image, which was generated in the previous step and we create a new container out of it. We execute the command in the container or make a change to its file system.

> We then look at that container, we take a snapshot of its file system and save it as an output for the next instruction along the chain.

> When ther is no more instructions to execute the image that was generated during that last step is output from the entire process as the final image that we really care about. 


#### Tagging an Image (Rename)
![Tagging an Image]('7.png')
![Tagging an Image-2]('7_1.png')

```
sudo docker build -t anjanpoonacha/project_name:latest .
```

#### Creating a container out of an Image

```
1. docker run -it alpine sh
2. docker ps (get the <id>)
3. docker commit -c 'CMD ["redis-server"]' <id> --> get <sha256>
4. docker run <sha256>
```

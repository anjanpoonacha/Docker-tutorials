# Docker tutorials

#### Override the default script
```
sudo docker run busybox echo hi there
```

#### List of all file in Busybox Image
```
sudo docker run busybox ls
```
- Prints the filename existing on the container. The busy box image has default filesystem snapshot.
Busybox image has default folder.
When we create new container out of the image, we take the FS snapshot and stick it in as a folder in the container.
echo and ls commands work in the busybox and not in the hello-world image bcz those programs only exist in the busybox

- ![Flow Diagram 'docker run'](/1.png)


#### List of all running images
```
sudo docker ps
```

#### List of all images from start
```
sudo docker ps --all
```

#### Run an image real quick
```
sudo docker run busybox ping google.com
```

#### What is docker run?
```
docker run = docker create + docker start
```

- ![Flow Diagram 'docker run'](/2.png)

##### More on docker run..

```
sudo docker create hello-world
```

```
sudo docker start -a <id>
```
- `-a` will make the docker watch for the output from the container and print the output into the terminal. (attach)

#### Start the exited container with default command (can't change the default command)
```
sudo docker start -a <container ID>
```

#### Clear All the containers
`sudo docker system prune`

#### Getting the log of previously run container
```
sudo docker log <Container ID>
```

#### Stop the container
```
sudo docker stop <Container ID>
```
- Hardware signal is sent to the process(primary process inside that container) --> sends <em>SIGTERM</em> (signal terminate). It tells to shut down on its own time. Lot of programming languages have an ability to listen to this signal in the code base. From this signal process like saving file, emit a message etc can be done.

```
sudo docker kill <Container ID>
```
- Sends <em>SIGKILL</em> command. It means to shut down right now and you do not get to do any additional work.

#### Execute an additional command in a container
```
docker exec -it <container id> <command>
```
- ![Execute command](/4.png)

- ![Execute command](/3.png)
``` 
-it = -i + -t
``` 
***-i*** -> connects the our terminal to the remote terminal <br/> ***-t***  -> autoformatting, etc

#### Open a Shell or Terminal in the context of the running container

```
docker exec -it <container id> sh
```
* options for command processor: `sh | bash | powershell | zsh `

```
docker run -it busybox sh
```

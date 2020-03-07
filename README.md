# Docker tutorials

#### Override the default script
`sudo docker run busybox echo hi there`
#### List of all file in Busybox Image
`sudo docker run busybox ls`
Prints the filename existing on the container. The busy box image has default filesystem snapshot.
Busybox image has default folder.
When we create new container out of the image, we take the FS snapshot and stick it in as a folder in the container.
echo and ls commands work in the busybox and not in the hello-world image bcz those programs only exist in the busybox

#### List of all running images
`sudo docker ps`

#### List of all images from start
`sudo docker ps --all`

#### Run an image real quick
`sudo docker run busybox ping google.com`

#### What is docker run?
`docker run` = `docker create` + `docker start`


 

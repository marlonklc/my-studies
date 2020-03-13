#### login on dockerhub
docker login -u <username> -p <password>

#### run a container docker
docker run -p <port-from>:<port-to> -d(non blocking terminal) <registry-path> 

#### pull image from registry
docker pull <registry-path>

#### tag image to push on registry
docker tag <<image-id>> <<registry-username>>/<<image-name>>

#### push image to registry
docker push <registry-username>/<image-name>

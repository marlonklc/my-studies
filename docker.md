#### login on dockerhub
`docker login -u <username> -p <password>`

#### run a container docker
```
docker run
  -d (run container in background)
  --rm (delete container when exit)
  -e <env-list> (set env variables)
  -p <port-from>:<port-to> (container port)
  -v <volume-from>:<volume-to> (bind mount volume)
  --name <image-name>
```
#### access to shell on running container
`docker attach <image-name>`

### build a image from Dockerfile
`docker build -t <image-name> <path-dockerfile>`

#### pull image from registry
`docker pull <registry-path>`

#### tag image to push on registry
`docker tag <image-id> <registry-username>/<image-name>`

#### push image to registry
`docker push <registry-username>/<image-name>`

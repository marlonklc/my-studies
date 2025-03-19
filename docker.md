## Install
- enable virtual machine on windows
 - `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
- install update on wsl2
 - wsl update x64 -> `https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi`
- set wsl2 default version (powershell)
 - `wsl --set-default-version 2`

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

#### remove docker images
`docker rmi -f <image-name>`

#### build a image from Dockerfile
`docker build -t <image-name> <path-dockerfile>`

#### pull image from registry
`docker pull <registry-path>`

#### tag image to push on registry
`docker tag <image-id> <registry-username>/<image-name>`

#### push image to registry
`docker push <registry-username>/<image-name>`

### toggle configs of docker-machine
- windows: `@FOR /f "tokens=*" %i IN ('docker-machine env --shell cmd <machinename>') DO %i`
- linux: `eval "$(docker-machine env <machinename>)"`

### docker stats (memory and cpu usage)
`docker stats`



# docker swarm
init swarm mode, need to configure principal node and slaves node
`docker swarm init` 

deploy stack by name, based on docker compose file
`docker stack deploy -c docker-compose.yml <stack>`

list services
`docker service ls`

list services by stack or stack and service name
`docker service ps <stack>`
`docker service ps <stack>_<service>`

scale service by name
`docker service scale <stack>_<service>=2`

force update/redeploy from stack and service
`docker service update --force <stack>_<service>`

force update all services from stack
`docker service ls --format '{{.Name}}' | grep <stack>_ | xargs -I {} docker service update --force {}

show ip addres from docker
`ip addr show docker0`
### AWS CLI
- install
- run `aws configure`
  - type key ID
  - type secret key
  - define zone (us-east-1)

### create instance EC2 by docker-machine
run `docker-machine create --driver amazonec2 <name>`

view configs docker-machine created before
`docker-machine env <name>`
configure new docker-machine envs
```
docker-machine env --shell cmd my-default
FOR /f "tokens=*" %i IN ('docker-machine env --shell cmd my-default') DO %i
```


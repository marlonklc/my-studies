## AWS CLI
- install
- run `aws configure`
  - type key ID
  - type secret key
  - define zone (us-east-1)

## create instance EC2 by docker-machine
- (1) run `docker-machine create --driver amazonec2 <name>`
- (2) view configs docker-machine (created on step 1) `docker-machine env <name>`
- (3) configure new docker-machine env (created on step 1) `FOR /f "tokens=*" %i IN ('docker-machine env --shell cmd <name>') DO %i`

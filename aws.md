## AWS CLI
- install
- run `aws configure`
  - type key ID
  - type secret key
  - define zone (us-east-1)

## create instance EC2 by docker-machine
- (1) run `docker-machine create --driver amazonec2 <name>`
- (2) view configs docker-machine (created on step 1) `docker-machine env <name>`
- (3) configure new docker-machine env (created on step 1) 
```
@FOR /f "tokens=*" %i IN ('docker-machine env --shell cmd <name>') DO %i
```

## generate SSL certificate with ACM
- open on aws console: Identity and Security > Certificate Manager
  - choose 'generate public certificate'
  - put your domain like as example.com (prefer to put with 'www' and without 'www' so that the client can access both ways)
  - choose what kind of validation do you prefer email/dns (email its more simple ; dns you need configure on your domain provider. Looks below)
  - define a tag with key/value
  - confirm and see on the end your record name and value. PS: Save them for future use
  
### certificate by AWS CLI
https://docs.aws.amazon.com/pt_br/elasticloadbalancing/latest/classic/elb-create-https-ssl-load-balancer.html
  
### configuration google domains to validate your ssl created
- open your google domains on DNS settings
- find section 'Custom resource records'
- put on columns:
  - Name: record name received on aws. Only the beginning of the name, its looks like `_8abc6414bbf92b5db7147903140c6123`
  - Type: choose CNAME
  - Data: record value receid on aws. Put all value, its looks like `_117c09eef51d9a25364343bd71093ccb.nhqijqilxf.acm-validations.aws.`
- save and waits until the settings are propagated (usually takes a few minutes)

## >> requirements
-- install google sdk (https://cloud.google.com/sdk/install)

## compute engine
Compute engine is like as AWS EC2
##### to conect on a compute engine
`gcloud compute ssh <username>@<instance> --zone <zonename>`
#### command to set current project 
`gcloud config set project <projectid>`

## buckets
Buckets are like as AWS S3
#### create a bucket
`gsutil mb gs://<bucketname>`
#### copy any file to bucket
`gsutil cp <filename> gs://<bucketname>/<path>`

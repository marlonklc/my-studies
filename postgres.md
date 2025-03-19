## Install server

`sudo apt update`
`sudo apt install postgresql postgresql-contrib -y`
ensure that service is running
`sudo systemctl start postgresql.service`

## install client (if necessary)
`sudo apt-get install -y postgresql-client`

## access by roles

accesing user on linux
`sudo -i -u postgres`

access PSQL direct by user
`sudo -u postgres psql`

create new user/role
`sudo -u postgres createuser --interactive`

## create and acces database

to create
`sudo -u postgres createdb <dbname>`

to access
`psql -d postgres`

check connection info inside of psql (postgres=#)
`\conninfo`


change password of user
> WITH ENCRYPTED
`sudo -u <user> psql -c "ALTER USER <user> PASSWORD '<newpassword>';"`
grant privileges (optional)
`GRANT ALL PRIVILEGES ON DATABASE <dbname> TO <user>;`


## permit external connections

edit file postgresql.conf
`sudo nano /etc/postgresql/16/main/postgresql.conf`
set address allowed
`listen_addresses = 'localhost,192.168.1.100'`

edit file pg_hba.conf
`sudo nano /etc/postgresql/16/main/pg_hba.conf`
set address allowed
`host    <dbname>    <user>    192.168.1.100/32    md5`

restart service
`sudo systemctl restart postgresql`



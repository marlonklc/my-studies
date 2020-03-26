# General Commands
#### start a new project with node
`npm init -y`
#### install a module
```
npm install <dependenciename>
  -P (install in dependencies. This is default if you doesn't pass one argument) 
  -D (install just in devDependencies)
```
#### execute a module without install it
`npx <modulename> <args>`

# Relational Database Modules

## knex

####initial command to generate knexfile
`npx knex init`

### ----- MIGRATIONS
Migrations are a way to make database changes or updates, like creating or dropping tables. Its like liquibase or flyway on Java

#### create an migration (to specific table)
`npx knex migrate:make <migrationname>`

#### execute all migrations
`npx knex migrate:latest`

### -----------------

# Non Relational Database Modules

## mongoose (MongoDB)

# Udacity: Build A Storefront Backend

This is a backend API build in Nodejs for an online store. It exposes a RESTful API that will be used by the frontend developer on the frontend.

The database schema and and API route information can be found in the [REQUIREMENT.md](REQUIREMENTS.md)

## Installation Instructions

This section contains all the packages used in this project and how to install them. However, you can fork this repo and run the following command at the root directory to install all packages.

`yarn` or `npm install`

### Packages

Here are some of the few packages that were installed.

#### express

`npm i -S express`
`npm i -D @types/express `
`npm i -S express-rate-limit`

#### typescript

`npm i -D typescript`

#### db-migrate

`npm install -g db-migrate`
`npm install -g db-migrate-pg`

#### rimraf

`npm install --save rimraf`

#### cors

`npm install --save cors`

#### bcrypt

`npm -i bcrypt`
`npm -i -D @types/bcrypt`

#### morgan

`npm install --save morgan`
`npm -i -D @types/morgan`

#### tsc-watch

`npm install --save tsc-watch`

#### jsonwebtoken

`npm install jsonwebtoken --sav`
`npm -i -D @types/jsonwebtoken`

#### helmet

`npm install helmet`

#### dotenv

`npm install --save-dev dotenv`

#### pg

`npm install pg`

#### jasmine

`npm install jasmine jasmine-spec-reporter @types/jasmine @ert78gb/jasmine-ts ts-node --save-dev`

#### supertest

`npm i supertest`
`npm i --save-dev @types/supertest`

==================================================================================
= **\*\*** Or you can relax and save time and do it in a moment by : =
= # npm install =
= it will install all dependencies and devDependencies in the =
= package.json file =
= and all we need will be well =
==================================================================================

## project structure 

`$  users`

  - add a user
  - get all  users
  - get user with id
  - update  user
  - authenticate  user
  - delete  user by id
  - delete  user by username


 $   `products`

  - add  product
  - get all products
  - get  product with id
  - update  product
  - delete  product by name
  - delete  product  by id


 $    `orders`

  - add  order
  - get all orders
  - get specific order
  - get all orders for specific user
  - get all orders including specific product
  - update status of order
  - add product to order
  - get all prodcuts of order
  - delete order
  - delete the order which include specific products
  - delete order for specific user


  ================================================================================

  ## Enviromental Variables Set up
Bellow are the environmental variables that needs to be set in a `.env` file. This is the default setting that I used for development, but you can change it to what works for you. 

**NB:** The given values are used in developement and testing but not in production. 

PORT=3000
NODE_ENV=dev
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_USER=postgres
POSTGRES_PASSWORD=8877
POSTGRES_Db=MYSTORE_DEV
POSTGRES_Db_TEST=MYSTORE_TEST
BCRYPT_PASSWORD = ASD-SAS
SALT_ROUND =10
TOKEN_SECRET = UDACITY

$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$

## connect database

in terminal we should connect to the database 
it is tow database created for this project

# store_dev 
for development

# store_test 
for testing

### we could connect database by postgres connection with PG
psql -h localhost -U postgres
\c mystore_dev

## Start App
`npm run watch`
npm run start

start server

### Running Ports 
After start up, the server will start on port `3000` and the database connected on port `5432`

## Endpoint Access
All endpoints are described in the [REQUIREMENT.md](REQUIREMENTS.md) file. 

## Token and Authentication
Tokens are passed along with the http header as 
Authorization   Bearer <token>


## Testing
Run test with 

npm ru test`

It sets the environment to `test`, migrates up tables for the test database, run
 the test then migrate down all the tables for the test database.

## Middleware needed 
as shown in package.json


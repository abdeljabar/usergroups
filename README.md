# About the API

This is a mini API for managing users & groups.

## 1. Clone the repository
`git clone https://github.com/abdeljabar/usergroups`

## 2. Build the containers
`docker-compose up --build`

## 3. Run composer install
`docker-compose run php composer install`

## 4. Create database
`docker-compose run php bin/console d:d:c`

## 5. Run doctrine migrations
`docker-compose run php bin/console d:m:m`

## 6. Load doctrine fixtures
`docker-compose run php bin/console d:f:l`

## 7. Link to the app
`http://localhost:8080`

# Automatic tests

## 1. Create database
`docker-compose run php bin/console d:d:c --env=test`

## 2. Create database
`docker-compose run php bin/console d:m:m --env=test`

## 3. Create database
`docker-compose run php bin/phpunit`

# Getting started with the Api

These endpoints don't necessitate authentication.

## Get paginated users
`GET http://localhost:8080/users`

## Get user details
`GET http://localhost:8080/users/{id}`

## Get paginated groups
`GET http://localhost:8080/groups`

## Get group details
`GET http://localhost:8080/groups/{id}`

## Admin authentication

To login please send json in the body of this uri. A fresh token will be generated for you to use in the endpoints that need authentication.
`POST http://localhost:8080/authentication_token`

The json body:

`{
"username": "admin",
"password": "password"
}`

## To create a new user
`POST http://localhost:8080/users`

The json body:

`{
"firstName": "John",
"lastName": "Doe",
"email": "taoufikallah@gmail.com",
"phone": "066900000",
"age": 27,
"type": "Test"
}`

## To update a user
`POST http://localhost:8080/users/{id}`

The json body:

`{
"firstName": "John Edited"
}`

## To delete a user
`DELETE http://localhost:8080/users/{id}`

## To create a new group
`POST http://localhost:8080/groups`

The json body:

`{
"name": "The Old Generation",
"description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea "
}`

## To update a group
`POST http://localhost:8080/groups/{id}`

The json body:

`{
"name": "The New Generation"
}`

## To delete a group
`DELETE http://localhost:8080/groups/{id}`
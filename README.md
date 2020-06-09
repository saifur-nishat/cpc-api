# cpc-api

cpc-api is REST API for Chittagong Pet Club.
cpc-api follows Token based authentication and uses PostgreSQL as database.

## Installation

First clone the repository and navigate to cpc-api folder.
Then run following commands to install all the dependencies  

```bash
docker build .
docker-compose build
```
Then run the following command to run in browser using address http://127.0.0.1:8000
```bash
docker-compose up
```
## API Endpoints
## USER Endpoints

For creating a user we'll use following endpoint
```bash
/api/user/create
```
Request format will be
```JSON
{
    "email": "email address",
    "password": "password",
    "name": "your name"
}
```
We'll send the request through POST method.
email, password are mandatory and name is optional.

In order to create an authentication token we'll use following endpoint 
```bash
/api/user/token
```
Then send a POST request in the following format
```JSON
{
    "email": "email address",
    "password": "password"
}
```
System will return a API token in following format
```JSON
{
    "token": "API token"
}
```
For updating user information user must be authenticated and use following endpoint
```bash
/api/user/me
```
Then send a request using PUT/PATCH method in following format
```JSON
{
    "token": "your authentication token",
    "email": "updated email",
    "password": "updated password",
    "name": "updated name"
}
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)

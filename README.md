# WALLET MICROSERVICE

Wallet microservice running on the JVM that manages credit/debit transactions on behalf of players

## Requirements

1. Java 8
2. Maven 3

## How to run the application

1. Execute below command to build the application from root folder in the command line
```
mvn clean install
```
2. To run the application execute below command
```sh
mvn spring-boot:run 
```

3. Once the application started you can test it by going to. Default application port is set to 8080 

```sh
http://localhost:8080/swagger-ui/index.html
```
## API endpoints

### 1. Create Wallet - Post endpoint

```sh
http://localhost:8080/api/save
```
##### Sample request

```
{
  "email": "test@gmail.com",
  "firstName": "tester",
  "lastName": "great"
}
```
### 2. Get balance by Player Id - Get endpoint
```
http://localhost:8080/api/balance/{id}
```
### 3. Get transactions By Player id - Get endpoint
```
http://localhost:8080/api/transaction/{id}
```
### 4. Debit money - Post endpoint
```
http://localhost:8080/api/credit/{id}
```
##### Sample request  

```
{
  "amount": 1000.00,
  "dateTime": "2022-11-20T23:41:31.219Z",
  "type": "string",
  "uniqueId": "3fa85f64-5717-4562-b3fc-2c963f66afb7"
}
```

### 4. Withdrawn money - Post endpoint
```
http://localhost:8080/api/debit/{id}
```
##### Sample Request
```
{
  "amount": 500.00,
  "dateTime": "2022-11-20T23:41:31.219Z",
  "type": "string",
  "uniqueId": "3fa85f64-5717-4562-b3fc-2c963f66afc6"
}
```

### 5. Get Transaction by user id - Get endpoint
```
http://localhost:8080/api/transaction/{id}
```

### Important

Only two transaction are supported and those transaction codes need to be used when adding transactions
```
CREDIT - for deposit transactions
DEBIT - for Withdraw transactions
```
### Technologies used
***
Java8
Spring boot
JPA
H2
***

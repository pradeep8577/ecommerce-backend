# ecommerce-backend-api

It is a rest api that i have created for learning purpose

## Run Locally :white_check_mark:

Clone the project

```bash
  git clone https://github.com/pradeep8577/ecommerce-backend.git
```

Go to the project directory

```bash
  cd ecommerce-backend
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run dev
```
Create a new file called ```.env``` Copy all the content from ```.env.example``` and paste it into .env Change all url.


## Environment Variables :mushroom:

To run this project, you will need to add the following environment variables to your .env file

`API_KEY = 5000`

`ANOTHER_API_KEY = true`

`APP_PORT` 

`DEBUG_MODE`

`DB_URL`

`JWT_SECRET` 

`REFRESH_SECRET` 

`APP_URL = http://localhost:5000`

# API References :key:

## Variables

| Key | Value | Type |
| --- | ------|-------------|
| localhost | http://localhost:5000/api | default |



## Endpoints :point_left:
### [Auth](#auth)

* 
    1. [Login](#1-login)
    2. [Register](#2-register)
    3. [Who am I](#3-who-am-i)
    4. [Refresh Token](#4-refresh-token)
    5. [Log out](#5-log-out)


### [Products](#products)
* 
    1. [Create a product](#1-create-a-product)
    2. [Update product](#2-update-product)
    3. [Delete Product](#3-delete-product)
    4. [Get Single Product](#4-get-single-product)
    5. [Get All Products](#5-get-all-products)

--------



## Auth :seedling:



### 1. Login



***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{localhost}}/login
```



***Body:***

```js        
{
    "email": "pradeep@gmail.com",
    "password": "12345"
}
```



### 2. Register



***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{localhost}}/register
```



***Body:***

```js        
{
    "name": "Pradeep Pawar",
    "email": "pradeep@gmail.com",
    "password": "12345",
    "repeat_password": "12345"
}
```



### 3. Who am I



***Endpoint:***

```bash
Method: GET
Type: 
URL: {{localhost}}/me
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer {{access_token}} | **access_token** must be a valid JWT token. |



### 4. Refresh Token



***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{localhost}}/refresh
```



***Body:***

```js        
{
    "refresh_token": "{{refresh_token}}"
}
```



### 5. Log out



***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{localhost}}/logout
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer {{access_token}} | **access_token** must be a valid JWT token. |



***Body:***

```js        
{
    "refresh_token": "{{refresh_token}}"
}
```



## Products :moneybag:



### 1. Create a product



***Endpoint:***

```bash
Method: POST
Type: FORMDATA
URL: {{localhost}}/products
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer {{access_token}} | **access_token** must be a valid JWT token. |



***Body:***

| Key | Value | Type |
| --- | ------|-------------|
| image |  | img |
| name | margarita | string |
| price | 4099 | number |
| size | medium | string |



### 2. Update product



***Endpoint:***

```bash
Method: PUT
Type: FORMDATA
URL: {{localhost}}/products/63a1cadc57dffda2abe4e492
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer {{access_token}} | **access_token** must be a valid JWT token. |



***Body:***

| Key | Value | Type |
| --- | ------|-------------|
| name | Chicken Dominator | string |
| price | 909 | number |
| size | Medium | string |



### 3. Delete Product



***Endpoint:***

```bash
Method: DELETE
Type: 
URL: {{localhost}}/products/63a1ce70106068dfed0dd378
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer {{access_token}} | **access_token** must be a valid JWT token. |



### 4. Get Single Product



***Endpoint:***

```bash
Method: GET
Type: 
URL: {{localhost}}/products/63a1cf824c547ec296581085
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer {{access_token}} | **access_token** must be a valid JWT token. |



### 5. Get All Products



***Endpoint:***

```bash
Method: GET
Type: 
URL: {{localhost}}/products
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer {{access_token}} | **access_token** must be a valid JWT token. |



---

## Tech Stack :heart:


**Server:** Node, Express

## Query Options

| Function | Parameter | Description | Example |
| --- | --- | --- | --- |
| Filtering | /attribute=value | Returns all featured products | /company=ikea : returns all products from ikea |
| Sorting | /sort=value1,-value2 | Returns sorted list of products according to the parameter options. - is used to indicate descending | /sort=name,-price : returns all products sorted in ascendign order of name and decreasing price values |
| Selecting | /fields=value1,value2 | Returns all products with only the selected fields | /fields=company,name : returns all products with only name and company |
| Numeric Filtering | /numericFilters=field op value | Returns all products with the filter applies | /numericFilters=price>30 : returns all products with their price above 30|
| Paging | /page=value&limit=value | Returns all products in pages with limit specifying no of products in a page| /page=4&limit=10 : returns the 4th page with 10 products |

### Products

```
GET      /products
GET      /products/:id
POST     /products
PUT      /products/:id
DELETE   /products/:id

```

### Categories

```
GET      /categories
GET      /categories/:id
POST     /categories
PUT      /categories/:id
DELETE   /categories/:id

```

## [Postman](https://documenter.getpostman.com/view/24887117/2s8Z6savNK) ![postman-logo-icon-orange](https://user-images.githubusercontent.com/52816688/209198935-d0bfdd57-c236-4ed4-b717-90ca6dd4e290.svg) 
Get the postman files [here.](https://documenter.getpostman.com/view/24887117/2s8Z6savNK)




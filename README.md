# Ding-Dong-backend
### Overview
This backend application is a simplified version of a platform for food delivery.
https://alexishaodingdong.herokuapp.com/

### Get all users
`GET` `/users/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": 1,
            "name": "Chris Elliott",
            "username": "cre123",
            "balance": 0.0,
            "email": "cre123@cornell.edu",
            "orders": [],
            "reviews_posted": [<SERIALIZED REVIEW WITHOUT USER AND RESTAURANT FIELD>, ...]
        }
        ...
    ]
}
```
### Get a specific user
`GET` `/user/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "username": <USER INPUT FOR USERNAME>,
        "balance": <USER INPUT FOR BALANCE>,
        "email": <USER INPUT FOR EMAIL>,
        "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...],
        "reviews_posted": [<SERIALIZED REVIEW WITHOUT USER AND RESTAURANT FIELD>, ...]
    }
}
```
### Add to balance
`POST` `/user/{id}/balance/`
##### Request
```yaml
{
    "amount": <USER INPUT FOR AMOUNT>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "username": <USER INPUT FOR USERNAME>,
        "balance": <BALANCE PLUS USER INPUT FOR AMOUNT>,
        "email": <USER INPUT FOR EMAIL>,
        "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...],
        "reviews_posted": [<SERIALIZED REVIEW WITHOUT USER AND RESTAURANT FIELD>, ...]
    }
}
```
### Update a specific user
`POST` `/user/{id}/`
##### Request
```yaml
{
    "username": <USER INPUT FOR USERNAME>,
    "balance": <USER INPUT FOR BALANCE>,
    "password_digest": <USER INPUT FOR PASSWORD>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "username": <USER INPUT FOR USERNAME>,
        "balance": <BALANCE PLUS USER INPUT FOR AMOUNT>,
        "email": <USER INPUT FOR EMAIL>,
        "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...],
        "reviews_posted": [<SERIALIZED REVIEW WITHOUT USER AND RESTAURANT FIELD>, ...]
    }
}
```
### Delete a specific user
`DELETE`  `/user/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "username": <USER INPUT FOR USERNAME>,
        "balance": <BALANCE PLUS USER INPUT FOR AMOUNT>,
        "email": <USER INPUT FOR EMAIL>,
        "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...],
        "reviews_posted": [<SERIALIZED REVIEW WITHOUT USER AND RESTAURANT FIELD>, ...]
    }
}
```
### Get all restaurants
`GET` `/restaurants/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": 1,
            "name": "Boston Fries",
            "rating": 0.0,
            "categories": [ <SERIALIZED CATEGORY WITHOUT RESTAURANTS FIELD>, ...],
            "menu": [ <SERIALIZED DISH WITHOUT RESTAURANT FIELD>, ...],
            "reviews": [ <SERIALIZED REVIEW WITHOUT RESTAURANT AND USER FIELD>, ...],
            "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...]
        }
        ...
    ]
}
```
### Create a restaurant
`POST` `/restaurant/`
##### Request
``` yaml
{
    "name": <USER INPUT FOR NAME>
}
```
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "name": <USER INPUT FOR NAME>,
            "rating": 0.0,
            "categories": [],
            "menu": [],
            "reviews": [],
            "orders": []
        }
    ]
}
```
### Get a specific restaurant
`GET` `/restaurant/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "name": <USER INPUT FOR NAME>,
            "rating": <CALCULATED RATING>,
            "categories": [ <SERIALIZED CATEGORY WITHOUT RESTAURANTS FIELD>, ...],
            "menu": [ <SERIALIZED DISH WITHOUT RESTAURANT FIELD>, ...],
            "reviews": [ <SERIALIZED REVIEW WITHOUT RESTAURANT AND USER FIELD>, ...],
            "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...]
        }
    ]
}
```
### Update a specific restaurant
`POST` `/restaurant/{id}/`
##### Request
```yaml
{
    "name": <USER INPUT FOR NAME>
}
```
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "name": <USER INPUT FOR NAME>,
            "rating": <CALCULATED RATING>,
            "categories": [ <SERIALIZED CATEGORY WITHOUT RESTAURANTS FIELD>, ...],
            "menu": [ <SERIALIZED DISH WITHOUT RESTAURANT FIELD>, ...],
            "reviews": [ <SERIALIZED REVIEW WITHOUT RESTAURANT AND USER FIELD>, ...],
            "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...]
        }
    ]
}
```
### Delete a specific restaurant
`DELETE` `/restaurant/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "name": <USER INPUT FOR NAME>,
            "rating": <CALCULATED RATING>,
            "categories": [ <SERIALIZED CATEGORY WITHOUT RESTAURANTS FIELD>, ...],
            "menu": [ <SERIALIZED DISH WITHOUT RESTAURANT FIELD>, ...],
            "reviews": [ <SERIALIZED REVIEW WITHOUT RESTAURANT AND USER FIELD>, ...],
            "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...]
        }
    ]
}
```
### Get all dishes
`GET` `/dishes/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": 1,
            "name": "Hotdog",
            "price": 4.0,
            "sold_out": false
        },
        {
            "id": 2,
            "name": "Hawaiian pizza",
            "price": 2.0,
            "sold_out": false
        }
        ...
    ]
}
```
### Create a dish
`POST` `/dish/`
##### Request
```yaml
{
    "name": <USER INPUT FOR NAME>,
    "price": <USER INPUT FOR PRICE>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "price": <USER INPUT FOR PRICE>,
        "sold_out": false
    }
}
```
### Get a specific dish
`GET` `/dish/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "price": <USER INPUT FOR PRICE>,
        "sold_out": <USER INPUT FOR SOLD_OUT>
    }
}
```
### Update a specific dish
`POST` `/dish/{id}/`
##### Request
```yaml
{
    "name": <USER INPUT FOR NAME>,
    "price": <USER INPUT FOR PRICE>,
    "sold_out": <USER INPUT FOR SOLD_OUT>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "price": <USER INPUT FOR PRICE>,
        "sold_out": <USER INPUT FOR SOLD_OUT>
    }
}
```
### Delete a specific dish
`DELETE` `/dish/{id}/`
##### Response
```yaml
{
    "name": <USER INPUT FOR NAME>,
    "price": <USER INPUT FOR PRICE>,
    "sold_out": <USER INPUT FOR SOLD_OUT>
}
```
### Get orders of a user
`GET` `/user/{id}/orders/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "date_time": <NOW>,
            "dishes": [ <SERIALIZED DISH WITHOUT RESTAURANT AND ORDERS FIELD>, ... ],
            "total": <CALCULATED TOTAL BASED ON DISHES>,
            "paid": <USER INPUT FOR PAID>,
            "delivered": <USER INPUT FOR DELIVERED>
        }
    ]
}
```
### Create an order
`POST` `/user/{user_id}/restaurant/{restaurant_id}/order/`
##### Request
```yaml
{
    "driver_id": <USER INPUT FOR DRIVER_ID>
} 
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "date_time": <NOW>,
            "dishes": [],
            "total": 0.0,
            "paid": false,
            "delivered": false
        }
    ]
}
```
### Add a dish to an order
`POST` `/order/{id}/add/`
##### Request
```yaml
{
    "dish_id": <USER INPUT FOR DISH_ID>
}
```
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "date_time": <NOW>,
            "dishes": [ <SERIALIZED DISH WITHOUT RESTAURANT AND ORDERS FIELD>, ... ],
            "total": <CALCULATED TOTAL BASED ON DISHES>,
            "paid": <USER INPUT FOR PAID>,
            "delivered": <USER INPUT FOR DELIVERED>
        }
    ]
}
```
### Get a specific order
`GET` `/order/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "date_time": <NOW>,
            "dishes": [ <SERIALIZED DISH WITHOUT RESTAURANT AND ORDERS FIELD>, ... ],
            "total": <CALCULATED TOTAL BASED ON DISHES>,
            "paid": <USER INPUT FOR PAID>,
            "delivered": <USER INPUT FOR DELIVERED>
        }
    ]
}
```
### Update a specific order
`POST` `/order/{id}/`
##### Request
```yaml
{
    "paid": <USER INPUT FOR PAID>,
    "delivered": <USER INPUT FOR DELIVERED>
}
```
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "date_time": <NOW>,
            "dishes": [ <SERIALIZED DISH WITHOUT RESTAURANT AND ORDERS FIELD>, ... ],
            "total": <CALCULATED TOTAL BASED ON DISHES>,
            "paid": <USER INPUT FOR PAID>,
            "delivered": <USER INPUT FOR DELIVERED>
        }
    ]
}
```
### Delete a specific order
`DELETE` `/order/{id}/`
```yaml
{
    "success": true,
    "data": [
        {
            "id": <ID>,
            "date_time": <NOW>,
            "dishes": [ <SERIALIZED DISH WITHOUT RESTAURANT AND ORDERS FIELD>, ... ],
            "total": <CALCULATED TOTAL BASED ON DISHES>,
            "paid": <USER INPUT FOR PAID>,
            "delivered": <USER INPUT FOR DELIVERED>
        }
    ]
}
```
### Get the driver of a specific order
`GET` `/order/{id}/driver/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "license_plate_number": <USER INPUT FOR LICENSE_PLATE_NUMBER>,
        "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...]
    }
}
```
### Create a driver
`POST` `/driver/`
##### Request
```yaml
{
    "name": <USER INPUT FOR NAME>,
    "license_plate_number": <USER INPUT FOR LICENSE_PLATE_NUMBER>
}
````
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "license_plate_number": <USER INPUT FOR LICENSE_PLATE_NUMBER>,
        "orders": []
    }
}
```
### Delete a specific driver
`DELETE` `/driver/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "name": <USER INPUT FOR NAME>,
        "license_plate_number": <USER INPUT FOR LICENSE_PLATE_NUMBER>,
        "orders": [ <SERIALIZED ORDER WITHOUT USER, RESTAURANT, AND DRIVER FIELD>, ...]
    }
}
```
### Get reviews posted by a specific user
`GET` `/user/{id}/reviews/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": 1,
            "rating": 2,
            "content": "Meh"
        },
        {
            "id": 2,
            "rating": 5,
            "content": "Amazing"
        }
        ...
    ]
}
```
### Get reviews of a specific restaurant
`GET` `/restaurant/{id}/reviews/`
##### Response
```yaml
{
    "success": true,
    "data": [
        {
            "id": 1,
            "rating": 2,
            "content": "Meh"
        },
        {
            "id": 2,
            "rating": 5,
            "content": "Amazing"
        }
        ...
    ]
}
```
### Post restaurant review
`POST` `/restaurant/{id}/review/`
##### Request
```yaml
{
    "rating": <USER INPUT FOR RATING>,
    "content": <USER INPUT FOR CONTENT>,
    "user_id": <USER INPUT FOR USER_ID>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "rating": <USER INPUT FOR RATING>,
        "content": <USER INPUT FOR CONTENT>
    }
}
```
### Update a specific review
`POST` `/review/{id}/`
##### Request
```yaml
{
    "rating": <USER INPUT FOR RATING>,
    "content": <USER INPUT FOR CONTENT>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "rating": <USER INPUT FOR RATING>,
        "content": <USER INPUT FOR CONTENT>
    }
}
```
### Delete a specific review
`DELETE` `/review/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "rating": <USER INPUT FOR RATING>,
        "content": <USER INPUT FOR CONTENT>
    }
}
```
### Get all categories
`GET` `/categories/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": 1,
        "description": "Fast food"
    }
    ...
}
```
### Create a category
`POST` `/category/`
##### Request
```yaml
{
    "description": <USER INPUT FOR DESCRIPTION>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "description": <USER INPUT FOR DESCRIPTION>
    }
}
```
### Add a restaurant to a category
`POST` `/category/{id}/add/`
##### Request
```yaml
{
    "restaurant_id": <USER INPUT FOR RESTAURANT_ID>
}
```
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "description": <USER INPUT FOR DESCRIPTION>
    }
}
```
### Delete a specific category
`DELETE` `/category/{id}/`
##### Response
```yaml
{
    "success": true,
    "data": {
        "id": <ID>,
        "description": <USER INPUT FOR DESCRIPTION>
    }
}
```
### Register an account
`POST` `/register/`
##### Request
```yaml
{
    "name": <USER INPUT FOR NAME>,
    "username": <USER INPUT FOR USERNAME>,
    "email": <USER INPUT FOR EMAIL>,
    "password": <USER INPUT FOR PASSWORD>
}
```
##### Response
```yaml
{
    "session_token": <SESSION_TOKEN>,
    "session_expiration": <SESSION_EXPIRATION>,
    "update_token": <UPDATE_TOKEN>
}
```
### Login
`POST` `/login/`
##### Request
```yaml
{
    "email": <USER INPUT FOR EMAIL>,
    "password": <USER INPUT FOR PASSWORD>
}
```
##### Response
```yaml
{
    "session_token": <SESSION_TOKEN>,
    "session_expiration": <SESSION_EXPIRATION>,
    "update_token": <UPDATE_TOKEN>
}
```
### Update session
`/POST/` `/session/`
##### Request
```yaml
update_token
```
##### Response
```yaml
{
    "session_token": <SESSION_TOKEN>,
    "session_expiration": <SESSION_EXPIRATION>,
    "update_token": <UPDATE_TOKEN>
}
```
### Verify session implementation
`/GET/` `/secret/`
##### Response
```yaml
{
    "session_token": <SESSION_TOKEN>,
    "session_expiration": <SESSION_EXPIRATION>,
    "update_token": <UPDATE_TOKEN>
}
```

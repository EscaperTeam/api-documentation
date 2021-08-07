# Authentication

## Signup

> Request body

```json
{
  "email": "example@e.mail",
  "password": "password",
  "player_name": "player_name",
  "first_name": "first_name",
  "last_name": "last_name",
  "city": {
    "latitude": 0.0,
    "longitude": 0.0
  }
}
```

> Return `201 Created`

```json
{}
```

This endpoint create a player account for the user.

### HTTP Request

`POST {API_URL}/signup`

### Body parameters

Parameter | Description | Required
--------- | ----------- | --------
email | The email to use for registration | x
password | The password to login with | x
player_name | The name that will be used in the application | x
first_name | The firstname of the user | x
last_name | The lastname of the user | x
city | The city of the user | x

## Login

> Request body

```json
{
  "email": "example@e.mail",
  "password": "password"
}
```

> Return `200 OK`

```json
{
  "access_token": "azecocapzie", 
  "refresh_token": "acencoaieno", 
  "at_expires": 1627048679, 
  "rt_expires": 1658498279, 
  "role": "Player", 
  "id": "player_id"
}
```

This endpoint login a player and returns his credentials.

### HTTP Request

`POST {API_URL}/login`

### Body parameters

Parameter | Description | Required
--------- | ----------- | --------
email | The user's email | x
password | The user's password | x

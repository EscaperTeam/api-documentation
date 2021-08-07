# Player

<aside class="notice">
    All these endpoints should be call with a header containing `Authorization: Bearer {access_token}`.
    The `access_token` is given by the `/login` endpoint.
</aside>


## Get Players

> Return `200 OK`

```json
[
  {
    "id": "player_1", 
    "email": "example1@e.mail",
    "player_name": "",
    "first_name": "",
    "last_name": "",
    "city": {
      "latitude": 0,
      "longitude": 0
    },
    "verified": true
  },
  {
    "id": "player_2",
    "email": "example2@e.mail",
    "player_name": "",
    "first_name": "",
    "last_name": "",
    "city": {
      "latitude": 0,
      "longitude": 0
    },
    "verified": false
  }
]
```

This endpoint get a list of all players.

<aside class="notice">
    You must be logged in as an administrator.
</aside>

### HTTP Request

`GET {API_URL}/player`


## Create Player

> Request body

```json
{
  "email":"example@e.mail",
  "player_name":"player_name",
  "first_name":"first_name",
  "last_name":"last_name",
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

This endpoint create a player.

<aside class="notice">
    You must be logged in as an administrator.
</aside>

### HTTP Request

`POST {API_URL}/player`

### Body parameters

Parameter | Description | Required
--------- | ----------- | --------
email | The player's email | x
player_name | The player's in-app name | x
first_name | The player's first name | x
last_name | The player's last name | x
city | The player's city | x


## Get Player

> Return `200 OK`

```json
[
  {
    "id": "player_1",
    "email": "example1@e.mail",
    "player_name": "",
    "first_name": "",
    "last_name": "",
    "city": {
      "latitude": 0,
      "longitude": 0
    },
    "verified": true
  }
]
```

This endpoint get a player.

<aside class="notice">
    You must be logged in as an administrator or as the player.
</aside>

### HTTP Request

`GET {API_URL}/player/:playerID`

### URL Parameters

Parameter | Description
--------- | -----------
playerID | The id of the player to get


## Update Player

> Request body

```json
{
    "player_name":"player_name",
    "first_name":"first_name",
    "last_name":"last_name",
    "city": {
        "latitude": 0.0,
        "longitude": 0.0
    }
}
```

> Return `200 OK`

```json
{}
```

This endpoint update a player.

<aside class="notice">
    You must be logged in as an administrator or as the player.
</aside>

### HTTP Request

`PUT {API_URL}/player/:playerID`

### URL Parameters

Parameter | Description
--------- | -----------
playerID | The id of the player to get

### Body parameters

Parameter | Description | Required
--------- | ----------- | --------
player_name | The player's in-app name | 
first_name | The player's first name | 
last_name | The player's last name | 
city | The player's city | 


## Delete Player

> Return `200 OK`

```json
{}
```

This endpoint delete a player.

<aside class="notice">
    You must be logged in as an administrator or as the player.
</aside>

### HTTP Request

`DELETE {API_URL}/player/:playerID`

### URL Parameters

Parameter | Description
--------- | -----------
playerID | The id of the player to get

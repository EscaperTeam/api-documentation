# Player

<aside class="notice">
    All these endpoints should be call with a header containing `Authorization: Bearer {access_token}`.
    The `access_token` is given by the `/login` endpoint.
</aside>


## GetPlayers

> Return `200 OK`

```json
[
    {
        "ID": "player_someid",
        "Email": "example@e.mail",
        "PlayerName": "",
        "FirstName": "",
        "LastName": "",
        "City": {
            "latitude": 0,
            "longitude": 0
        },
        "Verified": false,
        "CreatedAt": "2021-07-12T09:47:17.05153Z",
        "UpdatedAt": "2021-07-12T09:47:17.05153Z"
    },
    {
        "ID": "player_someotherid",
        "Email": "example2@e.mail",
        "PlayerName": "",
        "FirstName": "",
        "LastName": "",
        "City": {
            "latitude": 0,
            "longitude": 0
        },
        "Verified": false,
        "CreatedAt": "2021-07-12T11:14:33.383204Z",
        "UpdatedAt": "2021-07-12T11:14:33.383204Z"
    }
]
```

This endpoint get a list of all players.

<aside class="notice">
    You must be logged in as an administrator.
</aside>

### HTTP Request

`GET {API_URL}/player`


## CreatePlayer

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


## GetPlayer

> Return `200 OK`

```json
[
    {
        "ID": "player_someid",
        "Email": "example@e.mail",
        "PlayerName": "",
        "FirstName": "",
        "LastName": "",
        "City": {
            "latitude": 0,
            "longitude": 0
        },
        "Verified": false,
        "CreatedAt": "2021-07-12T09:47:17.05153Z",
        "UpdatedAt": "2021-07-12T09:47:17.05153Z"
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


## UpdatePlayer

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


## DeletePlayer

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

# User API specs

## Register User
Endpoint: **POST /api/users**

**Request Body:**
``` json
{
    "username" : "fex",
    "password" : "secret",
    "name" : "fex xhr"
}
```

**Response Body (RESOLVE) ✅:**
``` json
{
    "data" :{
        "username" : "fex",
        "name" : "fex xhr"
    }
    
}
```

**Response Body (REJECT) ❌:**
``` json
{
    "errors" :{
        "message" : "Username already in use",
    }
    
}
```
## Login User
Endpoint: **POST /api/users/login**

**Request Body:**
``` json
{
    "username" : "fex",
    "password" : "secret",
    "name" : "fex xhr"
}
```

**Response Body (RESOLVE) ✅:**
``` json
{
    "data" :{
        "username" : "fex",
        "name" : "fex xhr",
        "token" : "session token is generated"
    }
    
}
```

**Response Body (REJECT) ❌:**
``` json
{
    "errors" :{
        "message" : "Username or password is wrong",
    }
    
}
```

## Get User

Endpoint: **GET /api/users/current**

Header: 
- Authorization: *token*

**Response Body (RESOLVE) ✅:**
``` json
{
    "data" :{
        "username" : "fex",
        "name" : "fex xhr",
    }
    
}
```

**Response Body (REJECT) ❌:**
``` json
{
    "errors" :{
        "message" : "Unauthorized",
    }
    
}
```
## Update User

Endpoint: **PATCH /api/users/currnet**

Header: 
- Authorization: *token*

**Request Body:**
``` json
{
    "username" : "fex", //opsional if you wanna update this
    "password" : "secret", //opsional if you wanna update this
}
```

**Response Body (RESOLVE) ✅:**
``` json
{
    "data" :{
        "username" : "fex",
        "name" : "fex xhr"
    }
    
}
```

**Response Body (REJECT) ❌:**
``` json
{
    "errors" :{
        "message" : "Unautorized",
    }
    
}
```
## Logout User

Endpoint : DELETE /api/users/current

Headers :
- Authorization: token

Response Body (Success) :

```json
{
  "data" : true
}
```
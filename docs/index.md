---
title: My Sample API v1.0.0

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="my-sample-api">My Sample API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. 

A sample API to demonstrate the documentation pipeline.

Base URLs:

* <a href="https://api.example.com/v1">https://api.example.com/v1</a>

<h1 id="my-sample-api-users">Users</h1>

## List Users

<a id="opIdlistUsers"></a>

> Code samples

```shell title="Shell"
# You can also use wget
curl -X GET https://api.example.com/v1/users \
  -H 'Accept: application/json'

```

```http title="HTTP"
GET https://api.example.com/v1/users HTTP/1.1
Host: api.example.com
Accept: application/json

```

```javascript title="JavaScript"

const headers = {
  'Accept':'application/json'
};

fetch('https://api.example.com/v1/users',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby title="Ruby"
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.example.com/v1/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python title="Python"
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.example.com/v1/users', headers = headers)

print(r.json())

```

```php title="PHP"
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.example.com/v1/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java title="Java"
URL obj = new URL("https://api.example.com/v1/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go title="Go"
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.example.com/v1/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users`

Retrieve a paginated list of all users.

<h3 id="list-users-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|integer|false|Maximum number of users to return|
|offset|query|integer|false|Number of users to skip for pagination|

> Example responses

> 200 Response

```json
{
  "data": [
    {
      "id": "123e4567-e89b-12d3-a456-426614174000",
      "email": "john.doe@example.com",
      "name": "John Doe",
      "role": "user",
      "createdAt": "2024-01-15T09:30:00Z",
      "updatedAt": "2024-01-20T14:45:00Z"
    }
  ],
  "total": 0
}
```

<h3 id="list-users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of users|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication required|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[Error](#schemaerror)|

<h3 id="list-users-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» data|[[User](#schemauser)]|false|none|none|
|»» id|string(uuid)|true|none|Unique identifier for the user|
|»» email|string(email)|true|none|User's email address|
|»» name|string|true|none|User's full name|
|»» role|string|true|none|User's role in the system|
|»» createdAt|string(date-time)|true|none|Timestamp when the user was created|
|»» updatedAt|string(date-time)|true|none|Timestamp when the user was last updated|
|» total|integer|false|none|Total number of users|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|user|
|role|guest|

<aside class="success">
This operation does not require authentication
</aside>

## Create User

<a id="opIdcreateUser"></a>

> Code samples

```shell title="Shell"
# You can also use wget
curl -X POST https://api.example.com/v1/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http title="HTTP"
POST https://api.example.com/v1/users HTTP/1.1
Host: api.example.com
Content-Type: application/json
Accept: application/json

```

```javascript title="JavaScript"
const inputBody = '{
  "email": "john.doe@example.com",
  "name": "John Doe",
  "password": "securePassword123",
  "role": "user"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://api.example.com/v1/users',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby title="Ruby"
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.example.com/v1/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python title="Python"
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('https://api.example.com/v1/users', headers = headers)

print(r.json())

```

```php title="PHP"
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.example.com/v1/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java title="Java"
URL obj = new URL("https://api.example.com/v1/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go title="Go"
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.example.com/v1/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /users`

Create a new user account.

> Body parameter

```json
{
  "email": "john.doe@example.com",
  "name": "John Doe",
  "password": "securePassword123",
  "role": "user"
}
```

<h3 id="create-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserCreate](#schemausercreate)|true|none|

> Example responses

> 201 Response

```json
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "email": "john.doe@example.com",
  "name": "John Doe",
  "role": "user",
  "createdAt": "2024-01-15T09:30:00Z",
  "updatedAt": "2024-01-20T14:45:00Z"
}
```

<h3 id="create-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|User created successfully|[User](#schemauser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request body or parameters|[Error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication required|[Error](#schemaerror)|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|User with this email already exists|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Get User

<a id="opIdgetUser"></a>

> Code samples

```shell title="Shell"
# You can also use wget
curl -X GET https://api.example.com/v1/users/{id} \
  -H 'Accept: application/json'

```

```http title="HTTP"
GET https://api.example.com/v1/users/{id} HTTP/1.1
Host: api.example.com
Accept: application/json

```

```javascript title="JavaScript"

const headers = {
  'Accept':'application/json'
};

fetch('https://api.example.com/v1/users/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby title="Ruby"
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.example.com/v1/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python title="Python"
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.example.com/v1/users/{id}', headers = headers)

print(r.json())

```

```php title="PHP"
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.example.com/v1/users/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java title="Java"
URL obj = new URL("https://api.example.com/v1/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go title="Go"
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.example.com/v1/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users/{id}`

Retrieve a specific user by their ID.

<h3 id="get-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|Unique identifier of the user|

> Example responses

> 200 Response

```json
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "email": "john.doe@example.com",
  "name": "John Doe",
  "role": "user",
  "createdAt": "2024-01-15T09:30:00Z",
  "updatedAt": "2024-01-20T14:45:00Z"
}
```

<h3 id="get-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|User details|[User](#schemauser)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication required|[Error](#schemaerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource not found|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Update User

<a id="opIdupdateUser"></a>

> Code samples

```shell title="Shell"
# You can also use wget
curl -X PUT https://api.example.com/v1/users/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http title="HTTP"
PUT https://api.example.com/v1/users/{id} HTTP/1.1
Host: api.example.com
Content-Type: application/json
Accept: application/json

```

```javascript title="JavaScript"
const inputBody = '{
  "email": "john.doe@example.com",
  "name": "John Doe",
  "role": "user"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('https://api.example.com/v1/users/{id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby title="Ruby"
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'https://api.example.com/v1/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python title="Python"
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('https://api.example.com/v1/users/{id}', headers = headers)

print(r.json())

```

```php title="PHP"
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','https://api.example.com/v1/users/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java title="Java"
URL obj = new URL("https://api.example.com/v1/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go title="Go"
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://api.example.com/v1/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /users/{id}`

Update an existing user's information.

> Body parameter

```json
{
  "email": "john.doe@example.com",
  "name": "John Doe",
  "role": "user"
}
```

<h3 id="update-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|Unique identifier of the user|
|body|body|[UserUpdate](#schemauserupdate)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "email": "john.doe@example.com",
  "name": "John Doe",
  "role": "user",
  "createdAt": "2024-01-15T09:30:00Z",
  "updatedAt": "2024-01-20T14:45:00Z"
}
```

<h3 id="update-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|User updated successfully|[User](#schemauser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request body or parameters|[Error](#schemaerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication required|[Error](#schemaerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource not found|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Delete User

<a id="opIddeleteUser"></a>

> Code samples

```shell title="Shell"
# You can also use wget
curl -X DELETE https://api.example.com/v1/users/{id} \
  -H 'Accept: application/json'

```

```http title="HTTP"
DELETE https://api.example.com/v1/users/{id} HTTP/1.1
Host: api.example.com
Accept: application/json

```

```javascript title="JavaScript"

const headers = {
  'Accept':'application/json'
};

fetch('https://api.example.com/v1/users/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby title="Ruby"
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'https://api.example.com/v1/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python title="Python"
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('https://api.example.com/v1/users/{id}', headers = headers)

print(r.json())

```

```php title="PHP"
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','https://api.example.com/v1/users/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java title="Java"
URL obj = new URL("https://api.example.com/v1/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go title="Go"
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.example.com/v1/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /users/{id}`

Permanently delete a user account.

<h3 id="delete-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string(uuid)|true|Unique identifier of the user|

> Example responses

> 401 Response

```json
{
  "code": "VALIDATION_ERROR",
  "message": "The request body is invalid.",
  "details": [
    {
      "field": "string",
      "message": "string"
    }
  ]
}
```

<h3 id="delete-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|User deleted successfully|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication required|[Error](#schemaerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Resource not found|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "email": "john.doe@example.com",
  "name": "John Doe",
  "role": "user",
  "createdAt": "2024-01-15T09:30:00Z",
  "updatedAt": "2024-01-20T14:45:00Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|true|none|Unique identifier for the user|
|email|string(email)|true|none|User's email address|
|name|string|true|none|User's full name|
|role|string|true|none|User's role in the system|
|createdAt|string(date-time)|true|none|Timestamp when the user was created|
|updatedAt|string(date-time)|true|none|Timestamp when the user was last updated|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|user|
|role|guest|

<h2 id="tocS_UserCreate">UserCreate</h2>
<!-- backwards compatibility -->
<a id="schemausercreate"></a>
<a id="schema_UserCreate"></a>
<a id="tocSusercreate"></a>
<a id="tocsusercreate"></a>

```json
{
  "email": "john.doe@example.com",
  "name": "John Doe",
  "password": "securePassword123",
  "role": "user"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|none|User's email address|
|name|string|true|none|User's full name|
|password|string(password)|true|none|User's password (minimum 8 characters)|
|role|string|false|none|User's role in the system|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|user|
|role|guest|

<h2 id="tocS_UserUpdate">UserUpdate</h2>
<!-- backwards compatibility -->
<a id="schemauserupdate"></a>
<a id="schema_UserUpdate"></a>
<a id="tocSuserupdate"></a>
<a id="tocsuserupdate"></a>

```json
{
  "email": "john.doe@example.com",
  "name": "John Doe",
  "role": "user"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|false|none|User's email address|
|name|string|false|none|User's full name|
|role|string|false|none|User's role in the system|

#### Enumerated Values

|Property|Value|
|---|---|
|role|admin|
|role|user|
|role|guest|

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "code": "VALIDATION_ERROR",
  "message": "The request body is invalid.",
  "details": [
    {
      "field": "string",
      "message": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|true|none|Error code|
|message|string|true|none|Human-readable error message|
|details|[object]|false|none|none|
|» field|string|false|none|Field that caused the error|
|» message|string|false|none|Specific error for this field|


---
title: My Sample API v1.0.0

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="my-sample-api">My Sample API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

A sample API to demonstrate the documentation pipeline.

<h1 id="my-sample-api-default">Default</h1>

## Get Users

> Code samples

```shell title="Shell"
# You can also use wget
curl -X GET /users

```

```http title="HTTP"
GET /users HTTP/1.1

```

```javascript title="JavaScript"

fetch('/users',
{
  method: 'GET'

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

result = RestClient.get '/users',
  params: {
  }

p JSON.parse(result)

```

```python title="Python"
import requests

r = requests.get('/users')

print(r.json())

```

```php title="PHP"
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/users', array(
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
URL obj = new URL("/users");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users`

Retrieve a list of users.

<h3 id="get-users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A successful response.|None|

<aside class="success">
This operation does not require authentication
</aside>


---
title: collect resource usage in a home environment v0.0.0-semantic-release
language_tabs:
  - shell: curl
  - javascript: fetch
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="collect-resource-usage-in-a-home-environment">collect resource usage in a home environment v0.0.0-semantic-release</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="collect-resource-usage-in-a-home-environment-default">Default</h1>

## post__admin_stop

> Code samples

```shell
# You can also use wget
curl -X POST /admin/stop \
  -H 'Accept: application/text'

```

```javascript

const headers = {
  'Accept':'application/text'
};

fetch('/admin/stop',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /admin/stop`

Stop konsum server.

> Example responses

> 200 Response

<h3 id="post__admin_stop-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Progress message.|[TextOnlyMessage](#schematextonlymessage)|

<aside class="success">
This operation does not require authentication
</aside>

## post__admin_reload

> Code samples

```shell
# You can also use wget
curl -X POST /admin/reload \
  -H 'Accept: application/text'

```

```javascript

const headers = {
  'Accept':'application/text'
};

fetch('/admin/reload',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /admin/reload`

Reload konsum systemd config.

> Example responses

> 200 Response

<h3 id="post__admin_reload-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Progress message.|[TextOnlyMessage](#schematextonlymessage)|

<aside class="success">
This operation does not require authentication
</aside>

## get__admin_backup

> Code samples

```shell
# You can also use wget
curl -X GET /admin/backup \
  -H 'Accept: application/text'

```

```javascript

const headers = {
  'Accept':'application/text'
};

fetch('/admin/backup',
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

`GET /admin/backup`

Create backup.

> Example responses

> 200 Response

<h3 id="get__admin_backup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Backup data as text.|[TextOnlyMessage](#schematextonlymessage)|

<aside class="success">
This operation does not require authentication
</aside>

## get__state

> Code samples

```shell
# You can also use wget
curl -X GET /state \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/state',
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

`GET /state`

Retrieve application state.

> Example responses

> 200 Response

```json
[
  {
    "version": "string",
    "uptime": 0,
    "memory": {}
  }
]
```

<h3 id="get__state-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Server status.|Inline|

<h3 id="get__state-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» version|string|false|none|The software version of the server.|
|» uptime|number|false|none|The duration the sever is up and running.|
|» memory|object|false|none|The memory usage of the server.|

<aside class="success">
This operation does not require authentication
</aside>

## post__authenticate

> Code samples

```shell
# You can also use wget
curl -X POST /authenticate \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```javascript
const inputBody = '{
  "username": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/authenticate',
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

`POST /authenticate`

Login to request api token.

> Body parameter

```json
{
  "username": "string",
  "password": "string"
}
```

<h3 id="post__authenticate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AuthRequest](#schemaauthrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "access_token": "string",
  "refresh_token": "string"
}
```

> 401 Response

<h3 id="post__authenticate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Token generated.|[AuthResponse](#schemaauthresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed.|[TextOnlyMessage](#schematextonlymessage)|

<aside class="success">
This operation does not require authentication
</aside>

## tags__category

> Code samples

```shell
# You can also use wget
curl -X TAGS /category

```

```javascript

fetch('/category',
{
  method: 'TAGS'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`TAGS /category`

<h3 id="tags__category-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|

<aside class="success">
This operation does not require authentication
</aside>

## operationId__category

> Code samples

```shell
# You can also use wget
curl -X OPERATIONID /category

```

```javascript

fetch('/category',
{
  method: 'OPERATIONID'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`OPERATIONID /category`

<h3 id="operationid__category-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|

<aside class="success">
This operation does not require authentication
</aside>

## get__category

> Code samples

```shell
# You can also use wget
curl -X GET /category \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category',
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

`GET /category`

> Example responses

> 200 Response

```json
[
  {
    "id": "EV",
    "description": "mains power",
    "unit": "m3"
  }
]
```

<h3 id="get__category-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of categories.|Inline|

<h3 id="get__category-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Category](#schemacategory)]|false|none|none|
|» id|string|true|none|The id of the category.|
|» description|string|false|none|The human readable description of your category.|
|» unit|string|false|none|The physical measurment unit.|

<aside class="success">
This operation does not require authentication
</aside>

## security__category

> Code samples

```shell
# You can also use wget
curl -X SECURITY /category

```

```javascript

fetch('/category',
{
  method: 'SECURITY'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`SECURITY /category`

<h3 id="security__category-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|

<aside class="success">
This operation does not require authentication
</aside>

## put__category_{category}

> Code samples

```shell
# You can also use wget
curl -X PUT /category/{category} \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`PUT /category/{category}`

insert a new category

<h3 id="put__category_{category}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category that needs to be deleted|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="put__category_{category}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## security__category_{category}

> Code samples

```shell
# You can also use wget
curl -X SECURITY /category/{category}

```

```javascript

fetch('/category/{category}',
{
  method: 'SECURITY'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`SECURITY /category/{category}`

<h3 id="security__category_{category}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category that needs to be deleted|

<h3 id="security__category_{category}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|

<aside class="success">
This operation does not require authentication
</aside>

## delete__category_{category}

> Code samples

```shell
# You can also use wget
curl -X DELETE /category/{category} \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}',
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

`DELETE /category/{category}`

Delete a category.

<h3 id="delete__category_{category}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category that needs to be deleted|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="delete__category_{category}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success message.|[Message](#schemamessage)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|No such category error message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## get__category_{category}_value

> Code samples

```shell
# You can also use wget
curl -X GET /category/{category}/value \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/value',
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

`GET /category/{category}/value`

List values of a category.

<h3 id="get__category_{category}_value-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category from where the value bill deleted.|
|time|body|string|true|Time the value was present.|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="get__category_{category}_value-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Value list.|Inline|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Unsupported content-type.|None|

<h3 id="get__category_{category}_value-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Value](#schemavalue)]|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## post__category_{category}_value

> Code samples

```shell
# You can also use wget
curl -X POST /category/{category}/value \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/value',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /category/{category}/value`

Insert a value into a category.

<h3 id="post__category_{category}_value-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category from where the value bill deleted.|
|time|body|string|true|Time the value was present.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="post__category_{category}_value-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## delete__category_{category}_value

> Code samples

```shell
# You can also use wget
curl -X DELETE /category/{category}/value \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/value',
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

`DELETE /category/{category}/value`

Delete a value from a category.

<h3 id="delete__category_{category}_value-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category from where the value bill deleted.|
|time|body|string|true|Time the value was present.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="delete__category_{category}_value-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## get__category_{category}_meter

> Code samples

```shell
# You can also use wget
curl -X GET /category/{category}/meter \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/meter',
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

`GET /category/{category}/meter`

List meters of a category.

<h3 id="get__category_{category}_meter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category the meter belongs to.|
|mater|path|string|true|ID of meter to be deleted.|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "description": "string",
    "unit": "string",
    "serial": "string"
  }
]
```

<h3 id="get__category_{category}_meter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of meters.|Inline|

<h3 id="get__category_{category}_meter-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Meter](#schemameter)]|false|none|none|
|» id|string|true|none|The id of the meter.|
|» description|string|false|none|The human readable description of your meter.|
|» unit|string|false|none|The physical measurment unit.|
|» serial|string|false|none|The serial number of the meter.|

<aside class="success">
This operation does not require authentication
</aside>

## put__category_{category}_meter

> Code samples

```shell
# You can also use wget
curl -X PUT /category/{category}/meter \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/meter',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`PUT /category/{category}/meter`

Add a meter to a category.

<h3 id="put__category_{category}_meter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category the meter belongs to.|
|mater|path|string|true|ID of meter to be deleted.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="put__category_{category}_meter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## post__category_{category}_meter

> Code samples

```shell
# You can also use wget
curl -X POST /category/{category}/meter \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/meter',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /category/{category}/meter`

Update a meter.

<h3 id="post__category_{category}_meter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category the meter belongs to.|
|mater|path|string|true|ID of meter to be deleted.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="post__category_{category}_meter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## delete__category_{category}_meter

> Code samples

```shell
# You can also use wget
curl -X DELETE /category/{category}/meter \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/meter',
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

`DELETE /category/{category}/meter`

Delete a meter.

<h3 id="delete__category_{category}_meter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category the meter belongs to.|
|mater|path|string|true|ID of meter to be deleted.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="delete__category_{category}_meter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## get__category_{category}_note

> Code samples

```shell
# You can also use wget
curl -X GET /category/{category}/note \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/note',
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

`GET /category/{category}/note`

List notes of a category.

<h3 id="get__category_{category}_note-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category to note belongs to.|
|note|path|string|true|ID of note to be deleted.|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="get__category_{category}_note-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of notes.|Inline|

<h3 id="get__category_{category}_note-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Note](#schemanote)]|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## put__category_{category}_note

> Code samples

```shell
# You can also use wget
curl -X PUT /category/{category}/note \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/note',
{
  method: 'PUT',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`PUT /category/{category}/note`

add a note to a category.

<h3 id="put__category_{category}_note-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category to note belongs to.|
|note|path|string|true|ID of note to be deleted.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="put__category_{category}_note-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## post__category_{category}_note

> Code samples

```shell
# You can also use wget
curl -X POST /category/{category}/note \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/note',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /category/{category}/note`

Update a note.

<h3 id="post__category_{category}_note-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category to note belongs to.|
|note|path|string|true|ID of note to be deleted.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="post__category_{category}_note-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

## delete__category_{category}_note

> Code samples

```shell
# You can also use wget
curl -X DELETE /category/{category}/note \
  -H 'Accept: application/json'

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/category/{category}/note',
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

`DELETE /category/{category}/note`

Delete a note.

<h3 id="delete__category_{category}_note-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|category|path|string|true|ID of category to note belongs to.|
|note|path|string|true|ID of note to be deleted.|

> Example responses

> 200 Response

```json
{
  "message": "string"
}
```

<h3 id="delete__category_{category}_note-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success message.|[Message](#schemamessage)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Category">Category</h2>
<!-- backwards compatibility -->
<a id="schemacategory"></a>
<a id="schema_Category"></a>
<a id="tocScategory"></a>
<a id="tocscategory"></a>

```json
{
  "id": "EV",
  "description": "mains power",
  "unit": "m3"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|The id of the category.|
|description|string|false|none|The human readable description of your category.|
|unit|string|false|none|The physical measurment unit.|

<h2 id="tocS_Meter">Meter</h2>
<!-- backwards compatibility -->
<a id="schemameter"></a>
<a id="schema_Meter"></a>
<a id="tocSmeter"></a>
<a id="tocsmeter"></a>

```json
{
  "id": "string",
  "description": "string",
  "unit": "string",
  "serial": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|The id of the meter.|
|description|string|false|none|The human readable description of your meter.|
|unit|string|false|none|The physical measurment unit.|
|serial|string|false|none|The serial number of the meter.|

<h2 id="tocS_Note">Note</h2>
<!-- backwards compatibility -->
<a id="schemanote"></a>
<a id="schema_Note"></a>
<a id="tocSnote"></a>
<a id="tocsnote"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_Value">Value</h2>
<!-- backwards compatibility -->
<a id="schemavalue"></a>
<a id="schema_Value"></a>
<a id="tocSvalue"></a>
<a id="tocsvalue"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_State">State</h2>
<!-- backwards compatibility -->
<a id="schemastate"></a>
<a id="schema_State"></a>
<a id="tocSstate"></a>
<a id="tocsstate"></a>

```json
{
  "version": "string",
  "uptime": 0,
  "memory": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|version|string|false|none|The software version of the server.|
|uptime|number|false|none|The duration the sever is up and running.|
|memory|object|false|none|The memory usage of the server.|

<h2 id="tocS_AuthRequest">AuthRequest</h2>
<!-- backwards compatibility -->
<a id="schemaauthrequest"></a>
<a id="schema_AuthRequest"></a>
<a id="tocSauthrequest"></a>
<a id="tocsauthrequest"></a>

```json
{
  "username": "string",
  "password": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|password|string|false|none|none|

<h2 id="tocS_AuthResponse">AuthResponse</h2>
<!-- backwards compatibility -->
<a id="schemaauthresponse"></a>
<a id="schema_AuthResponse"></a>
<a id="tocSauthresponse"></a>
<a id="tocsauthresponse"></a>

```json
{
  "access_token": "string",
  "refresh_token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|access_token|string|false|none|none|
|refresh_token|string|false|none|none|

<h2 id="tocS_Message">Message</h2>
<!-- backwards compatibility -->
<a id="schemamessage"></a>
<a id="schema_Message"></a>
<a id="tocSmessage"></a>
<a id="tocsmessage"></a>

```json
{
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|

<h2 id="tocS_TextOnlyMessage">TextOnlyMessage</h2>
<!-- backwards compatibility -->
<a id="schematextonlymessage"></a>
<a id="schema_TextOnlyMessage"></a>
<a id="tocStextonlymessage"></a>
<a id="tocstextonlymessage"></a>

```json
"string"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|


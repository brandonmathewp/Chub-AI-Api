<!-- Generator: Widdershins v4.0.1 -->

<h1 id="rostro-api">Rostro API v0.5.9</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Rostro endpoints. For use as an OpenAI mimic, use the URL: 'https://api.rostro.dev/v1'. For use as an MCP server, use the URL: 'https://proto.rostro.dev/mcp'.

<a href="https://rostro.dev/tos">Terms of service</a>
Email: <a href="mailto:support@rostro.dev">Support</a> 

# Authentication

* API Key (Authorization)
    - Parameter Name: **Authorization**, in: header. 

<h1 id="rostro-api-default">Default</h1>

## Do Internal Search

<a id="opIdsearch_projects"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/search', headers = headers)

print(r.json())

```

`GET /search`

<h3 id="do-internal-search-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|any|false|Full-text search of definitions.|
|exact_search|query|any|false|Full-text exact search of definitions.|
|name_like|query|any|false|Simple name search.|
|first|query|integer|false|The number of the results to get per page.|
|min_users_chatted|query|any|false|The minimum number of users chatted with it.|
|tags|query|string|false|A comma-separated list of tags to include. Example: 'OC,CAI'|
|exclude_tags|query|string|false|A comma-separated list of tags to exclude. Example: 'NSFL,Furry'|
|page|query|integer|false|The page number of the results to get.|
|sort|query|undefined|false|The field to sort by.|
|asc|query|boolean|false|Whether to sort ascending (True) or descending (False).|
|include_forks|query|boolean|false|Whether to return forks or only root items.|
|nsfw|query|boolean|false|Whether to include NSFW items in the result.|
|nsfl|query|boolean|false|Whether to include NSFL items in the result. (Excluding NSFW also excludes NSFW, so this is typically unnecessary.)|
|nsfw_only|query|boolean|false|Whether to include only NSFW items in the result.|
|require_images|query|boolean|false|Whether to exclude results without usage gallery images.|
|require_example_dialogues|query|boolean|false|Whether to exclude results without example dialogues.|
|require_alternate_greetings|query|boolean|false|Whether to exclude results without alternate greetings.|
|require_custom_prompt|query|boolean|false|Whether to exclude results without a custom main/NSFW prompt.|
|max_days_ago|query|any|false|The maximum age in days of the log.|
|exclude_mine|query|boolean|false|Whether to exclude your private and unlisted projects.|
|only_mine|query|any|false|Whether to only get your projects.|
|min_tokens|query|any|false|The minimum token count.|
|max_tokens|query|any|false|The maximum token count.|
|require_expressions|query|boolean|false|Whether to require an expression pack.|
|require_lore|query|boolean|false|Whether to require either an embedded or linked lorebook.|
|mine_first|query|any|false|Whether to return your projects and your liked projects first.|
|require_lore_embedded|query|boolean|false|Whether to require either an embedded lorebook.|
|require_lore_linked|query|boolean|false|Whether to require either a linked lorebook.|
|my_favorites|query|any|false|Whether to only return items you have favorited.|
|topics|query|string|false|A comma-separated list of tags to include. Example: 'OC,CAI'|
|excludetopics|query|string|false|A comma-separated list of tags to exclude. Example: 'NSFL,Furry'|
|special_mode|query|any|false|none|
|creator_id|query|any|false|The creator id to filter by.|
|namespace|query|any|false|none|
|username|query|any|false|none|
|inclusive_or|query|any|false|If asking for multiple tags, whether to return matches for ANY (True) or ALL (False) tags given.|
|recommended_verified|query|any|false|Whether to only return recommended and verified projects.|
|min_tags|query|any|false|Exclude results with less than this many tags.|
|count|query|any|false|Whether to return the total count or not.|
|min_ai_rating|query|any|false|Optional. Minimum rating of the card.|
|language|query|any|false|If included, only returns cards in this language.|
|cursor|query|any|false|Pagination cursor.|
|max_messages|query|any|false|The maximum number of messages.|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="do-internal-search-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="do-internal-search-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Do Internal Search Bypass

<a id="opIddo_internal_search_bypass_search_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/search', headers = headers)

print(r.json())

```

`POST /search`

<h3 id="do-internal-search-bypass-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|any|false|Full-text search of definitions.|
|exact_search|query|any|false|Full-text exact search of definitions.|
|name_like|query|any|false|Simple name search.|
|first|query|integer|false|The number of the results to get per page.|
|min_users_chatted|query|any|false|The minimum number of users chatted with it.|
|tags|query|string|false|A comma-separated list of tags to include. Example: 'OC,CAI'|
|exclude_tags|query|string|false|A comma-separated list of tags to exclude. Example: 'NSFL,Furry'|
|page|query|integer|false|The page number of the results to get.|
|sort|query|undefined|false|The field to sort by.|
|asc|query|boolean|false|Whether to sort ascending (True) or descending (False).|
|include_forks|query|boolean|false|Whether to return forks or only root items.|
|nsfw|query|boolean|false|Whether to include NSFW items in the result.|
|nsfl|query|boolean|false|Whether to include NSFL items in the result. (Excluding NSFW also excludes NSFW, so this is typically unnecessary.)|
|nsfw_only|query|boolean|false|Whether to include only NSFW items in the result.|
|require_images|query|boolean|false|Whether to exclude results without usage gallery images.|
|require_example_dialogues|query|boolean|false|Whether to exclude results without example dialogues.|
|require_alternate_greetings|query|boolean|false|Whether to exclude results without alternate greetings.|
|require_custom_prompt|query|boolean|false|Whether to exclude results without a custom main/NSFW prompt.|
|max_days_ago|query|any|false|The maximum age in days of the log.|
|exclude_mine|query|boolean|false|Whether to exclude your private and unlisted projects.|
|only_mine|query|any|false|Whether to only get your projects.|
|min_tokens|query|any|false|The minimum token count.|
|max_tokens|query|any|false|The maximum token count.|
|require_expressions|query|boolean|false|Whether to require an expression pack.|
|require_lore|query|boolean|false|Whether to require either an embedded or linked lorebook.|
|mine_first|query|any|false|Whether to return your projects and your liked projects first.|
|require_lore_embedded|query|boolean|false|Whether to require either an embedded lorebook.|
|require_lore_linked|query|boolean|false|Whether to require either a linked lorebook.|
|my_favorites|query|any|false|Whether to only return items you have favorited.|
|topics|query|string|false|A comma-separated list of tags to include. Example: 'OC,CAI'|
|excludetopics|query|string|false|A comma-separated list of tags to exclude. Example: 'NSFL,Furry'|
|special_mode|query|any|false|none|
|creator_id|query|any|false|The creator id to filter by.|
|namespace|query|any|false|none|
|username|query|any|false|none|
|inclusive_or|query|any|false|If asking for multiple tags, whether to return matches for ANY (True) or ALL (False) tags given.|
|recommended_verified|query|any|false|Whether to only return recommended and verified projects.|
|min_tags|query|any|false|Exclude results with less than this many tags.|
|count|query|any|false|Whether to return the total count or not.|
|min_ai_rating|query|any|false|Optional. Minimum rating of the card.|
|language|query|any|false|If included, only returns cards in this language.|
|cursor|query|any|false|Pagination cursor.|
|max_messages|query|any|false|The maximum number of messages.|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="do-internal-search-bypass-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="do-internal-search-bypass-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## A quick search just by names.

<a id="opIdperform_miniature_search_minisearch_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/minisearch', headers = headers)

print(r.json())

```

`POST /minisearch`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="a-quick-search-just-by-names.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="a-quick-search-just-by-names.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upload a video or animation.

<a id="opIdupload_animation_api_media_video_upload_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('/api/media/video/upload', headers = headers)

print(r.json())

```

`POST /api/media/video/upload`

> Body parameter

```yaml
false

```

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "queue_length": 0,
  "primary_character_id": 0,
  "secondary_character_ids": [],
  "lorebook_id": 0,
  "primary_image_path": "",
  "user_owned": false,
  "nsfw_image": false,
  "description": "string",
  "prompt": {},
  "is_published": false,
  "comments_enabled": true,
  "is_done": true,
  "is_failed": false,
  "parent_image": "string",
  "item_id": "string",
  "uuid": "string",
  "info": {
    "width": 0,
    "height": 0,
    "dpi": 0,
    "z_index": 0,
    "opacity": 100,
    "duration": 0,
    "visible": true,
    "locked": false,
    "start_time": 0,
    "end_time": 0,
    "in_point": 0,
    "out_point": 0,
    "effects": {},
    "children": [
      null
    ]
  },
  "name": "string",
  "preview": "string"
}
```

<h3 id="upload-a-video-or-animation.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[GalleryItem](#schemagalleryitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## A quick extension fetch.

<a id="opIdget_ext_fetch_minifetch_extension__extension_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/minifetch/extension/{extension_id}', headers = headers)

print(r.json())

```

`POST /minifetch/extension/{extension_id}`

<h3 id="a-quick-extension-fetch.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|extension_id|path|string|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="a-quick-extension-fetch.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="a-quick-extension-fetch.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## A quick extensions fetch.

<a id="opIdget_exts_fetch_minifetch_extensions__extension_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/minifetch/extensions/{extension_id}', headers = headers)

print(r.json())

```

`POST /minifetch/extensions/{extension_id}`

<h3 id="a-quick-extensions-fetch.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|extension_id|path|string|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="a-quick-extensions-fetch.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="a-quick-extensions-fetch.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get an existing imagine project or image.

<a id="opIdfetch_imagine_project_imagine_project__uuid__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/imagine/project/{uuid}', headers = headers)

print(r.json())

```

`GET /imagine/project/{uuid}`

<h3 id="get-an-existing-imagine-project-or-image.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="get-an-existing-imagine-project-or-image.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="get-an-existing-imagine-project-or-image.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetch Project

<a id="opIdfetch_project_api_public__namespace___creator_name___project_name__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/public/{namespace}/{creator_name}/{project_name}', headers = headers)

print(r.json())

```

`GET /api/public/{namespace}/{creator_name}/{project_name}`

<h3 id="fetch-project-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|namespace|path|undefined|true|none|
|creator_name|path|string|true|none|
|project_name|path|string|true|none|
|full|query|boolean|false|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="fetch-project-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="fetch-project-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetch Character Id

<a id="opIdfetch_character_id_api_public__space___project_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/public/{space}/{project_id}', headers = headers)

print(r.json())

```

`GET /api/public/{space}/{project_id}`

<h3 id="fetch-character-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|space|path|undefined|true|none|
|project_id|path|integer|true|none|
|full|query|boolean|false|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="fetch-character-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="fetch-character-id-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## App Create

<a id="opIdapp_create_engine_api_apps_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/apps', headers = headers)

print(r.json())

```

`POST /engine/api/apps`

> Body parameter

```json
{}
```

<h3 id="app-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="app-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="app-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## App List

<a id="opIdapp_list_engine_api_apps_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/apps', headers = headers)

print(r.json())

```

`GET /engine/api/apps`

<h3 id="app-list-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tags|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="app-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="app-list-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## App Delete

<a id="opIdapp_delete_engine_api_apps__app_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/apps/{app_id}', headers = headers)

print(r.json())

```

`DELETE /engine/api/apps/{app_id}`

<h3 id="app-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|app_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="app-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="app-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## App Get

<a id="opIdapp_get_engine_api_apps__app_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/apps/{app_id}', headers = headers)

print(r.json())

```

`GET /engine/api/apps/{app_id}`

<h3 id="app-get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|app_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="app-get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="app-get-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## App Download

<a id="opIdapp_download_engine_api_apps_download_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/apps/download', headers = headers)

print(r.json())

```

`POST /engine/api/apps/download`

> Body parameter

```json
{}
```

<h3 id="app-download-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="app-download-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="app-download-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Assets List

<a id="opIdassets_list_engine_api_assets_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/assets', headers = headers)

print(r.json())

```

`GET /engine/api/assets`

<h3 id="assets-list-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|any|false|none|
|regex|query|any|false|none|
|sort|query|any|false|none|
|order|query|any|false|none|
|skip|query|any|false|none|
|limit|query|any|false|none|
|tags|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="assets-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="assets-list-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Create

<a id="opIdasset_create_engine_api_assets_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/assets', headers = headers)

print(r.json())

```

`POST /engine/api/assets`

> Body parameter

```yaml
false

```

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Delete

<a id="opIdasset_delete_engine_api_assets_delete"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/assets', headers = headers)

print(r.json())

```

`DELETE /engine/api/assets`

> Body parameter

```json
[
  "string"
]
```

<h3 id="asset-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|branchId|query|any|false|none|
|body|body|array[string]|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Get

<a id="opIdasset_get_engine_api_assets__asset_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/assets/{asset_id}', headers = headers)

print(r.json())

```

`GET /engine/api/assets/{asset_id}`

<h3 id="asset-get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-get-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Update

<a id="opIdasset_update_engine_api_assets__asset_id__put"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.put('/engine/api/assets/{asset_id}', headers = headers)

print(r.json())

```

`PUT /engine/api/assets/{asset_id}`

> Body parameter

```yaml
false

```

<h3 id="asset-update-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-update-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Get File

<a id="opIdasset_get_file_engine_api_assets__asset_id__file__filename__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/assets/{asset_id}/file/{filename}', headers = headers)

print(r.json())

```

`GET /engine/api/assets/{asset_id}/file/{filename}`

<h3 id="asset-get-file-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset_id|path|string|true|none|
|filename|path|string|true|none|
|branchId|query|any|false|none|
|immutableBackup|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-get-file-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-get-file-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Get Thumbnail

<a id="opIdasset_get_thumbnail_engine_api_assets__asset_id__thumbnail__size__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/assets/{asset_id}/thumbnail/{size}', headers = headers)

print(r.json())

```

`GET /engine/api/assets/{asset_id}/thumbnail/{size}`

<h3 id="asset-get-thumbnail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset_id|path|string|true|none|
|size|path|string|true|none|
|branchId|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-get-thumbnail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-get-thumbnail-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Reimport

<a id="opIdasset_reimport_engine_api_assets__asset_id__reimport_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/assets/{asset_id}/reimport', headers = headers)

print(r.json())

```

`POST /engine/api/assets/{asset_id}/reimport`

> Body parameter

```json
{}
```

<h3 id="asset-reimport-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset_id|path|string|true|none|
|branchId|query|any|false|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-reimport-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-reimport-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Duplicate

<a id="opIdasset_duplicate_engine_api_assets__asset_id__duplicate_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/assets/{asset_id}/duplicate', headers = headers)

print(r.json())

```

`POST /engine/api/assets/{asset_id}/duplicate`

> Body parameter

```json
{}
```

<h3 id="asset-duplicate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-duplicate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-duplicate-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Asset Paste

<a id="opIdasset_paste_engine_api_assets_paste_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/assets/paste', headers = headers)

print(r.json())

```

`POST /engine/api/assets/paste`

> Body parameter

```json
{}
```

<h3 id="asset-paste-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="asset-paste-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="asset-paste-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Checkpoint Create

<a id="opIdcheckpoint_create_engine_api_checkpoints_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/checkpoints', headers = headers)

print(r.json())

```

`POST /engine/api/checkpoints`

> Body parameter

```json
{}
```

<h3 id="checkpoint-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="checkpoint-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="checkpoint-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Checkpoint Get

<a id="opIdcheckpoint_get_engine_api_checkpoints__checkpoint_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/checkpoints/{checkpoint_id}', headers = headers)

print(r.json())

```

`GET /engine/api/checkpoints/{checkpoint_id}`

<h3 id="checkpoint-get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|checkpoint_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="checkpoint-get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="checkpoint-get-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Checkpoint Restore

<a id="opIdcheckpoint_restore_engine_api_checkpoints__checkpoint_id__restore_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/checkpoints/{checkpoint_id}/restore', headers = headers)

print(r.json())

```

`POST /engine/api/checkpoints/{checkpoint_id}/restore`

> Body parameter

```json
{}
```

<h3 id="checkpoint-restore-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|checkpoint_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="checkpoint-restore-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="checkpoint-restore-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Checkpoint Hard Reset

<a id="opIdcheckpoint_hard_reset_engine_api_checkpoints__checkpoint_id__hardreset_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/checkpoints/{checkpoint_id}/hardreset', headers = headers)

print(r.json())

```

`POST /engine/api/checkpoints/{checkpoint_id}/hardreset`

> Body parameter

```json
{}
```

<h3 id="checkpoint-hard-reset-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|checkpoint_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="checkpoint-hard-reset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="checkpoint-hard-reset-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Entities List

<a id="opIdentities_list_engine_api_entities_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/entities', headers = headers)

print(r.json())

```

`GET /engine/api/entities`

> Example responses

> 200 Response

```json
null
```

<h3 id="entities-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|

<h3 id="entities-list-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Entity Create

<a id="opIdentity_create_engine_api_entities_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/entities', headers = headers)

print(r.json())

```

`POST /engine/api/entities`

> Body parameter

```json
{}
```

<h3 id="entity-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="entity-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="entity-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Entity Get

<a id="opIdentity_get_engine_api_entities__entity_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/entities/{entity_id}', headers = headers)

print(r.json())

```

`GET /engine/api/entities/{entity_id}`

<h3 id="entity-get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|entity_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="entity-get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="entity-get-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Entity Update

<a id="opIdentity_update_engine_api_entities__entity_id__put"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/engine/api/entities/{entity_id}', headers = headers)

print(r.json())

```

`PUT /engine/api/entities/{entity_id}`

> Body parameter

```json
{}
```

<h3 id="entity-update-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|entity_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="entity-update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="entity-update-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Entity Delete

<a id="opIdentity_delete_engine_api_entities__entity_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/entities/{entity_id}', headers = headers)

print(r.json())

```

`DELETE /engine/api/entities/{entity_id}`

<h3 id="entity-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|entity_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="entity-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="entity-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Home Branch

<a id="opIdhome_branch_engine_api_editor_project__project_id__branch_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/editor/project/{project_id}/branch', headers = headers)

print(r.json())

```

`GET /engine/api/editor/project/{project_id}/branch`

<h3 id="home-branch-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="home-branch-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="home-branch-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Home File

<a id="opIdhome_file_engine_api_file_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/file', params={
  'url': 'string'
}, headers = headers)

print(r.json())

```

`GET /engine/api/file`

<h3 id="home-file-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|url|query|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="home-file-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="home-file-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Home Scene Opened

<a id="opIdhome_scene_opened_engine_api_editor_scene__scene_id__opened_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/engine/api/editor/scene/{scene_id}/opened', headers = headers)

print(r.json())

```

`POST /engine/api/editor/scene/{scene_id}/opened`

<h3 id="home-scene-opened-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|scene_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="home-scene-opened-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="home-scene-opened-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Home Scene Event

<a id="opIdhome_scene_event_engine_api_editor_scene__scene_id__events_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/editor/scene/{scene_id}/events', headers = headers)

print(r.json())

```

`POST /engine/api/editor/scene/{scene_id}/events`

> Body parameter

```json
{}
```

<h3 id="home-scene-event-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|scene_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="home-scene-event-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="home-scene-event-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Home Scene Tip

<a id="opIdhome_scene_tip_engine_api_editor_scene__scene_id__tips__tip__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/engine/api/editor/scene/{scene_id}/tips/{tip}', headers = headers)

print(r.json())

```

`POST /engine/api/editor/scene/{scene_id}/tips/{tip}`

<h3 id="home-scene-tip-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|scene_id|path|string|true|none|
|tip|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="home-scene-tip-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="home-scene-tip-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Create

<a id="opIdproject_create_engine_api_projects_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects', headers = headers)

print(r.json())

```

`POST /engine/api/projects`

> Body parameter

```json
{}
```

<h3 id="project-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Update

<a id="opIdproject_update_engine_api_projects__project_id__put"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/engine/api/projects/{project_id}', headers = headers)

print(r.json())

```

`PUT /engine/api/projects/{project_id}`

> Body parameter

```json
{}
```

<h3 id="project-update-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-update-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Get

<a id="opIdproject_get_engine_api_projects__project_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}`

<h3 id="project-get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-get-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Delete

<a id="opIdproject_delete_engine_api_projects__project_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/projects/{project_id}', headers = headers)

print(r.json())

```

`DELETE /engine/api/projects/{project_id}`

<h3 id="project-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Import

<a id="opIdproject_import_engine_api_projects_import_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/import', headers = headers)

print(r.json())

```

`POST /engine/api/projects/import`

> Body parameter

```json
{}
```

<h3 id="project-import-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-import-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-import-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Export

<a id="opIdproject_export_engine_api_projects__project_id__export_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/{project_id}/export', headers = headers)

print(r.json())

```

`POST /engine/api/projects/{project_id}/export`

<h3 id="project-export-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-export-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-export-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Unlock

<a id="opIdproject_unlock_engine_api_projects__project_id__unlock_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/{project_id}/unlock', headers = headers)

print(r.json())

```

`POST /engine/api/projects/{project_id}/unlock`

<h3 id="project-unlock-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-unlock-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-unlock-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Transfer

<a id="opIdproject_transfer_engine_api_projects__project_id__transfer_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/{project_id}/transfer', headers = headers)

print(r.json())

```

`POST /engine/api/projects/{project_id}/transfer`

> Body parameter

```json
{}
```

<h3 id="project-transfer-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-transfer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-transfer-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Accept Transfer

<a id="opIdproject_accept_transfer_engine_api_projects__project_id__accept_transfer_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/{project_id}/accept_transfer', headers = headers)

print(r.json())

```

`POST /engine/api/projects/{project_id}/accept_transfer`

<h3 id="project-accept-transfer-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-accept-transfer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-accept-transfer-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Decline Transfer

<a id="opIdproject_decline_transfer_engine_api_projects__project_id__decline_transfer_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/{project_id}/decline_transfer', headers = headers)

print(r.json())

```

`POST /engine/api/projects/{project_id}/decline_transfer`

<h3 id="project-decline-transfer-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-decline-transfer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-decline-transfer-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Activity

<a id="opIdproject_activity_engine_api_projects__project_id__activity_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/activity', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/activity`

<h3 id="project-activity-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-activity-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-activity-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Collab List

<a id="opIdproject_collab_list_engine_api_projects__project_id__collaborators_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/collaborators', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/collaborators`

<h3 id="project-collab-list-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-collab-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-collab-list-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Collab Create

<a id="opIdproject_collab_create_engine_api_projects__project_id__collaborators_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/{project_id}/collaborators', headers = headers)

print(r.json())

```

`POST /engine/api/projects/{project_id}/collaborators`

> Body parameter

```json
{}
```

<h3 id="project-collab-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-collab-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-collab-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Collab Update

<a id="opIdproject_collab_update_engine_api_projects__project_id__collaborators__collab_id__put"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/engine/api/projects/{project_id}/collaborators/{collab_id}', headers = headers)

print(r.json())

```

`PUT /engine/api/projects/{project_id}/collaborators/{collab_id}`

> Body parameter

```json
{}
```

<h3 id="project-collab-update-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|collab_id|path|string|true|none|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-collab-update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-collab-update-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Collab Delete

<a id="opIdproject_collab_delete_engine_api_projects__project_id__collaborators__collab_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/projects/{project_id}/collaborators/{collab_id}', headers = headers)

print(r.json())

```

`DELETE /engine/api/projects/{project_id}/collaborators/{collab_id}`

<h3 id="project-collab-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|collab_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-collab-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-collab-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Image

<a id="opIdproject_image_engine_api_projects__project_id__image_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/projects/{project_id}/image', headers = headers)

print(r.json())

```

`POST /engine/api/projects/{project_id}/image`

> Body parameter

```yaml
false

```

<h3 id="project-image-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-image-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-image-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Assets

<a id="opIdproject_assets_engine_api_projects__project_id__assets_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/assets', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/assets`

<h3 id="project-assets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|branchId|query|any|false|none|
|view|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-assets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-assets-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Scenes

<a id="opIdproject_scenes_engine_api_projects__project_id__scenes_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/scenes', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/scenes`

<h3 id="project-scenes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|branchId|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-scenes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-scenes-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Branches

<a id="opIdproject_branches_engine_api_projects__project_id__branches_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/branches', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/branches`

<h3 id="project-branches-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|limit|query|any|false|none|
|skip|query|any|false|none|
|closed|query|any|false|none|
|favorite|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-branches-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-branches-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Apps

<a id="opIdproject_apps_engine_api_projects__project_id__apps_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/apps', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/apps`

<h3 id="project-apps-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|limit|query|any|false|none|
|skip|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-apps-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-apps-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Repo

<a id="opIdproject_repo_engine_api_projects__project_id__repositories_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/repositories', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/repositories`

<h3 id="project-repo-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-repo-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-repo-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Repo Sourcefiles List

<a id="opIdproject_repo_sourcefiles_list_engine_api_projects__project_id__repositories__repo_service__sourcefiles_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles`

<h3 id="project-repo-sourcefiles-list-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|repo_service|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-repo-sourcefiles-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-repo-sourcefiles-list-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Repo Sourcefile

<a id="opIdproject_repo_sourcefile_engine_api_projects__project_id__repositories__repo_service__sourcefiles__relative_path__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles/{relative_path}', headers = headers)

print(r.json())

```

`GET /engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles/{relative_path}`

<h3 id="project-repo-sourcefile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|repo_service|path|string|true|none|
|relative_path|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-repo-sourcefile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-repo-sourcefile-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Project Repo Sourcefiles Delete

<a id="opIdproject_repo_sourcefiles_delete_engine_api_projects__project_id__repositories__repo_service__sourcefiles__file_name__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles/{file_name}', headers = headers)

print(r.json())

```

`DELETE /engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles/{file_name}`

<h3 id="project-repo-sourcefiles-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|string|true|none|
|repo_service|path|string|true|none|
|file_name|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="project-repo-sourcefiles-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="project-repo-sourcefiles-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Scene Create

<a id="opIdscene_create_engine_api_scenes_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/scenes', headers = headers)

print(r.json())

```

`POST /engine/api/scenes`

> Body parameter

```json
{}
```

<h3 id="scene-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="scene-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="scene-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Scene Delete

<a id="opIdscene_delete_engine_api_scenes__scene_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/scenes/{scene_id}', headers = headers)

print(r.json())

```

`DELETE /engine/api/scenes/{scene_id}`

<h3 id="scene-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|scene_id|path|string|true|none|
|branchId|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="scene-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="scene-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Scene Get

<a id="opIdscene_get_engine_api_scenes__scene_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/scenes/{scene_id}', headers = headers)

print(r.json())

```

`GET /engine/api/scenes/{scene_id}`

<h3 id="scene-get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|scene_id|path|string|true|none|
|branchId|query|any|false|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="scene-get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="scene-get-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Edit Scene

<a id="opIdedit_scene_engine_api_editor_scene__scene_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/engine/api/editor/scene/{scene_id}', headers = headers)

print(r.json())

```

`GET /engine/api/editor/scene/{scene_id}`

<h3 id="edit-scene-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|scene_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="edit-scene-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="edit-scene-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upload Start

<a id="opIdupload_start_engine_api_upload_start_upload_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/upload/start-upload', headers = headers)

print(r.json())

```

`POST /engine/api/upload/start-upload`

> Body parameter

```json
{}
```

<h3 id="upload-start-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="upload-start-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="upload-start-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upload Urls

<a id="opIdupload_urls_engine_api_upload_signed_urls_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/upload/signed-urls', headers = headers)

print(r.json())

```

`POST /engine/api/upload/signed-urls`

> Body parameter

```json
{}
```

<h3 id="upload-urls-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="upload-urls-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="upload-urls-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upload Complete

<a id="opIdupload_complete_engine_api_upload_complete_upload_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/upload/complete-upload', headers = headers)

print(r.json())

```

`POST /engine/api/upload/complete-upload`

> Body parameter

```json
{}
```

<h3 id="upload-complete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="upload-complete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="upload-complete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Watch Create

<a id="opIdwatch_create_engine_api_watch_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/engine/api/watch', headers = headers)

print(r.json())

```

`POST /engine/api/watch`

> Body parameter

```json
{}
```

<h3 id="watch-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="watch-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="watch-create-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Watch Delete

<a id="opIdwatch_delete_engine_api_watch__watch_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/engine/api/watch/{watch_id}', headers = headers)

print(r.json())

```

`DELETE /engine/api/watch/{watch_id}`

<h3 id="watch-delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|watch_id|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="watch-delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="watch-delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-read-only">Read-Only</h1>

Endpoints for exploration and download of character and lorebook definitions. Does not require login.

## Get all tags with counts, optionally by namespace.

<a id="opIdget_all_tags_for_post_tags_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/tags', headers = headers)

print(r.json())

```

`POST /tags`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-all-tags-with-counts,-optionally-by-namespace.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-all-tags-with-counts,-optionally-by-namespace.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get the profile for this user.

<a id="opIdget_user_profile_api_users__username__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/users/{username}', headers = headers)

print(r.json())

```

`GET /api/users/{username}`

<h3 id="get-the-profile-for-this-user.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|
|nsfw|query|any|false|true or false.|
|nsfl|query|any|false|true or false.|
|exclude_mine|query|any|false|Whether to exclude your private and unlisted projects.|
|include_projects|query|any|false|Whether to also fetch their projects.|

> Example responses

> 200 Response

```json
null
```

<h3 id="get-the-profile-for-this-user.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="get-the-profile-for-this-user.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get the user leaderboard.

<a id="opIdget_leaderboard_api_leaderboard_v1_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/leaderboard/v1', headers = headers)

print(r.json())

```

`GET /api/leaderboard/v1`

<h3 id="get-the-user-leaderboard.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|order_by|query|undefined|false|The field to order by.|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-the-user-leaderboard.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-the-user-leaderboard.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get unstructured items for these owners.

<a id="opIdfetch_items_lore_items_get"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.get('/lore/items', headers = headers)

print(r.json())

```

`GET /lore/items`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-unstructured-items-for-these-owners.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-unstructured-items-for-these-owners.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get the ratings for this project.

<a id="opIdproject_ratings_api_project__project_id__ratings_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/project/{project_id}/ratings', headers = headers)

print(r.json())

```

`GET /api/project/{project_id}/ratings`

<h3 id="get-the-ratings-for-this-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-the-ratings-for-this-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-the-ratings-for-this-project.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get who a given username follows.

<a id="opIduser_follows_post_api_follows__username__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/follows/{username}', headers = headers)

print(r.json())

```

`GET /api/follows/{username}`

<h3 id="get-who-a-given-username-follows.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|
|page|query|integer|false|The page to return.|
|count|query|any|false|Whether to return the total count or not.|
|asc|query|any|false|Whether to sort ascending (True) or descending (False).|
|min_ai_rating|query|any|false|Optional. Minimum rating of the card.|
|nsfw|query|boolean|false|Whether to include NSFW items in the result.|
|nsfl|query|boolean|false|Whether to include NSFL items in the result. (Excluding NSFW also excludes NSFW, so this is typically unnecessary.)|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-who-a-given-username-follows.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-who-a-given-username-follows.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get who follows a given username.

<a id="opIduser_followers_api_followers__username__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/followers/{username}', headers = headers)

print(r.json())

```

`GET /api/followers/{username}`

<h3 id="get-who-follows-a-given-username.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|
|page|query|integer|false|The page to return.|
|count|query|any|false|Whether to return the total count or not.|
|asc|query|any|false|Whether to sort ascending (True) or descending (False).|
|min_ai_rating|query|any|false|Optional. Minimum rating of the card.|
|nsfw|query|boolean|false|Whether to include NSFW items in the result.|
|nsfl|query|boolean|false|Whether to include NSFL items in the result. (Excluding NSFW also excludes NSFW, so this is typically unnecessary.)|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-who-follows-a-given-username.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-who-follows-a-given-username.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get recent updates from people you follow.

<a id="opIdmy_timeline_api_timeline_v1_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/timeline/v1', headers = headers)

print(r.json())

```

`GET /api/timeline/v1`

<h3 id="get-recent-updates-from-people-you-follow.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|The page to return.|
|count|query|any|false|Whether to return the total count or not.|
|asc|query|any|false|Whether to sort ascending (True) or descending (False).|
|min_ai_rating|query|any|false|Optional. Minimum rating of the card.|
|nsfw|query|boolean|false|Whether to include NSFW items in the result.|
|nsfl|query|boolean|false|Whether to include NSFL items in the result. (Excluding NSFW also excludes NSFW, so this is typically unnecessary.)|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-recent-updates-from-people-you-follow.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-recent-updates-from-people-you-follow.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get the configured atproto for this username for Bluesky.

<a id="opIdget_bluesky_atproto__username__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/atproto/{username}', headers = headers)

print(r.json())

```

`GET /atproto/{username}`

<h3 id="get-the-configured-atproto-for-this-username-for-bluesky.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|

> Example responses

> 200 Response

```json
null
```

<h3 id="get-the-configured-atproto-for-this-username-for-bluesky.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|Inline|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<h3 id="get-the-configured-atproto-for-this-username-for-bluesky.-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## Get recommended projects for a project.

<a id="opIdsimilar_projects_api_projects_similar__project_id___no_nsfl_enum___no_nsfw_enum__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/projects/similar/{project_id}/{no_nsfl_enum}/{no_nsfw_enum}', headers = headers)

print(r.json())

```

`GET /api/projects/similar/{project_id}/{no_nsfl_enum}/{no_nsfw_enum}`

<h3 id="get-recommended-projects-for-a-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|no_nsfl_enum|path|undefined|true|none|
|no_nsfw_enum|path|undefined|true|none|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="get-recommended-projects-for-a-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get expression packs for the character.

<a id="opIdget_expressions_api_characters__project_id__expressions_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/characters/{project_id}/expressions', headers = headers)

print(r.json())

```

`GET /api/characters/{project_id}/expressions`

<h3 id="get-expression-packs-for-the-character.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-expression-packs-for-the-character.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-expression-packs-for-the-character.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get all badges.

<a id="opIdget_badges_api_badges_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/badges', headers = headers)

print(r.json())

```

`GET /api/badges`

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-all-badges.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-all-badges.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get a specific badge.

<a id="opIdget_badge_api_badges__badge_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/badges/{badge_id}', headers = headers)

print(r.json())

```

`GET /api/badges/{badge_id}`

<h3 id="get-a-specific-badge.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|badge_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-a-specific-badge.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-a-specific-badge.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get the comments on a log.

<a id="opIdcomments_log_api_logs__log_id__comments_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/logs/{log_id}/comments', headers = headers)

print(r.json())

```

`GET /api/logs/{log_id}/comments`

<h3 id="get-the-comments-on-a-log.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|log_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-the-comments-on-a-log.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-the-comments-on-a-log.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Search (or get all) public logs

<a id="opIdget_all_public_logs_api_logs_search_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/logs/search', headers = headers)

print(r.json())

```

`GET /api/logs/search`

Fetch public logs from the API with a given search query.

<h3 id="search-(or-get-all)-public-logs-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|first|query|integer|false|The number of the results to get per page.|
|page|query|integer|false|The page number of the results to get.|
|search|query|any|false|Search based on names, descriptions, et cetera.|
|max_days_ago|query|any|false|The maximum age in days of the log.|
|min_characters|query|any|false|The minimum number of characters.|
|username|query|any|false|What user to search for.|
|character_id|query|any|false|What character to search for.|
|sort|query|undefined|false|The field to sort by.|
|asc|query|boolean|false|Whether to sort ascending (True) or descending (False).|
|nsfw|query|boolean|false|Whether to include NSFW results.|
|nsfl|query|boolean|false|Whether to include NSFL results.|
|require_images|query|any|false|Whether to exclude results without usage gallery images.|
|full_text_search|query|any|false|Full-text search of logs (Not implemented yet).|
|topics|query|string|false|A comma-separated list of tags to include. Example: 'OC,CAI'. Not yet implemented.|
|excludetopics|query|string|false|A comma-separated list of tags to exclude. Example: 'NSFL,Furry'. Not yet implemented.|
|count|query|any|false|Whether to return the total count or not.|
|is_live|query|any|false|Whether to check for liveness.|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="search-(or-get-all)-public-logs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="search-(or-get-all)-public-logs-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-characters">Characters</h1>

Endpoints related to Characters.

## Upsert an expression pack for the character.

<a id="opIdupsert_expressions_api_characters__project_id__expressions_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/characters/{project_id}/expressions', headers = headers)

print(r.json())

```

`POST /api/characters/{project_id}/expressions`

> Body parameter

```json
false
```

<h3 id="upsert-an-expression-pack-for-the-character.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="upsert-an-expression-pack-for-the-character.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete an expression pack for the character.

<a id="opIddelete_expressions_api_characters__project_id__expressions__tagname__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/characters/{project_id}/expressions/{tagname}', headers = headers)

print(r.json())

```

`DELETE /api/characters/{project_id}/expressions/{tagname}`

<h3 id="delete-an-expression-pack-for-the-character.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|
|tagname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-an-expression-pack-for-the-character.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-public-logs">Public Logs</h1>

Endpoints related to public chat logs.

## Make or update a comment on a log.

<a id="opIdcomment_log_api_logs__log_id__comment_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/logs/{log_id}/comment', headers = headers)

print(r.json())

```

`POST /api/logs/{log_id}/comment`

> Body parameter

```json
false
```

<h3 id="make-or-update-a-comment-on-a-log.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|log_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="make-or-update-a-comment-on-a-log.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete a comment on a log.

<a id="opIduncomment_log_logs__log_id__comment__rid__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/logs/{log_id}/comment/{rid}', headers = headers)

print(r.json())

```

`DELETE /logs/{log_id}/comment/{rid}`

<h3 id="delete-a-comment-on-a-log.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|log_id|path|integer|true|none|
|rid|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-a-comment-on-a-log.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## React to a log.

<a id="opIdreact_log_reactions_react__rid__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/reactions/react/{rid}', headers = headers)

print(r.json())

```

`POST /reactions/react/{rid}`

<h3 id="react-to-a-log.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|rid|path|integer|true|none|
|target_type|query|integer|false|The target type. None or 1 = chat, 2 = GalleryItem, 3 is message, 4 is chat comment, 5 is rating.|
|target_id|query|any|false|The target ID. None if no target ID.|
|chat_id|query|any|false|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="react-to-a-log.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Unreact to a log.

<a id="opIdunreact_log_reactions_react__rid__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/reactions/react/{rid}', headers = headers)

print(r.json())

```

`DELETE /reactions/react/{rid}`

<h3 id="unreact-to-a-log.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|rid|path|integer|true|none|
|target_type|query|integer|false|The target type. None or 1 = chat, 2 = GalleryItem, 3 is message, 4 is chat comment, 5 is rating.|
|target_id|query|any|false|The target ID. None if no target ID.|
|chat_id|query|any|false|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="unreact-to-a-log.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-mimic">Mimic</h1>

Endpoints for the OpenAI Mimic API.

## OpenAI Mimic API endpoint for chat completions. Model selection will be ignored and overridden with the one from the path.

<a id="opIdother_chat_mimic__model__v1_chat_completions_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/{model}/v1/chat/completions', headers = headers)

print(r.json())

```

`POST /{model}/v1/chat/completions`

> Body parameter

```json
{
  "messages": [
    {
      "content": "string",
      "role": "developer",
      "name": "string"
    }
  ],
  "model": "string",
  "audio": {
    "format": "wav",
    "voice": "string"
  },
  "frequency_penalty": 0,
  "function_call": "none",
  "functions": [
    {
      "name": "string",
      "description": "string",
      "parameters": {}
    }
  ],
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": true,
  "max_completion_tokens": 0,
  "max_tokens": 0,
  "metadata": {
    "property1": "string",
    "property2": "string"
  },
  "modalities": [
    "text"
  ],
  "n": 0,
  "parallel_tool_calls": true,
  "prediction": {
    "content": "string",
    "type": "content"
  },
  "presence_penalty": 0,
  "reasoning_effort": "low",
  "response_format": {
    "type": "text"
  },
  "seed": 0,
  "service_tier": "auto",
  "stop": "string",
  "store": true,
  "stream_options": {
    "include_usage": true
  },
  "temperature": 0,
  "tool_choice": "none",
  "tools": [
    {
      "function": {
        "name": "string",
        "description": "string",
        "parameters": {},
        "strict": true
      },
      "type": "function"
    }
  ],
  "top_logprobs": 0,
  "top_p": 0,
  "user": "string",
  "web_search_options": {
    "search_context_size": "low",
    "user_location": {
      "approximate": {
        "city": "string",
        "country": "string",
        "region": "string",
        "timezone": "string"
      },
      "type": "approximate"
    }
  },
  "stream": false
}
```

<h3 id="openai-mimic-api-endpoint-for-chat-completions.-model-selection-will-be-ignored-and-overridden-with-the-one-from-the-path.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|model|path|undefined|true|none|
|body|body|any|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "choices": [],
  "created": 0,
  "model": "string",
  "object": "chat.completion",
  "service_tier": "auto",
  "system_fingerprint": "string",
  "usage": {}
}
```

<h3 id="openai-mimic-api-endpoint-for-chat-completions.-model-selection-will-be-ignored-and-overridden-with-the-one-from-the-path.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ChatCompletion](#schemachatcompletion)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## OpenAI Mimic API endpoint for completions. Model selection will be ignored and overridden with the one from the path.

<a id="opIdchat_mimic_other_generic__model__v1_completions_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/{model}/v1/completions', headers = headers)

print(r.json())

```

`POST /{model}/v1/completions`

> Body parameter

```json
{
  "model": "string",
  "prompt": "string",
  "best_of": 0,
  "echo": true,
  "frequency_penalty": 0,
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": 0,
  "max_tokens": 0,
  "n": 0,
  "presence_penalty": 0,
  "seed": 0,
  "stop": "string",
  "stream_options": {
    "include_usage": true
  },
  "suffix": "string",
  "temperature": 0,
  "top_p": 0,
  "user": "string",
  "stream": false
}
```

<h3 id="openai-mimic-api-endpoint-for-completions.-model-selection-will-be-ignored-and-overridden-with-the-one-from-the-path.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|model|path|undefined|true|none|
|body|body|any|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "choices": [],
  "created": 0,
  "model": "string",
  "object": "chat.completion",
  "service_tier": "auto",
  "system_fingerprint": "string",
  "usage": {}
}
```

<h3 id="openai-mimic-api-endpoint-for-completions.-model-selection-will-be-ignored-and-overridden-with-the-one-from-the-path.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ChatCompletion](#schemachatcompletion)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## OpenAI Mimic API endpoint for completions (Model ambiguous, Must be one in model list for this endpoint).

<a id="opIdchat_mimic_all_generic_v1_completions_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/v1/completions', headers = headers)

print(r.json())

```

`POST /v1/completions`

> Body parameter

```json
{
  "model": "string",
  "prompt": "string",
  "best_of": 0,
  "echo": true,
  "frequency_penalty": 0,
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": 0,
  "max_tokens": 0,
  "n": 0,
  "presence_penalty": 0,
  "seed": 0,
  "stop": "string",
  "stream_options": {
    "include_usage": true
  },
  "suffix": "string",
  "temperature": 0,
  "top_p": 0,
  "user": "string",
  "stream": false
}
```

<h3 id="openai-mimic-api-endpoint-for-completions-(model-ambiguous,-must-be-one-in-model-list-for-this-endpoint).-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|any|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "choices": [],
  "created": 0,
  "model": "string",
  "object": "chat.completion",
  "service_tier": "auto",
  "system_fingerprint": "string",
  "usage": {}
}
```

<h3 id="openai-mimic-api-endpoint-for-completions-(model-ambiguous,-must-be-one-in-model-list-for-this-endpoint).-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ChatCompletion](#schemachatcompletion)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetch the list of available models. Will only return the path's model.

<a id="opIdmodels_mimic_other__model__v1_models_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/{model}/v1/models', headers = headers)

print(r.json())

```

`GET /{model}/v1/models`

<h3 id="fetch-the-list-of-available-models.-will-only-return-the-path's-model.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|model|path|undefined|true|none|

> Example responses

> 200 Response

```json
{
  "data": []
}
```

<h3 id="fetch-the-list-of-available-models.-will-only-return-the-path's-model.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[Models](#schemamodels)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## OpenAI Mimic API endpoint for chat completions (Model ambiguous, Must be one in model list for this endpoint).

<a id="opIdchat_mimic_all_v1_chat_completions_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/v1/chat/completions', headers = headers)

print(r.json())

```

`POST /v1/chat/completions`

> Body parameter

```json
{
  "messages": [
    {
      "content": "string",
      "role": "developer",
      "name": "string"
    }
  ],
  "model": "string",
  "audio": {
    "format": "wav",
    "voice": "string"
  },
  "frequency_penalty": 0,
  "function_call": "none",
  "functions": [
    {
      "name": "string",
      "description": "string",
      "parameters": {}
    }
  ],
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": true,
  "max_completion_tokens": 0,
  "max_tokens": 0,
  "metadata": {
    "property1": "string",
    "property2": "string"
  },
  "modalities": [
    "text"
  ],
  "n": 0,
  "parallel_tool_calls": true,
  "prediction": {
    "content": "string",
    "type": "content"
  },
  "presence_penalty": 0,
  "reasoning_effort": "low",
  "response_format": {
    "type": "text"
  },
  "seed": 0,
  "service_tier": "auto",
  "stop": "string",
  "store": true,
  "stream_options": {
    "include_usage": true
  },
  "temperature": 0,
  "tool_choice": "none",
  "tools": [
    {
      "function": {
        "name": "string",
        "description": "string",
        "parameters": {},
        "strict": true
      },
      "type": "function"
    }
  ],
  "top_logprobs": 0,
  "top_p": 0,
  "user": "string",
  "web_search_options": {
    "search_context_size": "low",
    "user_location": {
      "approximate": {
        "city": "string",
        "country": "string",
        "region": "string",
        "timezone": "string"
      },
      "type": "approximate"
    }
  },
  "stream": false
}
```

<h3 id="openai-mimic-api-endpoint-for-chat-completions-(model-ambiguous,-must-be-one-in-model-list-for-this-endpoint).-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|any|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "choices": [],
  "created": 0,
  "model": "string",
  "object": "chat.completion",
  "service_tier": "auto",
  "system_fingerprint": "string",
  "usage": {}
}
```

<h3 id="openai-mimic-api-endpoint-for-chat-completions-(model-ambiguous,-must-be-one-in-model-list-for-this-endpoint).-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ChatCompletion](#schemachatcompletion)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetch the list of all available models.

<a id="opIdmodels_mimic_all_v1_models_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/v1/models', headers = headers)

print(r.json())

```

`GET /v1/models`

> Example responses

> 200 Response

```json
{
  "data": []
}
```

<h3 id="fetch-the-list-of-all-available-models.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[Models](#schemamodels)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-user-account">User Account</h1>

Endpoints related to a user's account.

## Get user account information.

<a id="opIdget_user_account_for_api_account_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/account', headers = headers)

print(r.json())

```

`GET /api/account`

<h3 id="get-user-account-information.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|stripe_url|query|any|false|Whether to make a stripe billing link.|
|tokens|query|boolean|false|Whether to return token information.|
|blocks|query|boolean|false|Whether to return blocked user and tag information.|
|nocache|query|any|false|Do not cache results. For forcing the browser to reload. Does not change the API response.|
|no_cache|query|any|false|Do not cache results. For forcing the browser to reload. Does not change the API response.|
|badges|query|boolean|false|Whether to fetch user badges|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-user-account-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-user-account-information.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete this account completely and irreversibly.

<a id="opIdnuke_account_api_account_delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/account', headers = headers)

print(r.json())

```

`DELETE /api/account`

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-this-account-completely-and-irreversibly.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Block yourself from viewing these in search.

<a id="opIdblock_item_api_account_block__block_type___name__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/account/block/{block_type}/{name}', headers = headers)

print(r.json())

```

`POST /api/account/block/{block_type}/{name}`

<h3 id="block-yourself-from-viewing-these-in-search.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|block_type|path|undefined|true|none|
|name|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="block-yourself-from-viewing-these-in-search.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Unblock yourself from viewing these in search.

<a id="opIdunblock_item_api_account_block__block_type___name__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/account/block/{block_type}/{name}', headers = headers)

print(r.json())

```

`DELETE /api/account/block/{block_type}/{name}`

<h3 id="unblock-yourself-from-viewing-these-in-search.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|block_type|path|undefined|true|none|
|name|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="unblock-yourself-from-viewing-these-in-search.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Prevent users from commenting specific words/phrases on your pages.

<a id="opIdblacklist_word_api_account_blacklist_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/account/blacklist', headers = headers)

print(r.json())

```

`POST /api/account/blacklist`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="prevent-users-from-commenting-specific-words/phrases-on-your-pages.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove a word from your blacklist.

<a id="opIdunblacklist_word_api_account_blacklist_remove_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/account/blacklist/remove', headers = headers)

print(r.json())

```

`POST /api/account/blacklist/remove`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="remove-a-word-from-your-blacklist.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Set a default sort order in search.

<a id="opIdset_sort_api_account_sort__order__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/account/sort/{order}', headers = headers)

print(r.json())

```

`POST /api/account/sort/{order}`

<h3 id="set-a-default-sort-order-in-search.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|order|path|undefined|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="set-a-default-sort-order-in-search.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get truncated user account information.

<a id="opIdget_user_account_truncated_api_self_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/self', headers = headers)

print(r.json())

```

`GET /api/self`

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-truncated-user-account-information.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-truncated-user-account-information.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Unfollow a tag.

<a id="opIddelete_user_tag_favorite_follow_tag__tagname__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/follow/tag/{tagname}', headers = headers)

print(r.json())

```

`DELETE /follow/tag/{tagname}`

<h3 id="unfollow-a-tag.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tagname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="unfollow-a-tag.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Follow a tag.

<a id="opIduser_tag_favorite_follow_tag__tagname__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/follow/tag/{tagname}', headers = headers)

print(r.json())

```

`POST /follow/tag/{tagname}`

<h3 id="follow-a-tag.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tagname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="follow-a-tag.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Unfollow a username.

<a id="opIddelete_user_favorite_api_follow__username__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/follow/{username}', headers = headers)

print(r.json())

```

`DELETE /api/follow/{username}`

<h3 id="unfollow-a-username.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="unfollow-a-username.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Follow a username.

<a id="opIduser_favorite_api_follow__username__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/follow/{username}', headers = headers)

print(r.json())

```

`POST /api/follow/{username}`

<h3 id="follow-a-username.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="follow-a-username.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upsert a config

<a id="opIdupsert_config_part_config__config_id___sub_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/config/{config_id}/{sub_id}', headers = headers)

print(r.json())

```

`POST /config/{config_id}/{sub_id}`

> Body parameter

```json
false
```

<h3 id="upsert-a-config-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|config_id|path|string|true|none|
|sub_id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="upsert-a-config-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete config

<a id="opIddelete_config_part_config__config_id___sub_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/config/{config_id}/{sub_id}', headers = headers)

print(r.json())

```

`DELETE /config/{config_id}/{sub_id}`

<h3 id="delete-config-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|config_id|path|string|true|none|
|sub_id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-config-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upsert configs

<a id="opIdupsert_configs_parts_config_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/config', headers = headers)

print(r.json())

```

`POST /config`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="upsert-configs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete configs

<a id="opIddelete_configs_parts_config_delete"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.delete('/config', headers = headers)

print(r.json())

```

`DELETE /config`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-configs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetch configs

<a id="opIdfetch_configs_config_fetch_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/config/fetch', headers = headers)

print(r.json())

```

`POST /config/fetch`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="fetch-configs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="fetch-configs-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetches information about the user's account.

<a id="opIdaccount"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/oauth/userinfo', headers = headers)

print(r.json())

```

`GET /oauth/userinfo`

Response includes their identity, current scopes/access, subscription, and credit balance.

> Example responses

> 200 Response

```json
{
  "identity": "string",
  "username": "string",
  "scopes": [],
  "credits": 0,
  "credits_reset": "2025-08-14T23:44:22Z",
  "credits_reset_in": "4 hours, 10 minutes",
  "subscription": "string",
  "note": "string"
}
```

<h3 id="fetches-information-about-the-user's-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[OAuthUserStub](#schemaoauthuserstub)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Authorization
</aside>

## Get user account notifications.

<a id="opIdpost_user_notifications_api_notifications_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/notifications', headers = headers)

print(r.json())

```

`POST /api/notifications`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-user-account-notifications.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-user-account-notifications.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Dismiss all user account notifications.

<a id="opIddismiss_all_api_notifications_delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/notifications', headers = headers)

print(r.json())

```

`DELETE /api/notifications`

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="dismiss-all-user-account-notifications.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Dismiss a user account notification.

<a id="opIddismiss_api_notifications__notification_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/notifications/{notification_id}', headers = headers)

print(r.json())

```

`DELETE /api/notifications/{notification_id}`

<h3 id="dismiss-a-user-account-notification.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|notification_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="dismiss-a-user-account-notification.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Dismiss an announcement for the current user.

<a id="opIddismiss_announcement_api_notifications_announcement__announcement_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/notifications/announcement/{announcement_id}', headers = headers)

print(r.json())

```

`DELETE /api/notifications/announcement/{announcement_id}`

<h3 id="dismiss-an-announcement-for-the-current-user.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|announcement_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="dismiss-an-announcement-for-the-current-user.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get user account active tokens for the inference API.

<a id="opIdget_tokens_for_api_account_tokens_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/account/tokens', headers = headers)

print(r.json())

```

`GET /api/account/tokens`

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-user-account-active-tokens-for-the-inference-api.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-user-account-active-tokens-for-the-inference-api.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new token for this account for the inference API.

<a id="opIdcreate_inference_token_api_account_tokens_core_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/account/tokens/core', headers = headers)

print(r.json())

```

`POST /api/account/tokens/core`

Create a new chat token.
:return: ActiveToken on success.

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-a-new-token-for-this-account-for-the-inference-api.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-a-new-token-for-this-account-for-the-inference-api.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new token for this account for the base API for projects CRUD.

<a id="opIdcreate_projects_token_account_tokens_projects_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/account/tokens/projects', headers = headers)

print(r.json())

```

`POST /account/tokens/projects`

Create a new projects token.
:return: ActiveToken on success.

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-a-new-token-for-this-account-for-the-base-api-for-projects-crud.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-a-new-token-for-this-account-for-the-base-api-for-projects-crud.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Revoke a token.

<a id="opIdrevoke_api_account_token__token_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/account/token/{token_id}', headers = headers)

print(r.json())

```

`DELETE /api/account/token/{token_id}`

<h3 id="revoke-a-token.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|token_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="revoke-a-token.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-chat">Chat</h1>

Endpoints related to chatting.

## Create char

<a id="opIdcreate_char_api_core_characters_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/characters', headers = headers)

print(r.json())

```

`POST /api/core/characters`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="create-char-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove a linked lorebook for a character.

<a id="opIdremove_lorebook_api_core_characters_link__username___pathname__lorebook__project_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/core/characters/link/{username}/{pathname}/lorebook/{project_id}', headers = headers)

print(r.json())

```

`DELETE /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}`

<h3 id="remove-a-linked-lorebook-for-a-character.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|
|pathname|path|string|true|none|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="remove-a-linked-lorebook-for-a-character.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Add a linked lorebook for a character.

<a id="opIdadd_lorebook_api_core_characters_link__username___pathname__lorebook__project_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/core/characters/link/{username}/{pathname}/lorebook/{project_id}', headers = headers)

print(r.json())

```

`POST /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}`

<h3 id="add-a-linked-lorebook-for-a-character.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|
|pathname|path|string|true|none|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="add-a-linked-lorebook-for-a-character.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Update char

<a id="opIdupdate_char_for_api_core_characters__username___pathname__put"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/core/characters/{username}/{pathname}', headers = headers)

print(r.json())

```

`PUT /api/core/characters/{username}/{pathname}`

> Body parameter

```json
false
```

<h3 id="update-char-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|
|pathname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="update-char-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new chat

<a id="opIdmake_chat_api_core_chats_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats', headers = headers)

print(r.json())

```

`POST /api/core/chats`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-a-new-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-a-new-chat-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Search (or get all) chats for user.

<a id="opIdget_chats_for_api_core_chats_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/core/chats', headers = headers)

print(r.json())

```

`GET /api/core/chats`

<h3 id="search-(or-get-all)-chats-for-user.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|any|false|Max number of chats to get.|
|offset|query|any|false|The offset of chats to get.|
|sort_by|query|any|false|The field to sort by. Takes: updated_at, created_at, chat_count.|
|character|query|any|false|Which character to get chats for. Can be the git id as a string or username/projectname path.|
|include_closed|query|any|false|Whether to include closed/locked/archived chats.|
|only_closed|query|any|false|Whether to only include closed/locked/archived chats.|
|search|query|any|false|Search by name, summary, and other readily-available metadata.|
|semantic_search|query|any|false|Deprecated. Attempt to do a full semantic search on the logs.|
|semantic_embedding|query|any|false|Attempt to do a full semantic search on the logs.|
|scenario|query|any|false|Only fetch results with this scenario.|
|count|query|any|false|Whether to return the total count or not.|
|cursor|query|any|false|Pagination cursor.|
|asc|query|boolean|false|Whether to sort ascending (True) or descending (False).|
|chat_count_lt|query|any|false|Only fetch results with a chat count less than this.|
|chat_count_gt|query|any|false|Only fetch results with a chat count greater than this.|
|chat_count_lte|query|any|false|Only fetch results with a chat count less than or equal to this.|
|chat_count_gte|query|any|false|Only fetch results with a chat count greater than or equal to this.|
|name_like|query|any|false|Only fetch results with a name containing this string.|
|description_like|query|any|false|Only fetch results with a description containing this string.|
|summary_like|query|any|false|Only fetch results with a summary containing this string.|
|created_at_eq|query|any|false|Only fetch results with a created_at equal to this string.|
|created_at_lt|query|any|false|Only fetch results with a created_at less than this string.|
|created_at_gt|query|any|false|Only fetch results with a created_at greater than this string.|
|created_at_lte|query|any|false|Only fetch results with a created_at less than or equal to this string.|
|created_at_gte|query|any|false|Only fetch results with a created_at greater than or equal to this string.|
|updated_at_eq|query|any|false|Only fetch results with a updated_at equal to this string.|
|updated_at_lt|query|any|false|Only fetch results with a updated_at less than this string.|
|updated_at_gt|query|any|false|Only fetch results with a updated_at greater than this string.|
|updated_at_lte|query|any|false|Only fetch results with a updated_at less than or equal to this string.|
|updated_at_gte|query|any|false|Only fetch results with a updated_at greater than or equal to this string.|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="search-(or-get-all)-chats-for-user.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="search-(or-get-all)-chats-for-user.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new chat from import

<a id="opIdimport_chat_api_core_chats_import_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/import', headers = headers)

print(r.json())

```

`POST /api/core/chats/import`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-a-new-chat-from-import-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-a-new-chat-from-import-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get chat message

<a id="opIdget_chat_message_api_core_chats__chat_id__messages__msgid__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/core/chats/{chat_id}/messages/{msgid}', headers = headers)

print(r.json())

```

`GET /api/core/chats/{chat_id}/messages/{msgid}`

<h3 id="get-chat-message-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|msgid|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-chat-message-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-chat-message-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get all public chats for a character.

<a id="opIdget_chats_for_char_by_id_api_core_chats__chat_id__public_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/core/chats/{chat_id}/public', headers = headers)

print(r.json())

```

`GET /api/core/chats/{chat_id}/public`

<h3 id="get-all-public-chats-for-a-character.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-all-public-chats-for-a-character.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-all-public-chats-for-a-character.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete chat

<a id="opIddelete_chat_api_core_chats__chat_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/core/chats/{chat_id}', headers = headers)

print(r.json())

```

`DELETE /api/core/chats/{chat_id}`

<h3 id="delete-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## update chat

<a id="opIdupdate_chat_api_core_chats__chat_id__patch"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/core/chats/{chat_id}', headers = headers)

print(r.json())

```

`PATCH /api/core/chats/{chat_id}`

> Body parameter

```json
false
```

<h3 id="update-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="update-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="update-chat-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete chats in bulk

<a id="opIdbulk_delete_chats_api_core_chats_bulk_delete_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/bulk/delete', headers = headers)

print(r.json())

```

`POST /api/core/chats/bulk/delete`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-chats-in-bulk-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get the text of these messages.

<a id="opIdget_message_strings_api_core_chats_v2__chat_id__messages_content_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/v2/{chat_id}/messages/content', headers = headers)

print(r.json())

```

`POST /api/core/chats/v2/{chat_id}/messages/content`

> Body parameter

```json
false
```

<h3 id="get-the-text-of-these-messages.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-the-text-of-these-messages.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-the-text-of-these-messages.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove character from chat

<a id="opIdremove_character_api_core_chats__chat_id__character__char_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/core/chats/{chat_id}/character/{char_id}', headers = headers)

print(r.json())

```

`DELETE /api/core/chats/{chat_id}/character/{char_id}`

<h3 id="remove-character-from-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|char_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="remove-character-from-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Add character to chat

<a id="opIdadd_character_api_core_chats__chat_id__character__char_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/{chat_id}/character/{char_id}', headers = headers)

print(r.json())

```

`POST /api/core/chats/{chat_id}/character/{char_id}`

<h3 id="add-character-to-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|char_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="add-character-to-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="add-character-to-chat-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Add characters to chat

<a id="opIdadd_characters_api_core_chats__chat_id__characters_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/{chat_id}/characters', headers = headers)

print(r.json())

```

`POST /api/core/chats/{chat_id}/characters`

> Body parameter

```json
false
```

<h3 id="add-characters-to-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="add-characters-to-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="add-characters-to-chat-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove characters from chat

<a id="opIdremove_characters_api_core_chats__chat_id__characters_remove_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/{chat_id}/characters/remove', headers = headers)

print(r.json())

```

`POST /api/core/chats/{chat_id}/characters/remove`

> Body parameter

```json
false
```

<h3 id="remove-characters-from-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="remove-characters-from-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Invite user to chat

<a id="opIdadd_user_to_chat_api_core_chats__chat_id__user__tagname__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/{chat_id}/user/{tagname}', headers = headers)

print(r.json())

```

`POST /api/core/chats/{chat_id}/user/{tagname}`

<h3 id="invite-user-to-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|tagname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="invite-user-to-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove user from chat

<a id="opIdremove_user_api_core_chats__chat_id__user__user_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/core/chats/{chat_id}/user/{user_id}', headers = headers)

print(r.json())

```

`DELETE /api/core/chats/{chat_id}/user/{user_id}`

<h3 id="remove-user-from-chat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|user_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="remove-user-from-chat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get minimized chat tree by id.

<a id="opIdget_chat_meta_tree_api_core_chats_v2__chat_id__metatree_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/core/chats/v2/{chat_id}/metatree', headers = headers)

print(r.json())

```

`GET /api/core/chats/v2/{chat_id}/metatree`

<h3 id="get-minimized-chat-tree-by-id.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-minimized-chat-tree-by-id.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-minimized-chat-tree-by-id.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get chat tree by id

<a id="opIdget_chat_tree_by_id_api_core_chats_v2__chat_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/core/chats/v2/{chat_id}', headers = headers)

print(r.json())

```

`GET /api/core/chats/v2/{chat_id}`

<h3 id="get-chat-tree-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|include_messages|query|boolean|false|If false, doesn't return messages.|
|include_config|query|boolean|false|Whether to include the user config in the response.|
|include_meta|query|boolean|false|Whether to include the chat metadata in the response.|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-chat-tree-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-chat-tree-by-id-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Make a number of operations on messages in an atomic manner.

<a id="opIdatomic_chat_modification_api_core_chats_v2__chat_id__messages_atomic_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/chats/v2/{chat_id}/messages/atomic', headers = headers)

print(r.json())

```

`POST /api/core/chats/v2/{chat_id}/messages/atomic`

> Body parameter

```json
false
```

<h3 id="make-a-number-of-operations-on-messages-in-an-atomic-manner.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="make-a-number-of-operations-on-messages-in-an-atomic-manner.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="make-a-number-of-operations-on-messages-in-an-atomic-manner.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create lorebook

<a id="opIdcreate_book_api_core_lorebooks_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/lorebooks', headers = headers)

print(r.json())

```

`POST /api/core/lorebooks`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-lorebook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-lorebook-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Update lorebook

<a id="opIdupdate_lorebook_for_id_api_core_lorebooks__project_id__put"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/core/lorebooks/{project_id}', headers = headers)

print(r.json())

```

`PUT /api/core/lorebooks/{project_id}`

> Body parameter

```json
false
```

<h3 id="update-lorebook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="update-lorebook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get semantically related messages from earlier in the chat.

<a id="opIdget_semantic_context_api_core_extensions_context_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/core/extensions/context', headers = headers)

print(r.json())

```

`POST /api/core/extensions/context`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-semantically-related-messages-from-earlier-in-the-chat.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-semantically-related-messages-from-earlier-in-the-chat.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new chat, or retrieve latest

<a id="opIdmake_or_fetch_chat_api_chats_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/chats', headers = headers)

print(r.json())

```

`POST /api/chats`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-a-new-chat,-or-retrieve-latest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-a-new-chat,-or-retrieve-latest-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get user information for this chat.

<a id="opIdget_chat_user_api_core_chats__chat_id__users__user_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/core/chats/{chat_id}/users/{user_id}', headers = headers)

print(r.json())

```

`GET /api/core/chats/{chat_id}/users/{user_id}`

<h3 id="get-user-information-for-this-chat.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|user_id|path|string|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-user-information-for-this-chat.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-user-information-for-this-chat.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-imagine">Imagine</h1>

Endpoints related to audiovisual generation.

## A unified endpoint for multimedia asset generation.

<a id="opIdimagine"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/imagine', headers = headers)

print(r.json())

```

`POST /imagine`

> Body parameter

```json
{
  "lyrics": "string",
  "genre": "automatic",
  "music_type": "mixed",
  "duration": 4,
  "end_image": "string",
  "fps": 8,
  "i2i_type": "edit",
  "mask_image": "string",
  "preserve_transparency": true,
  "init_images": [],
  "octree_resolution": 384,
  "texture_size": 1024,
  "output_type": "glb",
  "speed": "normal",
  "do_texture": true,
  "do_autorig": false,
  "autorig_type": "unknown",
  "transcript": "A wizard's job is to vex chumps quickly in fog.",
  "voice": "bright_female_20s",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "aspect_ratio": "w1h1",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "generation_type": "text_to_speech"
}
```

<h3 id="a-unified-endpoint-for-multimedia-asset-generation.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|return_immediate|query|boolean|false|none|
|body|body|[GenerationRequest](#schemagenerationrequest)|true|none|
|» lyrics|body|any|false|The song's lyrics, if relevant. Each part should begin with a structure tag ([verse], [chorus], [bridge], [intro-short], [intro-medium], [intro-long], [outro-short], [outro-medium], [outro-long], [inst-short], [inst-medium], [inst-long], [silence]) and a newline, and end with two newlines. These segments should not contain lyrics: ([intro], [intro-short], [intro-medium], [inst], [inst-short], [inst-medium], [outro], [outro-short], [outro-medium])|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» genre|body|any|false|The musical genre.|
|»» *anonymous*|body|[MusicGenre](#schemamusicgenre)|false|none|
|»» *anonymous*|body|null|false|none|
|» music_type|body|any|false|Whether to make instrumental music, only vocals, or a fully mixed song. If requesting 'vocals' or 'mixed', lyrics MUST be provided.|
|»» *anonymous*|body|[MusicGenType](#schemamusicgentype)|false|none|
|»» *anonymous*|body|null|false|none|
|» duration|body|any|false|The desired duration, in seconds, of the video, sound effect, or other media. Does not affect music length.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» end_image|body|any|false|The final frame image for image-to-video, as a URL or base64 string. If you want a video to loop, give the same start and end image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» fps|body|any|false|The number of frames per second.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» i2i_type|body|any|false|Whether to do edit-based i2i ('edit'), edge-based i2i ('canny'), or face/person-based i2i ('face'). Edit preserves the most of the structure and style of the original image; canny preserves the image's structure, but not its style; face preserves neither, but keeps the visual identity/face of a person in the source image.|
|»» *anonymous*|body|[I2IType](#schemai2itype)|false|none|
|»» *anonymous*|body|null|false|none|
|» mask_image|body|any|false|The mask image, as a URL or base64 string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» preserve_transparency|body|any|false|If given, the transparency of the non-mask image(s) will be preserved. Useful if your input image has clear parts and you want to keep them clear.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_images|body|any|false|Optional. Reference images. A list of base64 image string(s) and/or URL(s). If not provided, text-to-image will be done on the text prompt. Because of this, it is recommended to use text-to-image first and select the preferred appearance.|
|»» *anonymous*|body|[string]|false|none|
|»» *anonymous*|body|null|false|none|
|» octree_resolution|body|any|false|The octree resolution to generate for 3D models. Lower resolutions will generate faster, but be less detailed.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» texture_size|body|any|false|The pixel width of the generated texture for 3D models. Lower resolutions will generate faster, but be less detailed.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» output_type|body|any|false|What file type to output.|
|»» *anonymous*|body|[Output3DType](#schemaoutput3dtype)|false|none|
|»» *anonymous*|body|null|false|none|
|» speed|body|any|false|Enabling turbo will make generations much faster but with slightly worse output.|
|»» *anonymous*|body|[Speed](#schemaspeed)|false|none|
|»» *anonymous*|body|null|false|none|
|» do_texture|body|any|false|Whether to generate a texture as well.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» do_autorig|body|any|false|Whether to generate a rig as well.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» autorig_type|body|any|false|The type of rigging to use. 'Bipedal' is common and will create much better rigs for humans and other bipeds. The 'quadruped' option is best for non-anthropomorphic animals. If you aren't sure which to pick, use 'unknown'.|
|»» *anonymous*|body|[RigType](#schemarigtype)|false|none|
|»» *anonymous*|body|null|false|none|
|» transcript|body|any|false|The text to read out.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» voice|body|any|false|Select a voice to use.|
|»» *anonymous*|body|[Voice](#schemavoice)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» generation_type|body|[GenerationType](#schemagenerationtype)|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|pop|
|»» *anonymous*|rhythm_and_blues|
|»» *anonymous*|dance|
|»» *anonymous*|jazz|
|»» *anonymous*|folk|
|»» *anonymous*|rock|
|»» *anonymous*|chinese_modern|
|»» *anonymous*|eastern_traditional|
|»» *anonymous*|eastern_opera|
|»» *anonymous*|metal|
|»» *anonymous*|reggae|
|»» *anonymous*|automatic|
|»» *anonymous*|instrumental|
|»» *anonymous*|vocals|
|»» *anonymous*|mixed|
|»» *anonymous*|canny|
|»» *anonymous*|face|
|»» *anonymous*|edit|
|»» *anonymous*|glb|
|»» *anonymous*|vrm|
|»» *anonymous*|turbo|
|»» *anonymous*|normal|
|»» *anonymous*|biped|
|»» *anonymous*|quadruped|
|»» *anonymous*|unknown|
|»» *anonymous*|none|
|»» *anonymous*|bright_female_20s|
|»» *anonymous*|gentle_female_30s|
|»» *anonymous*|whispery_female_40s|
|»» *anonymous*|formal_female_30s|
|»» *anonymous*|professional_female_30s|
|»» *anonymous*|resonant_male_40s|
|»» *anonymous*|light_male_20s|
|»» *anonymous*|animated_male_20s|
|»» *anonymous*|calm_female_20s|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|
|» generation_type|text_to_speech|
|» generation_type|text_to_image|
|» generation_type|text_to_video|
|» generation_type|image_to_image|
|» generation_type|image_to_video|
|» generation_type|text_to_sfx|
|» generation_type|text_to_music|
|» generation_type|text_to_3d|
|» generation_type|image_to_3d|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "primary_media_url": "string",
  "description": "string",
  "prompt": {},
  "is_done": true,
  "is_failed": false,
  "uuid": "string",
  "info": {
    "width": 0,
    "height": 0,
    "dpi": 0,
    "z_index": 0,
    "opacity": 100,
    "duration": 0,
    "visible": true,
    "locked": false,
    "start_time": 0,
    "end_time": 0,
    "in_point": 0,
    "out_point": 0,
    "effects": {},
    "children": [
      null
    ]
  },
  "secondary_media_urls": {
    "property1": "string",
    "property2": "string"
  },
  "error": {
    "reason": "unknown",
    "location": "string"
  },
  "note": "string"
}
```

<h3 id="a-unified-endpoint-for-multimedia-asset-generation.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ImaginedItem](#schemaimagineditem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Rejection](#schemarejection)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Authorization
</aside>

## A unified endpoint for fetching multimedia asset generation history.

<a id="opIdhistory"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/imagine/history', headers = headers)

print(r.json())

```

`POST /imagine/history`

> Body parameter

```json
{
  "first": 10,
  "generation_uuids": null,
  "uuids": null,
  "generated_only": false,
  "media_types": [
    "text_to_speech"
  ],
  "cursor": "string",
  "order_by": "created_at",
  "asc": true,
  "return_raw": false
}
```

<h3 id="a-unified-endpoint-for-fetching-multimedia-asset-generation-history.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[HistoryRequest](#schemahistoryrequest)|true|none|
|» first|body|integer|false|The number of the results to get.|
|» generation_uuids|body|any|false|If given, only these generation UUIDs will be fetched.|
|»» *anonymous*|body|[string]|false|none|
|»» *anonymous*|body|null|false|none|
|» uuids|body|any|false|If given, only these media UUIDs will be fetched.|
|»» *anonymous*|body|[string]|false|none|
|»» *anonymous*|body|null|false|none|
|» generated_only|body|any|false|Whether to return only generated images or not. If false, uploads like source images for image-to-image will be included.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» media_types|body|any|false|What generation types to fetch. If given, other types will be excluded.|
|»» *anonymous*|body|[[GenerationType](#schemagenerationtype)]|false|none|
|»»» GenerationType|body|[GenerationType](#schemagenerationtype)|false|none|
|»» *anonymous*|body|null|false|none|
|» cursor|body|any|false|The cursor to use to fetch the next page.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» order_by|body|any|false|What field to order results by. Defaults to created_at.|
|»» *anonymous*|body|[OrderMediaBy](#schemaordermediaby)|false|none|
|»» *anonymous*|body|null|false|none|
|» asc|body|any|false|Whether to sort results in ascending order. Defaults to false.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» return_raw|body|any|false|If true, the raw media files will be returned also, in base64 format.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|text_to_speech|
|»» *anonymous*|text_to_image|
|»» *anonymous*|text_to_video|
|»» *anonymous*|image_to_image|
|»» *anonymous*|image_to_video|
|»» *anonymous*|text_to_sfx|
|»» *anonymous*|text_to_music|
|»» *anonymous*|text_to_3d|
|»» *anonymous*|image_to_3d|
|»»» GenerationType|text_to_speech|
|»»» GenerationType|text_to_image|
|»»» GenerationType|text_to_video|
|»»» GenerationType|image_to_image|
|»»» GenerationType|image_to_video|
|»»» GenerationType|text_to_sfx|
|»»» GenerationType|text_to_music|
|»»» GenerationType|text_to_3d|
|»»» GenerationType|image_to_3d|
|»» *anonymous*|created_at|
|»» *anonymous*|updated_at|
|»» *anonymous*|uuid|

> Example responses

> 200 Response

```json
{
  "items": [],
  "previous_cursor": "string",
  "cursor": "string"
}
```

<h3 id="a-unified-endpoint-for-fetching-multimedia-asset-generation-history.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ImaginedItems](#schemaimagineditems)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Authorization
</aside>

## Delete the media with these uuids.

<a id="opIddelete"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/imagine/history/delete', headers = headers)

print(r.json())

```

`POST /imagine/history/delete`

> Body parameter

```json
{
  "uuids": []
}
```

<h3 id="delete-the-media-with-these-uuids.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[DeletionRequest](#schemadeletionrequest)|true|none|
|» uuids|body|[string]|false|none|

> Example responses

> 200 Response

```json
{
  "successes": [],
  "failures": []
}
```

<h3 id="delete-the-media-with-these-uuids.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[DeletionResponse](#schemadeletionresponse)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Authorization
</aside>

## Get current costs.

<a id="opIdget_costs_images_costs_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/images/costs', headers = headers)

print(r.json())

```

`GET /images/costs`

> Example responses

> 200 Response

```json
{
  "costs": {}
}
```

<h3 id="get-current-costs.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ImagineCosts](#schemaimaginecosts)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="success">
This operation does not require authentication
</aside>

## Get all images generated under your account.

<a id="opIdget_images_images_mine_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/images/mine', headers = headers)

print(r.json())

```

`GET /images/mine`

<h3 id="get-all-images-generated-under-your-account.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|first|query|integer|false|The number of the results to get per page.|
|page|query|integer|false|The page number of the results to get.|
|extension_id|query|any|false|none|
|chat_id|query|any|false|none|
|primary_character_id|query|any|false|none|
|parent_image|query|any|false|none|
|generation_uuid|query|any|false|none|
|count|query|any|false|Whether to return the total count or not.|
|include_tts|query|any|false|Whether to include_tts.|
|generated_only|query|any|false|Whether to return only generated images or not.|

> Example responses

> 200 Response

```json
{
  "count": 0,
  "nodes": [],
  "page": 1
}
```

<h3 id="get-all-images-generated-under-your-account.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[Gallery](#schemagallery)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Inpaint an image.

<a id="opIdinpaint_images_inpaint_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/images/inpaint', headers = headers)

print(r.json())

```

`POST /images/inpaint`

> Body parameter

```json
{
  "mask_image": "string",
  "preserve_transparency": true,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5
}
```

<h3 id="inpaint-an-image.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[InpaintRequest](#schemainpaintrequest)|true|none|
|» mask_image|body|any|false|The mask image, as a URL or base64 string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» preserve_transparency|body|any|false|If given, the transparency of the non-mask image(s) will be preserved. Useful if your input image has clear parts and you want to keep them clear.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="inpaint-an-image.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove the background from an image.

<a id="opIdremovebg_images_removebg_mask_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/images/removebg_mask', headers = headers)

print(r.json())

```

`POST /images/removebg_mask`

> Body parameter

```json
{
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "image": "",
  "alpha_matting": false,
  "post_process_mask": false,
  "alpha_matting_foreground_threshold": 240,
  "alpha_matting_background_threshold": 20,
  "alpha_matting_erode_size": 5
}
```

<h3 id="remove-the-background-from-an-image.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RemoveBGRequest](#schemaremovebgrequest)|true|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» image|body|any|false|Deprecated; please use 'init_image'.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» alpha_matting|body|any|false|Whether to perform alpha matting.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» post_process_mask|body|any|false|Whether to post process the mask image.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» alpha_matting_foreground_threshold|body|any|false|Threshold for alpha matting foreground.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» alpha_matting_background_threshold|body|any|false|Threshold for alpha matting background.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» alpha_matting_erode_size|body|any|false|Erode size for alpha matting.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="remove-the-background-from-an-image.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new music piece from a prompt.

<a id="opIdtext_to_music_music_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/music', headers = headers)

print(r.json())

```

`POST /music`

> Body parameter

```json
{
  "lyrics": "string",
  "genre": "automatic",
  "music_type": "mixed",
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "tags": [
    "string"
  ],
  "title": "string",
  "cfg_coefficient": 1.5,
  "temperature": 0.9,
  "top_k": 30,
  "lyrics_prompt": "string"
}
```

<h3 id="create-a-new-music-piece-from-a-prompt.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MusicGenerationRequest](#schemamusicgenerationrequest)|true|none|
|» lyrics|body|any|false|The song's lyrics, if relevant. Each part should begin with a structure tag ([verse], [chorus], [bridge], [intro-short], [intro-medium], [intro-long], [outro-short], [outro-medium], [outro-long], [inst-short], [inst-medium], [inst-long], [silence]) and a newline, and end with two newlines. These segments should not contain lyrics: ([intro], [intro-short], [intro-medium], [inst], [inst-short], [inst-medium], [outro], [outro-short], [outro-medium])|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» genre|body|any|false|The musical genre.|
|»» *anonymous*|body|[MusicGenre](#schemamusicgenre)|false|none|
|»» *anonymous*|body|null|false|none|
|» music_type|body|any|false|Whether to make instrumental music, only vocals, or a fully mixed song. If requesting 'vocals' or 'mixed', lyrics MUST be provided.|
|»» *anonymous*|body|[MusicGenType](#schemamusicgentype)|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» tags|body|any|false|For future use.|
|»» *anonymous*|body|[string]|false|none|
|»» *anonymous*|body|null|false|none|
|» title|body|any|false|For future use.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» cfg_coefficient|body|any|false|The CFG Coefficient. Increments of 0.1. Advanced setting.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» temperature|body|any|false|The temperature. Increments of 0.1. Advanced setting.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» top_k|body|any|false|The top k. Advanced setting.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» lyrics_prompt|body|any|false|For future use.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|pop|
|»» *anonymous*|rhythm_and_blues|
|»» *anonymous*|dance|
|»» *anonymous*|jazz|
|»» *anonymous*|folk|
|»» *anonymous*|rock|
|»» *anonymous*|chinese_modern|
|»» *anonymous*|eastern_traditional|
|»» *anonymous*|eastern_opera|
|»» *anonymous*|metal|
|»» *anonymous*|reggae|
|»» *anonymous*|automatic|
|»» *anonymous*|instrumental|
|»» *anonymous*|vocals|
|»» *anonymous*|mixed|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-a-new-music-piece-from-a-prompt.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create an audio of the submitted transcript.

<a id="opIdtext_to_speech_tts_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/tts', headers = headers)

print(r.json())

```

`POST /tts`

> Body parameter

```json
{
  "transcript": "A wizard's job is to vex chumps quickly in fog.",
  "voice": "bright_female_20s",
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "model": null,
  "voice_id": null,
  "remove_silence": true,
  "stream": false,
  "character_id": null
}
```

<h3 id="create-an-audio-of-the-submitted-transcript.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TextToSpeechRequest](#schematexttospeechrequest)|true|none|
|» transcript|body|any|false|The text to read out.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» voice|body|any|false|Select a voice to use.|
|»» *anonymous*|body|[Voice](#schemavoice)|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» model|body|any|false|Which model to use. z, or None for the default.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» voice_id|body|any|false|Which voice_id to use. None for the default.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_silence|body|any|false|Whether to remove gaps from the resulting audio.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» stream|body|any|false|Whether to stream the response.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» character_id|body|any|false|The character's voice to use. Overrides voice id. Must be given as the 'username/project-slug' id.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|bright_female_20s|
|»» *anonymous*|gentle_female_30s|
|»» *anonymous*|whispery_female_40s|
|»» *anonymous*|formal_female_30s|
|»» *anonymous*|professional_female_30s|
|»» *anonymous*|resonant_male_40s|
|»» *anonymous*|light_male_20s|
|»» *anonymous*|animated_male_20s|
|»» *anonymous*|calm_female_20s|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-an-audio-of-the-submitted-transcript.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get my voices.

<a id="opIdget_voices_voices_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/voices', headers = headers)

print(r.json())

```

`GET /voices`

> Example responses

> 200 Response

```json
{
  "voices": []
}
```

<h3 id="get-my-voices.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[Voices](#schemavoices)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete voice

<a id="opIddelete_voice_voices__voice_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/voices/{voice_id}', headers = headers)

print(r.json())

```

`DELETE /voices/{voice_id}`

<h3 id="delete-voice-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voice_id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-voice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create or update a voice clone.

<a id="opIdvoice_clone_voice_clone_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('/voice_clone', headers = headers)

print(r.json())

```

`POST /voice_clone`

> Body parameter

```yaml
sample: string
transcript: A wizard's job is to vex chumps quickly in fog.
model: all
reference_text: string
character_id_str: null
name: Deep Male
existing_id: null

```

<h3 id="create-or-update-a-voice-clone.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Body_voice_clone_voice_clone_post](#schemabody_voice_clone_voice_clone_post)|false|none|
|» sample|body|any|false|The sample audio file. Recognized formats: 'mp3', 'flv', 'ogg', 'wav', 'raw', 'm4a', 'mp4', 'wave'.|
|»» *anonymous*|body|string(binary)|false|none|
|»» *anonymous*|body|null|false|none|
|» transcript|body|any|false|The text to read out for the example output(s).|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» model|body|any|false|Which model to use. all, or None for the default.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» reference_text|body|any|false|Optional. The text that is being said in the sample audio. If not given, stt will be done on the example audio to get this.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» character_id_str|body|any|false|If given, the voice of this character will be set to the voice.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» name|body|any|false|The name of the voice.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» existing_id|body|any|false|The id of the existing voice.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|

> Example responses

> 200 Response

```json
{
  "uuid": "string",
  "version": 0,
  "user_id": 0,
  "name": "string",
  "is_done": true,
  "is_failed": true,
  "transcript": "string",
  "sample": "string",
  "reference_text": "string",
  "model": "string",
  "example": "string",
  "e2_example": "string",
  "f5_example": "string",
  "z_example": "string",
  "created_at": "string",
  "updated_at": "string"
}
```

<h3 id="create-or-update-a-voice-clone.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[VoiceClone](#schemavoiceclone)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create an image from a prompt.

<a id="opIdtext2img_images_text2img_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/images/text2img', headers = headers)

print(r.json())

```

`POST /images/text2img`

> Body parameter

```json
{
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5
}
```

<h3 id="create-an-image-from-a-prompt.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TextToImage](#schematexttoimage)|true|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-an-image-from-a-prompt.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new image from a base one and a prompt.

<a id="opIdimage_to_image_images_img2img_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/images/img2img', headers = headers)

print(r.json())

```

`POST /images/img2img`

> Body parameter

```json
{
  "i2i_type": "edit",
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "type": "edit"
}
```

<h3 id="create-a-new-image-from-a-base-one-and-a-prompt.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ImageToImageRequest](#schemaimagetoimagerequest)|true|none|
|» i2i_type|body|any|false|Whether to do edit-based i2i ('edit'), edge-based i2i ('canny'), or face/person-based i2i ('face'). Edit preserves the most of the structure and style of the original image; canny preserves the image's structure, but not its style; face preserves neither, but keeps the visual identity/face of a person in the source image.|
|»» *anonymous*|body|[I2IType](#schemai2itype)|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» type|body|any|false|Whether to do edit-based i2i ('edit'), edge-based i2i ('canny'), or face/person-based i2i ('face'). Edit preserves the most of the structure and style of the original image; canny preserves the image's structure, but not its style; face preserves neither, but keeps the visual identity/face of a person in the source image.|
|»» *anonymous*|body|[I2IType](#schemai2itype)|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|canny|
|»» *anonymous*|face|
|»» *anonymous*|edit|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|
|»» *anonymous*|canny|
|»» *anonymous*|face|
|»» *anonymous*|edit|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-a-new-image-from-a-base-one-and-a-prompt.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new animation from a base image.

<a id="opIdimage_to_animation_images_animate_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/images/animate', headers = headers)

print(r.json())

```

`POST /images/animate`

> Body parameter

```json
{
  "end_image": "string",
  "fps": 8,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "loop": false,
  "num_frames": 12
}
```

<h3 id="create-a-new-animation-from-a-base-image.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[VideoRequest](#schemavideorequest)|true|none|
|» end_image|body|any|false|The final frame image for image-to-video, as a URL or base64 string. If you want a video to loop, give the same start and end image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» fps|body|any|false|The number of frames per second.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» loop|body|any|false|Whether to loop the image.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» num_frames|body|any|false|The number of frames to generate.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-a-new-animation-from-a-base-image.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new video from a prompt.

<a id="opIdimage_to_animation_video_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/video', headers = headers)

print(r.json())

```

`POST /video`

> Body parameter

```json
{
  "end_image": "string",
  "fps": 8,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "loop": false,
  "num_frames": 12
}
```

<h3 id="create-a-new-video-from-a-prompt.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[VideoRequest](#schemavideorequest)|true|none|
|» end_image|body|any|false|The final frame image for image-to-video, as a URL or base64 string. If you want a video to loop, give the same start and end image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» fps|body|any|false|The number of frames per second.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» loop|body|any|false|Whether to loop the image.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» num_frames|body|any|false|The number of frames to generate.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-a-new-video-from-a-prompt.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new sound effect from a prompt.

<a id="opIdtext_to_foley_foley_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/foley', headers = headers)

print(r.json())

```

`POST /foley`

> Body parameter

```json
{
  "duration": 4,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "two starships are fighting in space with laser cannons",
  "negative_prompt": "distorted",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5
}
```

<h3 id="create-a-new-sound-effect-from-a-prompt.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FoleyRequest](#schemafoleyrequest)|true|none|
|» duration|body|any|false|The desired duration, in seconds, of the video, sound effect, or other media. Does not affect music length.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The desired aspect ratio.|
|»» *anonymous*|body|[AspectRatio](#schemaaspectratio)|false|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|w1h1|
|»» *anonymous*|w1h2|
|»» *anonymous*|w2h1|
|»» *anonymous*|w16h9|
|»» *anonymous*|w21h9|
|»» *anonymous*|w2h3|
|»» *anonymous*|w3h2|
|»» *anonymous*|w3h4|
|»» *anonymous*|w4h3|
|»» *anonymous*|w4h5|
|»» *anonymous*|w5h4|
|»» *anonymous*|w9h16|
|»» *anonymous*|w9h21|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-a-new-sound-effect-from-a-prompt.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upscale an image.

<a id="opIdupscale_image_images_upscale_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/images/upscale', headers = headers)

print(r.json())

```

`POST /images/upscale`

> Body parameter

```json
{
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "aspect_ratio": null,
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "image": "",
  "preserve_transparency": true
}
```

<h3 id="upscale-an-image.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpscaleBase](#schemaupscalebase)|true|none|
|» seed|body|any|false|Use this only if reproducible results are important.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt|body|any|false|It should be descriptive of exactly what you want, and fairly detailed.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» negative_prompt|body|any|false|What you don't want in the result.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» aspect_ratio|body|any|false|The aspect ratio. If given, this will override the width and height. Values are '1:1', '16:9', '21:9', '2:3', '3:2', '3:4', '4:3', '4:5', '5:4', '9:16', and '9:21'.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» num_inference_steps|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» remove_background|body|any|false|Whether to remove the background of any image(s) before/after this operation.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» init_image|body|any|false|Base64 image string, or a URL to an image.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» strength|body|any|false|The strength of any image-to-image transformation.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guidance_scale|body|any|false|How strongly the prompt affects the output.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_id|body|any|false|If this is inside of a chat, include its ID as a string.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» uuid|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» sub_mode|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|The width. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|The height. Overridden by aspect ratio.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» item_id|body|any|false|The item_id, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» extension_source|body|any|false|If an extension is requesting this, include its ID.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|The UUID of the parent image, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» image|body|any|false|Deprecated; please use 'init_image'.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» preserve_transparency|body|any|false|If given, this transparency will be preserved.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="upscale-an-image.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Check on a running task.

<a id="opIdtask_check_check_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/check', headers = headers)

print(r.json())

```

`POST /check`

> Body parameter

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "request_type": "string"
}
```

<h3 id="check-on-a-running-task.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RunningGenerationCheck](#schemarunninggenerationcheck)|true|none|
|» generation_uuid|body|any|false|The unique identity of the generation, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» cost|body|any|false|Cost in credits, if any.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» request_type|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="check-on-a-running-task.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## A unified endpoint for checking on a running generation.

<a id="opIdcheck"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/imagine/check', headers = headers)

print(r.json())

```

`POST /imagine/check`

> Body parameter

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "request_type": "string"
}
```

<h3 id="a-unified-endpoint-for-checking-on-a-running-generation.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RunningGenerationCheck](#schemarunninggenerationcheck)|true|none|
|» generation_uuid|body|any|false|The unique identity of the generation, if any.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» cost|body|any|false|Cost in credits, if any.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» request_type|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "primary_media_url": "string",
  "description": "string",
  "prompt": {},
  "is_done": true,
  "is_failed": false,
  "uuid": "string",
  "info": {
    "width": 0,
    "height": 0,
    "dpi": 0,
    "z_index": 0,
    "opacity": 100,
    "duration": 0,
    "visible": true,
    "locked": false,
    "start_time": 0,
    "end_time": 0,
    "in_point": 0,
    "out_point": 0,
    "effects": {},
    "children": [
      null
    ]
  },
  "secondary_media_urls": {
    "property1": "string",
    "property2": "string"
  },
  "error": {
    "reason": "unknown",
    "location": "string"
  },
  "note": "string"
}
```

<h3 id="a-unified-endpoint-for-checking-on-a-running-generation.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ImaginedItem](#schemaimagineditem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Authorization
</aside>

## STT endpoint.

<a id="opIdspeech_to_text_stt_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('/stt', headers = headers)

print(r.json())

```

`POST /stt`

> Body parameter

```yaml
sample: string

```

<h3 id="stt-endpoint.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Body_speech_to_text_stt_post](#schemabody_speech_to_text_stt_post)|true|none|
|» sample|body|string(binary)|true|The sample audio file. Recognized formats: 'mp3', 'flv', 'ogg', 'wav', 'raw', 'm4a', 'mp4', 'wave'.|

> Example responses

> 200 Response

```json
{
  "reference_text": ""
}
```

<h3 id="stt-endpoint.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[STTResponse](#schemasttresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## API endpoint for generic completions.

<a id="opIdchat_mars_all_prompt_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/prompt', headers = headers)

print(r.json())

```

`POST /prompt`

> Body parameter

```json
{
  "messages": [],
  "model": "mobile",
  "frequency_penalty": 1.15,
  "logit_bias": {},
  "logprobs": false,
  "top_logprobs": 0,
  "max_tokens": 300,
  "max_completion_tokens": 0,
  "n": 1,
  "presence_penalty": 1.15,
  "response_format": {
    "type": "text",
    "json_schema": {
      "name": "string",
      "description": "string",
      "schema": {},
      "strict": true
    }
  },
  "seed": -9223372036854776000,
  "stop": [],
  "stream": false,
  "stream_options": {
    "include_usage": true,
    "continuous_usage_stats": false
  },
  "temperature": 0.8,
  "top_p": 1,
  "tools": [
    {
      "type": "function",
      "function": {
        "name": "string",
        "description": "string",
        "parameters": {}
      }
    }
  ],
  "tool_choice": "none",
  "parallel_tool_calls": false,
  "user": "string",
  "best_of": 0,
  "use_beam_search": false,
  "top_k": 50,
  "min_p": 0,
  "repetition_penalty": 0,
  "length_penalty": 1,
  "stop_token_ids": [],
  "include_stop_str_in_output": false,
  "ignore_eos": false,
  "min_tokens": 50,
  "skip_special_tokens": true,
  "spaces_between_special_tokens": true,
  "truncate_prompt_tokens": 1,
  "prompt_logprobs": 0,
  "allowed_token_ids": [
    0
  ],
  "bad_words": [
    "string"
  ],
  "echo": false,
  "add_generation_prompt": true,
  "continue_final_message": false,
  "add_special_tokens": false,
  "documents": [
    {
      "property1": "string",
      "property2": "string"
    }
  ],
  "chat_template": "string",
  "chat_template_kwargs": {},
  "mm_processor_kwargs": {},
  "guided_json": "string",
  "guided_regex": "string",
  "guided_choice": [
    "string"
  ],
  "guided_grammar": "string",
  "structural_tag": "string",
  "guided_decoding_backend": "string",
  "guided_whitespace_pattern": "string",
  "priority": 0,
  "request_id": "string",
  "logits_processors": [
    "string"
  ],
  "return_tokens_as_token_ids": true,
  "cache_salt": "string",
  "kv_transfer_params": {},
  "vllm_xargs": {
    "property1": "string",
    "property2": "string"
  },
  "identity": "string",
  "prompt": "string",
  "query": "",
  "typical": 0,
  "token_repetition_penalty": 1.05,
  "guided_decoding": {
    "json": "string",
    "regex": "string",
    "choice": [
      "string"
    ],
    "grammar": "string",
    "json_object": true,
    "backend": "string",
    "backend_was_auto": false,
    "disable_fallback": false,
    "disable_any_whitespace": false,
    "disable_additional_properties": false,
    "whitespace_pattern": "string",
    "structural_tag": "string"
  },
  "sent_at": 0,
  "publish_to": "string",
  "token_repetition_range": -1,
  "token_repetition_decay": 0,
  "top_a": 0,
  "tfs": 0,
  "next": [
    "string"
  ],
  "n_tokens": 0,
  "do_voice": false,
  "voice_id": null,
  "template": "Hi how are you?",
  "parameters": {}
}
```

<h3 id="api-endpoint-for-generic-completions.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MarsRequest](#schemamarsrequest)|true|none|
|» messages|body|[anyOf]|false|none|
|»» *anonymous*|body|[ChatCompletionDeveloperMessageParam](#schemachatcompletiondevelopermessageparam)|false|none|
|»»» content|body|any|true|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|[[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)]|false|none|
|»»»»» ChatCompletionContentPartTextParam|body|[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)|false|none|
|»»»»»» text|body|string|true|none|
|»»»»»» type|body|string|true|none|
|»»» role|body|string|true|none|
|»»» name|body|string|false|none|
|»» *anonymous*|body|[ChatCompletionSystemMessageParam](#schemachatcompletionsystemmessageparam)|false|none|
|»»» content|body|any|true|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|[[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)]|false|none|
|»»»»» ChatCompletionContentPartTextParam|body|[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)|false|none|
|»»» role|body|string|true|none|
|»»» name|body|string|false|none|
|»» *anonymous*|body|[ChatCompletionUserMessageParam](#schemachatcompletionusermessageparam)|false|none|
|»»» content|body|any|true|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|[anyOf]|false|none|
|»»»»» *anonymous*|body|[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)|false|none|
|»»»»» *anonymous*|body|[ChatCompletionContentPartImageParam](#schemachatcompletioncontentpartimageparam)|false|none|
|»»»»»» image_url|body|[ImageURL](#schemaimageurl)|true|none|
|»»»»»»» url|body|string|true|none|
|»»»»»»» detail|body|string|false|none|
|»»»»»» type|body|string|true|none|
|»»»»» *anonymous*|body|[ChatCompletionContentPartInputAudioParam](#schemachatcompletioncontentpartinputaudioparam)|false|none|
|»»»»»» input_audio|body|[InputAudio](#schemainputaudio)|true|none|
|»»»»»»» data|body|string|true|none|
|»»»»»»» format|body|string|true|none|
|»»»»»» type|body|string|true|none|
|»»»»» *anonymous*|body|[File](#schemafile)|false|none|
|»»»»»» file|body|[FileFile](#schemafilefile)|true|none|
|»»»»»»» file_data|body|string|false|none|
|»»»»»»» file_id|body|string|false|none|
|»»»»»»» filename|body|string|false|none|
|»»»»»» type|body|string|true|none|
|»»» role|body|string|true|none|
|»»» name|body|string|false|none|
|»» *anonymous*|body|[ChatCompletionAssistantMessageParam](#schemachatcompletionassistantmessageparam)|false|none|
|»»» role|body|string|true|none|
|»»» audio|body|any|false|none|
|»»»» *anonymous*|body|[Audio](#schemaaudio)|false|none|
|»»»»» id|body|string|true|none|
|»»»» *anonymous*|body|null|false|none|
|»»» content|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|[anyOf]|false|none|
|»»»»» *anonymous*|body|[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)|false|none|
|»»»»» *anonymous*|body|[ChatCompletionContentPartRefusalParam](#schemachatcompletioncontentpartrefusalparam)|false|none|
|»»»»»» refusal|body|string|true|none|
|»»»»»» type|body|string|true|none|
|»»»» *anonymous*|body|null|false|none|
|»»» function_call|body|any|false|none|
|»»»» *anonymous*|body|[FunctionCall-Input](#schemafunctioncall-input)|false|none|
|»»»»» arguments|body|string|true|none|
|»»»»» name|body|string|true|none|
|»»»» *anonymous*|body|null|false|none|
|»»» name|body|string|false|none|
|»»» refusal|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» tool_calls|body|[[ChatCompletionMessageToolCallParam](#schemachatcompletionmessagetoolcallparam)]|false|none|
|»»»» ChatCompletionMessageToolCallParam|body|[ChatCompletionMessageToolCallParam](#schemachatcompletionmessagetoolcallparam)|false|none|
|»»»»» id|body|string|true|none|
|»»»»» function|body|[openai__types__chat__chat_completion_message_tool_call_param__Function](#schemaopenai__types__chat__chat_completion_message_tool_call_param__function)|true|none|
|»»»»»» arguments|body|string|true|none|
|»»»»»» name|body|string|true|none|
|»»»»» type|body|string|true|none|
|»» *anonymous*|body|[ChatCompletionToolMessageParam](#schemachatcompletiontoolmessageparam)|false|none|
|»»» content|body|any|true|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|[[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)]|false|none|
|»»»»» ChatCompletionContentPartTextParam|body|[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)|false|none|
|»»» role|body|string|true|none|
|»»» tool_call_id|body|string|true|none|
|»» *anonymous*|body|[ChatCompletionFunctionMessageParam](#schemachatcompletionfunctionmessageparam)|false|none|
|»»» content|body|any|true|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» name|body|string|true|none|
|»»» role|body|string|true|none|
|» model|body|any|false|The model to use. If using the combined endpoint, must be one of the available models. If using a model-specific endpoint, this value will be ignored and overridden by the path.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» frequency_penalty|body|any|false|Frequency penalty is a way to prevent word repetitions.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» logit_bias|body|any|false|none|
|»» *anonymous*|body|object|false|none|
|»»» **additionalProperties**|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» logprobs|body|any|false|none|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» top_logprobs|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» max_tokens|body|any|false|The maximum tokens to return. This is a hard limit.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» max_completion_tokens|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» n|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» presence_penalty|body|any|false|Presence penalty is a way to prevent topic repetitions.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» response_format|body|any|false|none|
|»» *anonymous*|body|[ResponseFormat](#schemaresponseformat)|false|none|
|»»» type|body|string|true|none|
|»»» json_schema|body|any|false|none|
|»»»» *anonymous*|body|[JsonSchemaResponseFormat](#schemajsonschemaresponseformat)|false|none|
|»»»»» name|body|string|true|none|
|»»»»» description|body|any|false|none|
|»»»»»» *anonymous*|body|string|false|none|
|»»»»»» *anonymous*|body|null|false|none|
|»»»»» schema|body|any|false|none|
|»»»»»» *anonymous*|body|object|false|none|
|»»»»»» *anonymous*|body|null|false|none|
|»»»»» strict|body|any|false|none|
|»»»»»» *anonymous*|body|boolean|false|none|
|»»»»»» *anonymous*|body|null|false|none|
|»»»» *anonymous*|body|null|false|none|
|»» *anonymous*|body|[StructuralTagResponseFormat](#schemastructuraltagresponseformat)|false|none|
|»»» type|body|string|true|none|
|»»» structures|body|[[StructuralTag](#schemastructuraltag)]|true|none|
|»»»» StructuralTag|body|[StructuralTag](#schemastructuraltag)|false|none|
|»»»»» begin|body|string|true|none|
|»»»»» schema|body|any|false|none|
|»»»»»» *anonymous*|body|object|false|none|
|»»»»»» *anonymous*|body|null|false|none|
|»»»»» end|body|string|true|none|
|»»» triggers|body|[string]|true|none|
|»» *anonymous*|body|null|false|none|
|» seed|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» stop|body|any|false|A list of strings to stop generations at. Will override min_tokens.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|[string]|false|none|
|»» *anonymous*|body|null|false|none|
|» stream|body|any|false|Whether to return the response streaming. Defaults to false.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» stream_options|body|any|false|none|
|»» *anonymous*|body|[StreamOptions](#schemastreamoptions)|false|none|
|»»» include_usage|body|any|false|none|
|»»»» *anonymous*|body|boolean|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» continuous_usage_stats|body|any|false|none|
|»»»» *anonymous*|body|boolean|false|none|
|»»»» *anonymous*|body|null|false|none|
|»» *anonymous*|body|null|false|none|
|» temperature|body|any|false|The temperature. Like creativity.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» top_p|body|any|false|The top percentage of tokens to sample from at each step.|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» tools|body|any|false|none|
|»» *anonymous*|body|[[ChatCompletionToolsParam](#schemachatcompletiontoolsparam)]|false|none|
|»»» ChatCompletionToolsParam|body|[ChatCompletionToolsParam](#schemachatcompletiontoolsparam)|false|none|
|»»»» type|body|string|false|none|
|»»»» function|body|[vllm__entrypoints__openai__protocol__FunctionDefinition](#schemavllm__entrypoints__openai__protocol__functiondefinition)|true|none|
|»»»»» name|body|string|true|none|
|»»»»» description|body|any|false|none|
|»»»»»» *anonymous*|body|string|false|none|
|»»»»»» *anonymous*|body|null|false|none|
|»»»»» parameters|body|any|false|none|
|»»»»»» *anonymous*|body|object|false|none|
|»»»»»» *anonymous*|body|null|false|none|
|»» *anonymous*|body|null|false|none|
|» tool_choice|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|[vllm__entrypoints__openai__protocol__ChatCompletionNamedToolChoiceParam](#schemavllm__entrypoints__openai__protocol__chatcompletionnamedtoolchoiceparam)|false|none|
|»»» function|body|[ChatCompletionNamedFunction](#schemachatcompletionnamedfunction)|true|none|
|»»»» name|body|string|true|none|
|»»» type|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parallel_tool_calls|body|any|false|none|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» user|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» best_of|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» use_beam_search|body|boolean|false|none|
|» top_k|body|any|false|The top K most likely tokens to sample from at each step.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» min_p|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» repetition_penalty|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» length_penalty|body|number|false|none|
|» stop_token_ids|body|any|false|none|
|»» *anonymous*|body|[integer]|false|none|
|»» *anonymous*|body|null|false|none|
|» include_stop_str_in_output|body|boolean|false|none|
|» ignore_eos|body|boolean|false|none|
|» min_tokens|body|any|false|The minimum tokens to return. This is a soft limit -- if the model hits certain stop strings it may stop earlier, but it will *attempt* to return a response at least this long.|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» skip_special_tokens|body|boolean|false|none|
|» spaces_between_special_tokens|body|boolean|false|none|
|» truncate_prompt_tokens|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» prompt_logprobs|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» allowed_token_ids|body|any|false|none|
|»» *anonymous*|body|[integer]|false|none|
|»» *anonymous*|body|null|false|none|
|» bad_words|body|[string]|false|none|
|» echo|body|boolean|false|If true, the new message will be prepended with the last message if they belong to the same role.|
|» add_generation_prompt|body|boolean|false|none|
|» continue_final_message|body|boolean|false|none|
|» add_special_tokens|body|boolean|false|If true, special tokens (e.g. BOS) will be added to the prompt on top of what is added by the chat template. For most models, the chat template takes care of adding the special tokens so this should be set to false (as is the default).|
|» documents|body|any|false|A list of dicts representing documents that will be accessible to the model if it is performing RAG (retrieval-augmented generation). If the template does not support RAG, this argument will have no effect. We recommend that each document should be a dict containing "title" and "text" keys.|
|»» *anonymous*|body|[object]|false|none|
|»»» **additionalProperties**|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_template|body|any|false|A Jinja template to use for this conversion. As of transformers v4.44, default chat template is no longer allowed, so you must provide a chat template if the tokenizer does not define one.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» chat_template_kwargs|body|any|false|Additional keyword args to pass to the template renderer. Will be accessible by the chat template.|
|»» *anonymous*|body|object|false|none|
|»» *anonymous*|body|null|false|none|
|» mm_processor_kwargs|body|any|false|Additional kwargs to pass to the HF processor.|
|»» *anonymous*|body|object|false|none|
|»» *anonymous*|body|null|false|none|
|» guided_json|body|any|false|If specified, the output will follow the JSON schema.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|object|false|none|
|»» *anonymous*|body|[BaseModel](#schemabasemodel)|false|none|
|»» *anonymous*|body|null|false|none|
|» guided_regex|body|any|false|If specified, the output will follow the regex pattern.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» guided_choice|body|any|false|If specified, the output will be exactly one of the choices.|
|»» *anonymous*|body|[string]|false|none|
|»» *anonymous*|body|null|false|none|
|» guided_grammar|body|any|false|If specified, the output will follow the context free grammar.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» structural_tag|body|any|false|If specified, the output will follow the structural tag schema.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» guided_decoding_backend|body|any|false|If specified, will override the default guided decoding backend of the server for this specific request. If set, must be either 'outlines' / 'lm-format-enforcer'|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» guided_whitespace_pattern|body|any|false|If specified, will override the default whitespace pattern for guided json decoding.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» priority|body|integer|false|none|
|» request_id|body|string|false|The request_id related to this request. If the caller does not set it, a random_uuid will be generated. This id is used through out the inference process and return in response.|
|» logits_processors|body|any|false|A list of either qualified names of logits processors, or constructor objects, to apply when sampling. A constructor is a JSON object with a required 'qualname' field specifying the qualified name of the processor class/factory, and optional 'args' and 'kwargs' fields containing positional and keyword arguments. For example: {'qualname': 'my_module.MyLogitsProcessor', 'args': [1, 2], 'kwargs': {'param': 'value'}}.|
|»» *anonymous*|body|[anyOf]|false|none|
|»»» *anonymous*|body|string|false|none|
|»»» *anonymous*|body|[LogitsProcessorConstructor](#schemalogitsprocessorconstructor)|false|none|
|»»»» qualname|body|string|true|none|
|»»»» args|body|any|false|none|
|»»»»» *anonymous*|body|[any]|false|none|
|»»»»» *anonymous*|body|null|false|none|
|»»»» kwargs|body|any|false|none|
|»»»»» *anonymous*|body|object|false|none|
|»»»»» *anonymous*|body|null|false|none|
|»» *anonymous*|body|null|false|none|
|» return_tokens_as_token_ids|body|any|false|If specified with 'logprobs', tokens are represented  as strings of the form 'token_id:{token_id}' so that tokens that are not JSON-encodable can be identified.|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» cache_salt|body|any|false|If specified, the prefix cache will be salted with the provided string to prevent an attacker to guess prompts in multi-user environments. The salt should be random, protected from access by 3rd parties, and long enough to be unpredictable (e.g., 43 characters base64-encoded, corresponding to 256 bit). Not supported by vLLM engine V0.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» kv_transfer_params|body|any|false|KVTransfer parameters used for disaggregated serving.|
|»» *anonymous*|body|object|false|none|
|»» *anonymous*|body|null|false|none|
|» vllm_xargs|body|any|false|Additional request parameters with string or numeric values, used by custom extensions.|
|»» *anonymous*|body|object|false|none|
|»»» **additionalProperties**|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|integer|false|none|
|»»»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» identity|body|string|false|For internal sanity-checking.|
|» prompt|body|any|false|The prompt to use.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» query|body|string|false|The raw query string, already pre-parsed.|
|» typical|body|number|false|The typical|
|» token_repetition_penalty|body|any|false|Repetition Penalty as a way to prevent word repetitions|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» guided_decoding|body|any|false|none|
|»» *anonymous*|body|[GuidedDecodingParams](#schemaguideddecodingparams)|false|none|
|»»» json|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|object|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» regex|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» choice|body|any|false|none|
|»»»» *anonymous*|body|[string]|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» grammar|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» json_object|body|any|false|none|
|»»»» *anonymous*|body|boolean|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» backend|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» backend_was_auto|body|boolean|false|none|
|»»» disable_fallback|body|boolean|false|none|
|»»» disable_any_whitespace|body|boolean|false|none|
|»»» disable_additional_properties|body|boolean|false|none|
|»»» whitespace_pattern|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|null|false|none|
|»»» structural_tag|body|any|false|none|
|»»»» *anonymous*|body|string|false|none|
|»»»» *anonymous*|body|null|false|none|
|»» *anonymous*|body|null|false|none|
|» sent_at|body|integer|false|The UTC seconds sent at.|
|» publish_to|body|any|false|Result topic.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» token_repetition_range|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» token_repetition_decay|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» top_a|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» tfs|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» next|body|any|false|The next queue to send it on to.|
|»» *anonymous*|body|[string]|false|none|
|»» *anonymous*|body|null|false|none|
|» n_tokens|body|any|false|none|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» do_voice|body|any|false|none|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» voice_id|body|any|false|Which voice_id to use. None for the default.|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» template|body|any|false|The template to use. Example: "Tell me more about {{user}}."|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parameters|body|any|false|The params for the template. These will be directly replaced in the template. E.g. for the template example above,  parameters of {"{{user}}": "Jake"} would make the raw prompt given to the model "Tell me more about Jake."|
|»» *anonymous*|body|object|false|none|
|»»» **additionalProperties**|body|string|false|none|
|»» *anonymous*|body|null|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»»»»»» detail|auto|
|»»»»»»» detail|low|
|»»»»»»» detail|high|
|»»»»»»» format|wav|
|»»»»»»» format|mp3|
|»»» type|text|
|»»» type|json_object|
|»»» type|json_schema|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "choices": [],
  "created": 0,
  "model": "string",
  "object": "chat.completion",
  "service_tier": "auto",
  "system_fingerprint": "string",
  "usage": {}
}
```

<h3 id="api-endpoint-for-generic-completions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[ChatCompletion](#schemachatcompletion)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Update an existing imagine project or image.

<a id="opIdupdate_imagine_project_imagine_project__uuid__patch"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/imagine/project/{uuid}', headers = headers)

print(r.json())

```

`PATCH /imagine/project/{uuid}`

> Body parameter

```json
{
  "description": "string",
  "comments_enabled": true,
  "duration": 0,
  "width": 0,
  "height": 0,
  "dpi": 0,
  "z_index": 0,
  "opacity": 0,
  "visible": true,
  "locked": true,
  "start_time": 0,
  "end_time": 0,
  "in_point": 0,
  "out_point": 0,
  "name": "string",
  "parent_image": "string",
  "is_published": true,
  "is_nsfw": true,
  "is_nsfl": true,
  "imagination_type": "string",
  "image": "string",
  "preview": "string",
  "effects": {}
}
```

<h3 id="update-an-existing-imagine-project-or-image.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|
|body|body|[ImagineChangeRequest](#schemaimaginechangerequest)|true|none|
|» description|body|any|false|Description|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» comments_enabled|body|any|false|Are comments enabled|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» duration|body|any|false|Duration|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» width|body|any|false|Width|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» height|body|any|false|Height|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» dpi|body|any|false|DPI|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» z_index|body|any|false|Z Index|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» opacity|body|any|false|Opacity|
|»» *anonymous*|body|integer|false|none|
|»» *anonymous*|body|null|false|none|
|» visible|body|any|false|Visible|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» locked|body|any|false|Locked|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» start_time|body|any|false|Start time|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» end_time|body|any|false|End time|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» in_point|body|any|false|In time|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» out_point|body|any|false|Out time|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|null|false|none|
|» name|body|any|false|Image Name|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» parent_image|body|any|false|parent_image|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» is_published|body|any|false|Is published|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» is_nsfw|body|any|false|Is NSFW|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» is_nsfl|body|any|false|Is NSFL|
|»» *anonymous*|body|boolean|false|none|
|»» *anonymous*|body|null|false|none|
|» imagination_type|body|any|false|none|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» image|body|any|false|Image path or base64|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» preview|body|any|false|Preview|
|»» *anonymous*|body|string|false|none|
|»» *anonymous*|body|null|false|none|
|» effects|body|any|false|Effects|
|»» *anonymous*|body|any|false|none|
|»» *anonymous*|body|null|false|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="update-an-existing-imagine-project-or-image.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new 3D model from a prompt and/or image(s).

<a id="opIdmodel_3d_object_model3d_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/model3d', headers = headers)

print(r.json())

```

`POST /model3d`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-a-new-3d-model-from-a-prompt-and/or-image(s).-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a sprite pack from an image or a prompt.

<a id="opIdsprite_pack_images_expressions_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/images/expressions', headers = headers)

print(r.json())

```

`POST /images/expressions`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}
```

<h3 id="create-a-sprite-pack-from-an-image-or-a-prompt.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[TimedResponse](#schematimedresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-live">Live</h1>

Endpoints related to multi-user and live voice.

## Make an invite link.

<a id="opIdlive_invite_live_invite_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/live/invite', headers = headers)

print(r.json())

```

`POST /live/invite`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="make-an-invite-link.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="make-an-invite-link.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Change the permissions of a live user.

<a id="opIdlive_perms_update_live_permissions_patch"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/live/permissions', headers = headers)

print(r.json())

```

`PATCH /live/permissions`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="change-the-permissions-of-a-live-user.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get a new live token.

<a id="opIdgo_live_live_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/live', headers = headers)

print(r.json())

```

`POST /live`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-a-new-live-token.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-a-new-live-token.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Request live voice chat.

<a id="opIdlive_voice_live_voice_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/live/voice', headers = headers)

print(r.json())

```

`POST /live/voice`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="request-live-voice-chat.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="request-live-voice-chat.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## End live voice chat.

<a id="opIdremove_agent_live_voice__chat_id___agent_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/live/voice/{chat_id}/{agent_id}', headers = headers)

print(r.json())

```

`DELETE /live/voice/{chat_id}/{agent_id}`

<h3 id="end-live-voice-chat.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|chat_id|path|integer|true|none|
|agent_id|path|string|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="end-live-voice-chat.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="end-live-voice-chat.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-personas">Personas</h1>

CRUD for user personas.

## Get personas for a user.

<a id="opIdget_personas_api_personas_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/personas', headers = headers)

print(r.json())

```

`GET /api/personas`

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-personas-for-a-user.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-personas-for-a-user.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a new persona

<a id="opIdmake_persona_api_personas_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/personas', headers = headers)

print(r.json())

```

`POST /api/personas`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-a-new-persona-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-a-new-persona-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Update an existing persona

<a id="opIdupdate_persona_api_personas__persona_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/personas/{persona_id}', headers = headers)

print(r.json())

```

`POST /api/personas/{persona_id}`

> Body parameter

```json
false
```

<h3 id="update-an-existing-persona-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|persona_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="update-an-existing-persona-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete an existing persona

<a id="opIddelete_persona_api_personas__persona_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/personas/{persona_id}', headers = headers)

print(r.json())

```

`DELETE /api/personas/{persona_id}`

<h3 id="delete-an-existing-persona-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|persona_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-an-existing-persona-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-projects">Projects</h1>

Endpoints common to all projects.

## Update the metadata for this project.

<a id="opIdupdate_project_metadata_api_project__project_id__metadata_put"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/project/{project_id}/metadata', headers = headers)

print(r.json())

```

`PUT /api/project/{project_id}/metadata`

> Body parameter

```json
false
```

<h3 id="update-the-metadata-for-this-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="update-the-metadata-for-this-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetch the gallery of all images for all projects.

<a id="opIdall_images_get_api_gallery_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/gallery', headers = headers)

print(r.json())

```

`GET /api/gallery`

<h3 id="fetch-the-gallery-of-all-images-for-all-projects.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|nsfw|query|any|false|none|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|count|query|any|false|Whether to return the total count or not.|

> Example responses

> 200 Response

```json
{
  "count": 0,
  "nodes": [],
  "page": 1
}
```

<h3 id="fetch-the-gallery-of-all-images-for-all-projects.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[Gallery](#schemagallery)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fetch the gallery of images for this project.

<a id="opIdget_images_wrapper_api_gallery_project__project_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/gallery/project/{project_id}', headers = headers)

print(r.json())

```

`GET /api/gallery/project/{project_id}`

<h3 id="fetch-the-gallery-of-images-for-this-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|
|nsfw|query|any|false|none|
|page|query|integer|false|none|
|limit|query|integer|false|none|
|count|query|any|false|Whether to return the total count or not.|

> Example responses

> 200 Response

```json
{
  "count": 0,
  "nodes": [],
  "page": 1
}
```

<h3 id="fetch-the-gallery-of-images-for-this-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[Gallery](#schemagallery)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Upload to the gallery of images.

<a id="opIdupload_image_api_gallery_upload_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/gallery/upload', headers = headers)

print(r.json())

```

`POST /api/gallery/upload`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "queue_length": 0,
  "primary_character_id": 0,
  "secondary_character_ids": [],
  "lorebook_id": 0,
  "primary_image_path": "",
  "user_owned": false,
  "nsfw_image": false,
  "description": "string",
  "prompt": {},
  "is_published": false,
  "comments_enabled": true,
  "is_done": true,
  "is_failed": false,
  "parent_image": "string",
  "item_id": "string",
  "uuid": "string",
  "info": {
    "width": 0,
    "height": 0,
    "dpi": 0,
    "z_index": 0,
    "opacity": 100,
    "duration": 0,
    "visible": true,
    "locked": false,
    "start_time": 0,
    "end_time": 0,
    "in_point": 0,
    "out_point": 0,
    "effects": {},
    "children": [
      null
    ]
  },
  "name": "string",
  "preview": "string"
}
```

<h3 id="upload-to-the-gallery-of-images.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[GalleryItem](#schemagalleryitem)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete an image from the gallery.

<a id="opIdwrapped_delete_image_api_gallery__uuid__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/gallery/{uuid}', headers = headers)

print(r.json())

```

`DELETE /api/gallery/{uuid}`

<h3 id="delete-an-image-from-the-gallery.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|
|projectId|query|any|false|Optional. The project to dissociate it from. Used when the requester does not own the image, but owns the associated project.|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-an-image-from-the-gallery.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Disable ratings for this project.

<a id="opIddisable_api_project__project_id__ratings_disable_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/project/{project_id}/ratings/disable', headers = headers)

print(r.json())

```

`POST /api/project/{project_id}/ratings/disable`

<h3 id="disable-ratings-for-this-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="disable-ratings-for-this-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Enable ratings for this project.

<a id="opIdenable_api_project__project_id__ratings_enable_post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/project/{project_id}/ratings/enable', headers = headers)

print(r.json())

```

`POST /api/project/{project_id}/ratings/enable`

<h3 id="enable-ratings-for-this-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="enable-ratings-for-this-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Make or update a rating for this project.

<a id="opIdrate_project_api_project__project_id__rate_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/project/{project_id}/rate', headers = headers)

print(r.json())

```

`POST /api/project/{project_id}/rate`

> Body parameter

```json
false
```

<h3 id="make-or-update-a-rating-for-this-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="make-or-update-a-rating-for-this-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Unfavorite a project.

<a id="opIddelete_proj_favorite_api_favorites__project_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/favorites/{project_id}', headers = headers)

print(r.json())

```

`DELETE /api/favorites/{project_id}`

<h3 id="unfavorite-a-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="unfavorite-a-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Favorite a project.

<a id="opIdproj_favorite_api_favorites__project_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/favorites/{project_id}', headers = headers)

print(r.json())

```

`POST /api/favorites/{project_id}`

<h3 id="favorite-a-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="favorite-a-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get favorited projects.

<a id="opIdmy_favorites_api_favorites_get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/favorites', headers = headers)

print(r.json())

```

`GET /api/favorites`

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-favorited-projects.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-favorited-projects.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Report a project.

<a id="opIdproj_report_api_reports_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/reports', headers = headers)

print(r.json())

```

`POST /api/reports`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="report-a-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Report a rating.

<a id="opIdproj_rating_report_api_ratings_reports_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/ratings/reports', headers = headers)

print(r.json())

```

`POST /api/ratings/reports`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="report-a-rating.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Delete a project permanently.

<a id="opIddelete_proj_api_project__project_id__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/project/{project_id}', headers = headers)

print(r.json())

```

`DELETE /api/project/{project_id}`

<h3 id="delete-a-project-permanently.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-a-project-permanently.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get forks for this project.

<a id="opIdproject_forks_forks_project__project_id__get"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/forks/project/{project_id}', headers = headers)

print(r.json())

```

`GET /forks/project/{project_id}`

<h3 id="get-forks-for-this-project.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|
|limit|query|integer|false|How many to return.|
|cursor|query|any|false|Pagination cursor.|
|nsfw|query|any|false|Whether to include NSFW items in the result.|
|nsfl|query|any|false|Whether to include NSFL items in the result. (Excluding NSFW also excludes NSFW, so this is typically unnecessary.)|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-forks-for-this-project.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-forks-for-this-project.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Fork a character (V2, better options).

<a id="opIdfork_project_v2_api_project__project_id__fork_v2_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/project/{project_id}/fork/v2', headers = headers)

print(r.json())

```

`POST /api/project/{project_id}/fork/v2`

> Body parameter

```json
false
```

<h3 id="fork-a-character-(v2,-better-options).-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="fork-a-character-(v2,-better-options).-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-unstable">Unstable</h1>

Endpoints under active development. May/will be unusable, broken, and/or change without warning. Best not to use these.

## Infer the emotion of a string.

<a id="opIdinfer_emotions_api_infer_emotion_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/infer/emotion', headers = headers)

print(r.json())

```

`POST /api/infer/emotion`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="infer-the-emotion-of-a-string.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="infer-the-emotion-of-a-string.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Add a tag to this entity.

<a id="opIdtag_entity_api_tags__project_id___tagname__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/api/tags/{project_id}/{tagname}', headers = headers)

print(r.json())

```

`POST /api/tags/{project_id}/{tagname}`

<h3 id="add-a-tag-to-this-entity.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|
|tagname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="add-a-tag-to-this-entity.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove a tag from this entity.

<a id="opIduntag_entity_api_tags__project_id___tagname__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/tags/{project_id}/{tagname}', headers = headers)

print(r.json())

```

`DELETE /api/tags/{project_id}/{tagname}`

<h3 id="remove-a-tag-from-this-entity.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project_id|path|integer|true|none|
|tagname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="remove-a-tag-from-this-entity.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Attempt to change your username.

<a id="opIdchange_my_username_api_self_username_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/self/username', headers = headers)

print(r.json())

```

`POST /api/self/username`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="attempt-to-change-your-username.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Check if username is taken.

<a id="opIdcheck_my_username_api_check_username_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/check/username', headers = headers)

print(r.json())

```

`POST /api/check/username`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="check-if-username-is-taken.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="success">
This operation does not require authentication
</aside>

## Delete a project permanently.

<a id="opIddelete_a_proj_full_api_project__namespace___username___pathname__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/project/{namespace}/{username}/{pathname}', headers = headers)

print(r.json())

```

`DELETE /api/project/{namespace}/{username}/{pathname}`

<h3 id="delete-a-project-permanently.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|namespace|path|undefined|true|none|
|username|path|string|true|none|
|pathname|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="delete-a-project-permanently.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create a list of suggested tags for a character.

<a id="opIdsuggest_tags_api_suggestions_tags_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/suggestions/tags', headers = headers)

print(r.json())

```

`POST /api/suggestions/tags`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-a-list-of-suggested-tags-for-a-character.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-a-list-of-suggested-tags-for-a-character.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Use to request that two tags be merged.

<a id="opIdsuggest_tags_merge_request_merge_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/request/merge', headers = headers)

print(r.json())

```

`POST /request/merge`

> Body parameter

```json
false
```

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="use-to-request-that-two-tags-be-merged.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Set active preset

<a id="opIdset_active_preset_presets_active__preset_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/presets/active/{preset_id}', headers = headers)

print(r.json())

```

`POST /presets/active/{preset_id}`

<h3 id="set-active-preset-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|preset_id|path|string|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="set-active-preset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="set-active-preset-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Get active preset

<a id="opIdget_preset_for_presets_active_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/presets/active', headers = headers)

print(r.json())

```

`POST /presets/active`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="get-active-preset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="get-active-preset-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Create extension

<a id="opIdcreate_extension_extensions_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/extensions', headers = headers)

print(r.json())

```

`POST /extensions`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-extension-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-extension-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Make a number of operations on files in a pseudo-atomic manner.

<a id="opIdupload_zip_file_extension__extension_id__upload_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('/extension/{extension_id}/upload', headers = headers)

print(r.json())

```

`POST /extension/{extension_id}/upload`

> Body parameter

```yaml
false

```

<h3 id="make-a-number-of-operations-on-files-in-a-pseudo-atomic-manner.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|extension_id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="make-a-number-of-operations-on-files-in-a-pseudo-atomic-manner.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-lore">Lore</h1>

Endpoints related to RAG and lorebooks.

## Make a RAG lore request.

<a id="opIdrequest_lore_lore_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/lore', headers = headers)

print(r.json())

```

`POST /lore`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="make-a-rag-lore-request.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="make-a-rag-lore-request.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Add an unstructured item.

<a id="opIdadd_lore_item_lore_item_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'multipart/form-data',
  'Accept': 'application/json'
}

r = requests.post('/lore/item', headers = headers)

print(r.json())

```

`POST /lore/item`

> Body parameter

```yaml
false

```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="add-an-unstructured-item.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="add-an-unstructured-item.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

## Remove an unstructured item.

<a id="opIdremove_lore_item_lore__owner_id__item__uuid__delete"></a>

> Code samples

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/lore/{owner_id}/item/{uuid}', headers = headers)

print(r.json())

```

`DELETE /lore/{owner_id}/item/{uuid}`

<h3 id="remove-an-unstructured-item.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|
|owner_id|path|integer|true|none|

> Example responses

> 200 Response

```json
{
  "message": "success",
  "success": true
}
```

<h3 id="remove-an-unstructured-item.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|[APIResponse](#schemaapiresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-presets">Presets</h1>

## Create preset

<a id="opIdcreate_preset_presets_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/presets', headers = headers)

print(r.json())

```

`POST /presets`

> Body parameter

```json
false
```

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="create-preset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="create-preset-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None, Authorization, None
</aside>

<h1 id="rostro-api-stages">Stages</h1>

## Fetch stage storage.

<a id="opIdstorage_fetch_api_storage_stage__stage_id__fetch_post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/api/storage/stage/{stage_id}/fetch', headers = headers)

print(r.json())

```

`POST /api/storage/stage/{stage_id}/fetch`

Experimental and only partially implemented.

> Body parameter

```json
false
```

<h3 id="fetch-stage-storage.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|stage_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="fetch-stage-storage.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="fetch-stage-storage.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Authorization
</aside>

## Update stage storage.

<a id="opIdstorage_updates_api_storage_stage__stage_id__post"></a>

> Code samples

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/api/storage/stage/{stage_id}', headers = headers)

print(r.json())

```

`POST /api/storage/stage/{stage_id}`

Experimental and only partially implemented.

> Body parameter

```json
false
```

<h3 id="update-stage-storage.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|stage_id|path|integer|true|none|

> Example responses

> 400 Response

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}
```

<h3 id="update-stage-storage.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[UserError](#schemausererror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[UserError](#schemausererror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[UserError](#schemausererror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[UserError](#schemausererror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Validation Error|[HTTPValidationError](#schemahttpvalidationerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[APIError](#schemaapierror)|

<h3 id="update-stage-storage.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
Authorization
</aside>

# Schemas

<h2 id="tocS_APIError">APIError</h2>
<!-- backwards compatibility -->
<a id="schemaapierror"></a>
<a id="schema_APIError"></a>
<a id="tocSapierror"></a>
<a id="tocsapierror"></a>

```json
{
  "error": "UNKNOWN",
  "message": "UNKNOWN",
  "type": "UNKNOWN",
  "code": "",
  "errorCode": 500,
  "param": {}
}

```

APIError

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|string|false|none|none|
|message|string|false|none|none|
|type|string|false|none|none|
|code|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errorCode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|param|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|any|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_APIResponse">APIResponse</h2>
<!-- backwards compatibility -->
<a id="schemaapiresponse"></a>
<a id="schema_APIResponse"></a>
<a id="tocSapiresponse"></a>
<a id="tocsapiresponse"></a>

```json
{
  "message": "success",
  "success": true
}

```

APIResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|any|false|none|Some message, usually just success.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|any|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_Annotation">Annotation</h2>
<!-- backwards compatibility -->
<a id="schemaannotation"></a>
<a id="schema_Annotation"></a>
<a id="tocSannotation"></a>
<a id="tocsannotation"></a>

```json
{
  "type": "url_citation",
  "url_citation": {
    "end_index": 0,
    "start_index": 0,
    "title": "string",
    "url": "string"
  }
}

```

Annotation

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|url_citation|[AnnotationURLCitation](#schemaannotationurlcitation)|true|none|none|

<h2 id="tocS_AnnotationURLCitation">AnnotationURLCitation</h2>
<!-- backwards compatibility -->
<a id="schemaannotationurlcitation"></a>
<a id="schema_AnnotationURLCitation"></a>
<a id="tocSannotationurlcitation"></a>
<a id="tocsannotationurlcitation"></a>

```json
{
  "end_index": 0,
  "start_index": 0,
  "title": "string",
  "url": "string"
}

```

AnnotationURLCitation

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|end_index|integer|true|none|none|
|start_index|integer|true|none|none|
|title|string|true|none|none|
|url|string|true|none|none|

<h2 id="tocS_AspectRatio">AspectRatio</h2>
<!-- backwards compatibility -->
<a id="schemaaspectratio"></a>
<a id="schema_AspectRatio"></a>
<a id="tocSaspectratio"></a>
<a id="tocsaspectratio"></a>

```json
"w1h1"

```

AspectRatio

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AspectRatio|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|AspectRatio|w1h1|
|AspectRatio|w1h2|
|AspectRatio|w2h1|
|AspectRatio|w16h9|
|AspectRatio|w21h9|
|AspectRatio|w2h3|
|AspectRatio|w3h2|
|AspectRatio|w3h4|
|AspectRatio|w4h3|
|AspectRatio|w4h5|
|AspectRatio|w5h4|
|AspectRatio|w9h16|
|AspectRatio|w9h21|

<h2 id="tocS_Audio">Audio</h2>
<!-- backwards compatibility -->
<a id="schemaaudio"></a>
<a id="schema_Audio"></a>
<a id="tocSaudio"></a>
<a id="tocsaudio"></a>

```json
{
  "id": "string"
}

```

Audio

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|

<h2 id="tocS_BaseModel">BaseModel</h2>
<!-- backwards compatibility -->
<a id="schemabasemodel"></a>
<a id="schema_BaseModel"></a>
<a id="tocSbasemodel"></a>
<a id="tocsbasemodel"></a>

```json
{}

```

BaseModel

### Properties

*None*

<h2 id="tocS_Body_speech_to_text_stt_post">Body_speech_to_text_stt_post</h2>
<!-- backwards compatibility -->
<a id="schemabody_speech_to_text_stt_post"></a>
<a id="schema_Body_speech_to_text_stt_post"></a>
<a id="tocSbody_speech_to_text_stt_post"></a>
<a id="tocsbody_speech_to_text_stt_post"></a>

```json
{
  "sample": "string"
}

```

Body_speech_to_text_stt_post

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sample|string(binary)|true|none|The sample audio file. Recognized formats: 'mp3', 'flv', 'ogg', 'wav', 'raw', 'm4a', 'mp4', 'wave'.|

<h2 id="tocS_Body_voice_clone_voice_clone_post">Body_voice_clone_voice_clone_post</h2>
<!-- backwards compatibility -->
<a id="schemabody_voice_clone_voice_clone_post"></a>
<a id="schema_Body_voice_clone_voice_clone_post"></a>
<a id="tocSbody_voice_clone_voice_clone_post"></a>
<a id="tocsbody_voice_clone_voice_clone_post"></a>

```json
{
  "sample": "string",
  "transcript": "A wizard's job is to vex chumps quickly in fog.",
  "model": "all",
  "reference_text": "string",
  "character_id_str": null,
  "name": "Deep Male",
  "existing_id": null
}

```

Body_voice_clone_voice_clone_post

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sample|any|false|none|The sample audio file. Recognized formats: 'mp3', 'flv', 'ogg', 'wav', 'raw', 'm4a', 'mp4', 'wave'.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string(binary)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transcript|any|false|none|The text to read out for the example output(s).|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|false|none|Which model to use. all, or None for the default.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reference_text|any|false|none|Optional. The text that is being said in the sample audio. If not given, stt will be done on the example audio to get this.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|character_id_str|any|false|none|If given, the voice of this character will be set to the voice.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|any|false|none|The name of the voice.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|existing_id|any|false|none|The id of the existing voice.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_ChatCompletion">ChatCompletion</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletion"></a>
<a id="schema_ChatCompletion"></a>
<a id="tocSchatcompletion"></a>
<a id="tocschatcompletion"></a>

```json
{
  "id": "string",
  "choices": [],
  "created": 0,
  "model": "string",
  "object": "chat.completion",
  "service_tier": "auto",
  "system_fingerprint": "string",
  "usage": {}
}

```

ChatCompletion

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|choices|[[Choice](#schemachoice)]|true|none|none|
|created|integer|true|none|none|
|model|string|true|none|none|
|object|string|true|none|none|
|service_tier|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|system_fingerprint|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|usage|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[CompletionUsage](#schemacompletionusage)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|auto|
|*anonymous*|default|
|*anonymous*|flex|
|*anonymous*|scale|

<h2 id="tocS_ChatCompletionAssistantMessageParam">ChatCompletionAssistantMessageParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionassistantmessageparam"></a>
<a id="schema_ChatCompletionAssistantMessageParam"></a>
<a id="tocSchatcompletionassistantmessageparam"></a>
<a id="tocschatcompletionassistantmessageparam"></a>

```json
{
  "role": "assistant",
  "audio": {
    "id": "string"
  },
  "content": "string",
  "function_call": {
    "arguments": "string",
    "name": "string"
  },
  "name": "string",
  "refusal": "string",
  "tool_calls": [
    {
      "id": "string",
      "function": {
        "arguments": "string",
        "name": "string"
      },
      "type": "function"
    }
  ]
}

```

ChatCompletionAssistantMessageParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|role|string|true|none|none|
|audio|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Audio](#schemaaudio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[anyOf]|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[ChatCompletionContentPartRefusalParam](#schemachatcompletioncontentpartrefusalparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|function_call|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[FunctionCall-Input](#schemafunctioncall-input)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|refusal|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tool_calls|[[ChatCompletionMessageToolCallParam](#schemachatcompletionmessagetoolcallparam)]|false|none|none|

<h2 id="tocS_ChatCompletionAudio">ChatCompletionAudio</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionaudio"></a>
<a id="schema_ChatCompletionAudio"></a>
<a id="tocSchatcompletionaudio"></a>
<a id="tocschatcompletionaudio"></a>

```json
{
  "id": "string",
  "data": "string",
  "expires_at": 0,
  "transcript": "string"
}

```

ChatCompletionAudio

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|data|string|true|none|none|
|expires_at|integer|true|none|none|
|transcript|string|true|none|none|

<h2 id="tocS_ChatCompletionAudioParam">ChatCompletionAudioParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionaudioparam"></a>
<a id="schema_ChatCompletionAudioParam"></a>
<a id="tocSchatcompletionaudioparam"></a>
<a id="tocschatcompletionaudioparam"></a>

```json
{
  "format": "wav",
  "voice": "string"
}

```

ChatCompletionAudioParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|format|string|true|none|none|
|voice|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|format|wav|
|format|aac|
|format|mp3|
|format|flac|
|format|opus|
|format|pcm16|
|*anonymous*|alloy|
|*anonymous*|ash|
|*anonymous*|ballad|
|*anonymous*|coral|
|*anonymous*|echo|
|*anonymous*|fable|
|*anonymous*|onyx|
|*anonymous*|nova|
|*anonymous*|sage|
|*anonymous*|shimmer|
|*anonymous*|verse|

<h2 id="tocS_ChatCompletionContentPartImageParam">ChatCompletionContentPartImageParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletioncontentpartimageparam"></a>
<a id="schema_ChatCompletionContentPartImageParam"></a>
<a id="tocSchatcompletioncontentpartimageparam"></a>
<a id="tocschatcompletioncontentpartimageparam"></a>

```json
{
  "image_url": {
    "url": "string",
    "detail": "auto"
  },
  "type": "image_url"
}

```

ChatCompletionContentPartImageParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|image_url|[ImageURL](#schemaimageurl)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_ChatCompletionContentPartInputAudioParam">ChatCompletionContentPartInputAudioParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletioncontentpartinputaudioparam"></a>
<a id="schema_ChatCompletionContentPartInputAudioParam"></a>
<a id="tocSchatcompletioncontentpartinputaudioparam"></a>
<a id="tocschatcompletioncontentpartinputaudioparam"></a>

```json
{
  "input_audio": {
    "data": "string",
    "format": "wav"
  },
  "type": "input_audio"
}

```

ChatCompletionContentPartInputAudioParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|input_audio|[InputAudio](#schemainputaudio)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_ChatCompletionContentPartRefusalParam">ChatCompletionContentPartRefusalParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletioncontentpartrefusalparam"></a>
<a id="schema_ChatCompletionContentPartRefusalParam"></a>
<a id="tocSchatcompletioncontentpartrefusalparam"></a>
<a id="tocschatcompletioncontentpartrefusalparam"></a>

```json
{
  "refusal": "string",
  "type": "refusal"
}

```

ChatCompletionContentPartRefusalParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|refusal|string|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_ChatCompletionContentPartTextParam">ChatCompletionContentPartTextParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletioncontentparttextparam"></a>
<a id="schema_ChatCompletionContentPartTextParam"></a>
<a id="tocSchatcompletioncontentparttextparam"></a>
<a id="tocschatcompletioncontentparttextparam"></a>

```json
{
  "text": "string",
  "type": "text"
}

```

ChatCompletionContentPartTextParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|text|string|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_ChatCompletionDeveloperMessageParam">ChatCompletionDeveloperMessageParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletiondevelopermessageparam"></a>
<a id="schema_ChatCompletionDeveloperMessageParam"></a>
<a id="tocSchatcompletiondevelopermessageparam"></a>
<a id="tocschatcompletiondevelopermessageparam"></a>

```json
{
  "content": "string",
  "role": "developer",
  "name": "string"
}

```

ChatCompletionDeveloperMessageParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)]|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|role|string|true|none|none|
|name|string|false|none|none|

<h2 id="tocS_ChatCompletionFunctionCallOptionParam">ChatCompletionFunctionCallOptionParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionfunctioncalloptionparam"></a>
<a id="schema_ChatCompletionFunctionCallOptionParam"></a>
<a id="tocSchatcompletionfunctioncalloptionparam"></a>
<a id="tocschatcompletionfunctioncalloptionparam"></a>

```json
{
  "name": "string"
}

```

ChatCompletionFunctionCallOptionParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|

<h2 id="tocS_ChatCompletionFunctionMessageParam">ChatCompletionFunctionMessageParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionfunctionmessageparam"></a>
<a id="schema_ChatCompletionFunctionMessageParam"></a>
<a id="tocSchatcompletionfunctionmessageparam"></a>
<a id="tocschatcompletionfunctionmessageparam"></a>

```json
{
  "content": "string",
  "name": "string",
  "role": "function"
}

```

ChatCompletionFunctionMessageParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|role|string|true|none|none|

<h2 id="tocS_ChatCompletionMessageToolCallParam">ChatCompletionMessageToolCallParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionmessagetoolcallparam"></a>
<a id="schema_ChatCompletionMessageToolCallParam"></a>
<a id="tocSchatcompletionmessagetoolcallparam"></a>
<a id="tocschatcompletionmessagetoolcallparam"></a>

```json
{
  "id": "string",
  "function": {
    "arguments": "string",
    "name": "string"
  },
  "type": "function"
}

```

ChatCompletionMessageToolCallParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|function|[openai__types__chat__chat_completion_message_tool_call_param__Function](#schemaopenai__types__chat__chat_completion_message_tool_call_param__function)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_ChatCompletionNamedFunction">ChatCompletionNamedFunction</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionnamedfunction"></a>
<a id="schema_ChatCompletionNamedFunction"></a>
<a id="tocSchatcompletionnamedfunction"></a>
<a id="tocschatcompletionnamedfunction"></a>

```json
{
  "name": "string"
}

```

ChatCompletionNamedFunction

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|

<h2 id="tocS_ChatCompletionPredictionContentParam">ChatCompletionPredictionContentParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionpredictioncontentparam"></a>
<a id="schema_ChatCompletionPredictionContentParam"></a>
<a id="tocSchatcompletionpredictioncontentparam"></a>
<a id="tocschatcompletionpredictioncontentparam"></a>

```json
{
  "content": "string",
  "type": "content"
}

```

ChatCompletionPredictionContentParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)]|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|

<h2 id="tocS_ChatCompletionStreamOptionsParam">ChatCompletionStreamOptionsParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionstreamoptionsparam"></a>
<a id="schema_ChatCompletionStreamOptionsParam"></a>
<a id="tocSchatcompletionstreamoptionsparam"></a>
<a id="tocschatcompletionstreamoptionsparam"></a>

```json
{
  "include_usage": true
}

```

ChatCompletionStreamOptionsParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|include_usage|boolean|false|none|none|

<h2 id="tocS_ChatCompletionSystemMessageParam">ChatCompletionSystemMessageParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionsystemmessageparam"></a>
<a id="schema_ChatCompletionSystemMessageParam"></a>
<a id="tocSchatcompletionsystemmessageparam"></a>
<a id="tocschatcompletionsystemmessageparam"></a>

```json
{
  "content": "string",
  "role": "system",
  "name": "string"
}

```

ChatCompletionSystemMessageParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)]|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|role|string|true|none|none|
|name|string|false|none|none|

<h2 id="tocS_ChatCompletionToolMessageParam">ChatCompletionToolMessageParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletiontoolmessageparam"></a>
<a id="schema_ChatCompletionToolMessageParam"></a>
<a id="tocSchatcompletiontoolmessageparam"></a>
<a id="tocschatcompletiontoolmessageparam"></a>

```json
{
  "content": "string",
  "role": "tool",
  "tool_call_id": "string"
}

```

ChatCompletionToolMessageParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)]|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|role|string|true|none|none|
|tool_call_id|string|true|none|none|

<h2 id="tocS_ChatCompletionToolParam">ChatCompletionToolParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletiontoolparam"></a>
<a id="schema_ChatCompletionToolParam"></a>
<a id="tocSchatcompletiontoolparam"></a>
<a id="tocschatcompletiontoolparam"></a>

```json
{
  "function": {
    "name": "string",
    "description": "string",
    "parameters": {},
    "strict": true
  },
  "type": "function"
}

```

ChatCompletionToolParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|function|[openai__types__shared_params__function_definition__FunctionDefinition](#schemaopenai__types__shared_params__function_definition__functiondefinition)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_ChatCompletionToolsParam">ChatCompletionToolsParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletiontoolsparam"></a>
<a id="schema_ChatCompletionToolsParam"></a>
<a id="tocSchatcompletiontoolsparam"></a>
<a id="tocschatcompletiontoolsparam"></a>

```json
{
  "type": "function",
  "function": {
    "name": "string",
    "description": "string",
    "parameters": {}
  }
}

```

ChatCompletionToolsParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|function|[vllm__entrypoints__openai__protocol__FunctionDefinition](#schemavllm__entrypoints__openai__protocol__functiondefinition)|true|none|none|

<h2 id="tocS_ChatCompletionUserMessageParam">ChatCompletionUserMessageParam</h2>
<!-- backwards compatibility -->
<a id="schemachatcompletionusermessageparam"></a>
<a id="schema_ChatCompletionUserMessageParam"></a>
<a id="tocSchatcompletionusermessageparam"></a>
<a id="tocschatcompletionusermessageparam"></a>

```json
{
  "content": "string",
  "role": "user",
  "name": "string"
}

```

ChatCompletionUserMessageParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|content|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[anyOf]|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[ChatCompletionContentPartTextParam](#schemachatcompletioncontentparttextparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[ChatCompletionContentPartImageParam](#schemachatcompletioncontentpartimageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[ChatCompletionContentPartInputAudioParam](#schemachatcompletioncontentpartinputaudioparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[File](#schemafile)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|role|string|true|none|none|
|name|string|false|none|none|

<h2 id="tocS_DeletionRequest">DeletionRequest</h2>
<!-- backwards compatibility -->
<a id="schemadeletionrequest"></a>
<a id="schema_DeletionRequest"></a>
<a id="tocSdeletionrequest"></a>
<a id="tocsdeletionrequest"></a>

```json
{
  "uuids": []
}

```

DeletionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuids|[string]|false|none|none|

<h2 id="tocS_DeletionResponse">DeletionResponse</h2>
<!-- backwards compatibility -->
<a id="schemadeletionresponse"></a>
<a id="schema_DeletionResponse"></a>
<a id="tocSdeletionresponse"></a>
<a id="tocsdeletionresponse"></a>

```json
{
  "successes": [],
  "failures": []
}

```

DeletionResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|successes|[string]|false|none|none|
|failures|[string]|false|none|none|

<h2 id="tocS_File">File</h2>
<!-- backwards compatibility -->
<a id="schemafile"></a>
<a id="schema_File"></a>
<a id="tocSfile"></a>
<a id="tocsfile"></a>

```json
{
  "file": {
    "file_data": "string",
    "file_id": "string",
    "filename": "string"
  },
  "type": "file"
}

```

File

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|file|[FileFile](#schemafilefile)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_FileFile">FileFile</h2>
<!-- backwards compatibility -->
<a id="schemafilefile"></a>
<a id="schema_FileFile"></a>
<a id="tocSfilefile"></a>
<a id="tocsfilefile"></a>

```json
{
  "file_data": "string",
  "file_id": "string",
  "filename": "string"
}

```

FileFile

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|file_data|string|false|none|none|
|file_id|string|false|none|none|
|filename|string|false|none|none|

<h2 id="tocS_FoleyRequest">FoleyRequest</h2>
<!-- backwards compatibility -->
<a id="schemafoleyrequest"></a>
<a id="schema_FoleyRequest"></a>
<a id="tocSfoleyrequest"></a>
<a id="tocsfoleyrequest"></a>

```json
{
  "duration": 4,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "two starships are fighting in space with laser cannons",
  "negative_prompt": "distorted",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5
}

```

FoleyRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|duration|any|false|none|The desired duration, in seconds, of the video, sound effect, or other media. Does not affect music length.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_FunctionCall-Input">FunctionCall-Input</h2>
<!-- backwards compatibility -->
<a id="schemafunctioncall-input"></a>
<a id="schema_FunctionCall-Input"></a>
<a id="tocSfunctioncall-input"></a>
<a id="tocsfunctioncall-input"></a>

```json
{
  "arguments": "string",
  "name": "string"
}

```

FunctionCall

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|arguments|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocS_FunctionCall-Output">FunctionCall-Output</h2>
<!-- backwards compatibility -->
<a id="schemafunctioncall-output"></a>
<a id="schema_FunctionCall-Output"></a>
<a id="tocSfunctioncall-output"></a>
<a id="tocsfunctioncall-output"></a>

```json
{
  "arguments": "string",
  "name": "string"
}

```

FunctionCall

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|arguments|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocS_Gallery">Gallery</h2>
<!-- backwards compatibility -->
<a id="schemagallery"></a>
<a id="schema_Gallery"></a>
<a id="tocSgallery"></a>
<a id="tocsgallery"></a>

```json
{
  "count": 0,
  "nodes": [],
  "page": 1
}

```

Gallery

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|count|integer|false|none|The number of results returned.|
|nodes|[[GalleryItem](#schemagalleryitem)]|false|none|Images/screencaps related to the project.|
|page|integer|false|none|The page of results returned.|

<h2 id="tocS_GalleryItem">GalleryItem</h2>
<!-- backwards compatibility -->
<a id="schemagalleryitem"></a>
<a id="schema_GalleryItem"></a>
<a id="tocSgalleryitem"></a>
<a id="tocsgalleryitem"></a>

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "queue_length": 0,
  "primary_character_id": 0,
  "secondary_character_ids": [],
  "lorebook_id": 0,
  "primary_image_path": "",
  "user_owned": false,
  "nsfw_image": false,
  "description": "string",
  "prompt": {},
  "is_published": false,
  "comments_enabled": true,
  "is_done": true,
  "is_failed": false,
  "parent_image": "string",
  "item_id": "string",
  "uuid": "string",
  "info": {
    "width": 0,
    "height": 0,
    "dpi": 0,
    "z_index": 0,
    "opacity": 100,
    "duration": 0,
    "visible": true,
    "locked": false,
    "start_time": 0,
    "end_time": 0,
    "in_point": 0,
    "out_point": 0,
    "effects": {},
    "children": [
      null
    ]
  },
  "name": "string",
  "preview": "string"
}

```

GalleryItem

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|generation_uuid|any|false|none|The unique identity of the generation, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cost|any|false|none|Cost in credits, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|queue_length|any|false|none|The queue length.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|primary_character_id|any|false|none|The id of the main character used in the image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|secondary_character_ids|[integer]|false|none|The ids of the other characters used in the image.|
|lorebook_id|any|false|none|The id of the lorebook used in the image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|primary_image_path|string|false|none|The path where the image is located.|
|user_owned|boolean|false|none|Whether the image belongs to the user.|
|nsfw_image|any|false|none|Whether the image is NSFW.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|any|false|none|A generated description of the image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|Prompt metadata.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|any|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|is_published|boolean|false|none|Whether this has been published.|
|comments_enabled|boolean|false|none|Whether this has comments enabled.|
|is_done|boolean|false|none|Whether this generation is completed.|
|is_failed|boolean|false|none|Whether this generation is failed.|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|string|false|none|The unique identity of the image.|
|info|any|false|none|The project info.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[LayerInfo](#schemalayerinfo)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|any|false|none|Optional. Layer name.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|preview|any|false|none|Optional. Layer preview.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_GenerationRequest">GenerationRequest</h2>
<!-- backwards compatibility -->
<a id="schemagenerationrequest"></a>
<a id="schema_GenerationRequest"></a>
<a id="tocSgenerationrequest"></a>
<a id="tocsgenerationrequest"></a>

```json
{
  "lyrics": "string",
  "genre": "automatic",
  "music_type": "mixed",
  "duration": 4,
  "end_image": "string",
  "fps": 8,
  "i2i_type": "edit",
  "mask_image": "string",
  "preserve_transparency": true,
  "init_images": [],
  "octree_resolution": 384,
  "texture_size": 1024,
  "output_type": "glb",
  "speed": "normal",
  "do_texture": true,
  "do_autorig": false,
  "autorig_type": "unknown",
  "transcript": "A wizard's job is to vex chumps quickly in fog.",
  "voice": "bright_female_20s",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "aspect_ratio": "w1h1",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "generation_type": "text_to_speech"
}

```

GenerationRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lyrics|any|false|none|The song's lyrics, if relevant. Each part should begin with a structure tag ([verse], [chorus], [bridge], [intro-short], [intro-medium], [intro-long], [outro-short], [outro-medium], [outro-long], [inst-short], [inst-medium], [inst-long], [silence]) and a newline, and end with two newlines. These segments should not contain lyrics: ([intro], [intro-short], [intro-medium], [inst], [inst-short], [inst-medium], [outro], [outro-short], [outro-medium])|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|genre|any|false|none|The musical genre.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[MusicGenre](#schemamusicgenre)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|music_type|any|false|none|Whether to make instrumental music, only vocals, or a fully mixed song. If requesting 'vocals' or 'mixed', lyrics MUST be provided.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[MusicGenType](#schemamusicgentype)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|duration|any|false|none|The desired duration, in seconds, of the video, sound effect, or other media. Does not affect music length.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|end_image|any|false|none|The final frame image for image-to-video, as a URL or base64 string. If you want a video to loop, give the same start and end image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fps|any|false|none|The number of frames per second.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|i2i_type|any|false|none|Whether to do edit-based i2i ('edit'), edge-based i2i ('canny'), or face/person-based i2i ('face'). Edit preserves the most of the structure and style of the original image; canny preserves the image's structure, but not its style; face preserves neither, but keeps the visual identity/face of a person in the source image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[I2IType](#schemai2itype)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mask_image|any|false|none|The mask image, as a URL or base64 string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|preserve_transparency|any|false|none|If given, the transparency of the non-mask image(s) will be preserved. Useful if your input image has clear parts and you want to keep them clear.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_images|any|false|none|Optional. Reference images. A list of base64 image string(s) and/or URL(s). If not provided, text-to-image will be done on the text prompt. Because of this, it is recommended to use text-to-image first and select the preferred appearance.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|octree_resolution|any|false|none|The octree resolution to generate for 3D models. Lower resolutions will generate faster, but be less detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|texture_size|any|false|none|The pixel width of the generated texture for 3D models. Lower resolutions will generate faster, but be less detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|output_type|any|false|none|What file type to output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Output3DType](#schemaoutput3dtype)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|speed|any|false|none|Enabling turbo will make generations much faster but with slightly worse output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Speed](#schemaspeed)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|do_texture|any|false|none|Whether to generate a texture as well.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|do_autorig|any|false|none|Whether to generate a rig as well.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|autorig_type|any|false|none|The type of rigging to use. 'Bipedal' is common and will create much better rigs for humans and other bipeds. The 'quadruped' option is best for non-anthropomorphic animals. If you aren't sure which to pick, use 'unknown'.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[RigType](#schemarigtype)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transcript|any|false|none|The text to read out.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|voice|any|false|none|Select a voice to use.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Voice](#schemavoice)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|generation_type|[GenerationType](#schemagenerationtype)|false|none|The type of media to generate.|

<h2 id="tocS_GenerationType">GenerationType</h2>
<!-- backwards compatibility -->
<a id="schemagenerationtype"></a>
<a id="schema_GenerationType"></a>
<a id="tocSgenerationtype"></a>
<a id="tocsgenerationtype"></a>

```json
"text_to_speech"

```

GenerationType

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|GenerationType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|GenerationType|text_to_speech|
|GenerationType|text_to_image|
|GenerationType|text_to_video|
|GenerationType|image_to_image|
|GenerationType|image_to_video|
|GenerationType|text_to_sfx|
|GenerationType|text_to_music|
|GenerationType|text_to_3d|
|GenerationType|image_to_3d|

<h2 id="tocS_GuidedDecodingParams">GuidedDecodingParams</h2>
<!-- backwards compatibility -->
<a id="schemaguideddecodingparams"></a>
<a id="schema_GuidedDecodingParams"></a>
<a id="tocSguideddecodingparams"></a>
<a id="tocsguideddecodingparams"></a>

```json
{
  "json": "string",
  "regex": "string",
  "choice": [
    "string"
  ],
  "grammar": "string",
  "json_object": true,
  "backend": "string",
  "backend_was_auto": false,
  "disable_fallback": false,
  "disable_any_whitespace": false,
  "disable_additional_properties": false,
  "whitespace_pattern": "string",
  "structural_tag": "string"
}

```

GuidedDecodingParams

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|json|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|regex|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|choice|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|grammar|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|json_object|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|backend|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|backend_was_auto|boolean|false|none|none|
|disable_fallback|boolean|false|none|none|
|disable_any_whitespace|boolean|false|none|none|
|disable_additional_properties|boolean|false|none|none|
|whitespace_pattern|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|structural_tag|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_HTTPValidationError">HTTPValidationError</h2>
<!-- backwards compatibility -->
<a id="schemahttpvalidationerror"></a>
<a id="schema_HTTPValidationError"></a>
<a id="tocShttpvalidationerror"></a>
<a id="tocshttpvalidationerror"></a>

```json
{
  "detail": [
    {
      "loc": [
        "string"
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}

```

HTTPValidationError

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|detail|[[ValidationError](#schemavalidationerror)]|false|none|none|

<h2 id="tocS_HistoryRequest">HistoryRequest</h2>
<!-- backwards compatibility -->
<a id="schemahistoryrequest"></a>
<a id="schema_HistoryRequest"></a>
<a id="tocShistoryrequest"></a>
<a id="tocshistoryrequest"></a>

```json
{
  "first": 10,
  "generation_uuids": null,
  "uuids": null,
  "generated_only": false,
  "media_types": [
    "text_to_speech"
  ],
  "cursor": "string",
  "order_by": "created_at",
  "asc": true,
  "return_raw": false
}

```

HistoryRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|first|integer|false|none|The number of the results to get.|
|generation_uuids|any|false|none|If given, only these generation UUIDs will be fetched.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuids|any|false|none|If given, only these media UUIDs will be fetched.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|generated_only|any|false|none|Whether to return only generated images or not. If false, uploads like source images for image-to-image will be included.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|media_types|any|false|none|What generation types to fetch. If given, other types will be excluded.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[[GenerationType](#schemagenerationtype)]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cursor|any|false|none|The cursor to use to fetch the next page.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|order_by|any|false|none|What field to order results by. Defaults to created_at.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[OrderMediaBy](#schemaordermediaby)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|asc|any|false|none|Whether to sort results in ascending order. Defaults to false.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|return_raw|any|false|none|If true, the raw media files will be returned also, in base64 format.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_I2IType">I2IType</h2>
<!-- backwards compatibility -->
<a id="schemai2itype"></a>
<a id="schema_I2IType"></a>
<a id="tocSi2itype"></a>
<a id="tocsi2itype"></a>

```json
"canny"

```

I2IType

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|I2IType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|I2IType|canny|
|I2IType|face|
|I2IType|edit|

<h2 id="tocS_ImageToImageRequest">ImageToImageRequest</h2>
<!-- backwards compatibility -->
<a id="schemaimagetoimagerequest"></a>
<a id="schema_ImageToImageRequest"></a>
<a id="tocSimagetoimagerequest"></a>
<a id="tocsimagetoimagerequest"></a>

```json
{
  "i2i_type": "edit",
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "type": "edit"
}

```

ImageToImageRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|i2i_type|any|false|none|Whether to do edit-based i2i ('edit'), edge-based i2i ('canny'), or face/person-based i2i ('face'). Edit preserves the most of the structure and style of the original image; canny preserves the image's structure, but not its style; face preserves neither, but keeps the visual identity/face of a person in the source image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[I2IType](#schemai2itype)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|any|false|none|Whether to do edit-based i2i ('edit'), edge-based i2i ('canny'), or face/person-based i2i ('face'). Edit preserves the most of the structure and style of the original image; canny preserves the image's structure, but not its style; face preserves neither, but keeps the visual identity/face of a person in the source image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[I2IType](#schemai2itype)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_ImageURL">ImageURL</h2>
<!-- backwards compatibility -->
<a id="schemaimageurl"></a>
<a id="schema_ImageURL"></a>
<a id="tocSimageurl"></a>
<a id="tocsimageurl"></a>

```json
{
  "url": "string",
  "detail": "auto"
}

```

ImageURL

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|string|true|none|none|
|detail|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|detail|auto|
|detail|low|
|detail|high|

<h2 id="tocS_ImagineChangeRequest">ImagineChangeRequest</h2>
<!-- backwards compatibility -->
<a id="schemaimaginechangerequest"></a>
<a id="schema_ImagineChangeRequest"></a>
<a id="tocSimaginechangerequest"></a>
<a id="tocsimaginechangerequest"></a>

```json
{
  "description": "string",
  "comments_enabled": true,
  "duration": 0,
  "width": 0,
  "height": 0,
  "dpi": 0,
  "z_index": 0,
  "opacity": 0,
  "visible": true,
  "locked": true,
  "start_time": 0,
  "end_time": 0,
  "in_point": 0,
  "out_point": 0,
  "name": "string",
  "parent_image": "string",
  "is_published": true,
  "is_nsfw": true,
  "is_nsfl": true,
  "imagination_type": "string",
  "image": "string",
  "preview": "string",
  "effects": {}
}

```

ImagineChangeRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|any|false|none|Description|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|comments_enabled|any|false|none|Are comments enabled|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|duration|any|false|none|Duration|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|Width|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|Height|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|dpi|any|false|none|DPI|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|z_index|any|false|none|Z Index|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|opacity|any|false|none|Opacity|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|visible|any|false|none|Visible|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|locked|any|false|none|Locked|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|start_time|any|false|none|Start time|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|end_time|any|false|none|End time|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|in_point|any|false|none|In time|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|out_point|any|false|none|Out time|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|any|false|none|Image Name|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|parent_image|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|is_published|any|false|none|Is published|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|is_nsfw|any|false|none|Is NSFW|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|is_nsfl|any|false|none|Is NSFL|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|imagination_type|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|image|any|false|none|Image path or base64|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|preview|any|false|none|Preview|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|effects|any|false|none|Effects|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|any|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_ImagineCosts">ImagineCosts</h2>
<!-- backwards compatibility -->
<a id="schemaimaginecosts"></a>
<a id="schema_ImagineCosts"></a>
<a id="tocSimaginecosts"></a>
<a id="tocsimaginecosts"></a>

```json
{
  "costs": {}
}

```

ImagineCosts

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|costs|object|false|none|The number of credits per endpoint.|
|» **additionalProperties**|integer|false|none|none|

<h2 id="tocS_ImaginedItem">ImaginedItem</h2>
<!-- backwards compatibility -->
<a id="schemaimagineditem"></a>
<a id="schema_ImaginedItem"></a>
<a id="tocSimagineditem"></a>
<a id="tocsimagineditem"></a>

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "primary_media_url": "string",
  "description": "string",
  "prompt": {},
  "is_done": true,
  "is_failed": false,
  "uuid": "string",
  "info": {
    "width": 0,
    "height": 0,
    "dpi": 0,
    "z_index": 0,
    "opacity": 100,
    "duration": 0,
    "visible": true,
    "locked": false,
    "start_time": 0,
    "end_time": 0,
    "in_point": 0,
    "out_point": 0,
    "effects": {},
    "children": [
      null
    ]
  },
  "secondary_media_urls": {
    "property1": "string",
    "property2": "string"
  },
  "error": {
    "reason": "unknown",
    "location": "string"
  },
  "note": "string"
}

```

ImaginedItem

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|generation_uuid|any|false|none|The unique identity of the generation, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cost|any|false|none|Cost in credits, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|primary_media_url|any|false|none|The URL where the generated media is located. If this value is non-null, use it to show clickable link(s) in your response with a relevant call-to-action like this: [Watch the Video](put the primary_media_url here).|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|any|false|none|A generated description of the item.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|Prompt metadata.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|any|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|is_done|boolean|false|none|Whether this generation is completed.|
|is_failed|boolean|false|none|Whether this generation is failed.|
|uuid|any|false|none|The unique identity of the media.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|info|any|false|none|The layer info, if this is part of a project.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[LayerInfo](#schemalayerinfo)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|secondary_media_urls|any|false|none|If this generated a compound asset like a 3D model, the URLS of other components of the asset, like texture images, will be here.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|any|false|none|If there was an error, the reason may be here.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Rejection](#schemarejection)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|note|any|false|none|A note, typically for the LLM.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_ImaginedItems">ImaginedItems</h2>
<!-- backwards compatibility -->
<a id="schemaimagineditems"></a>
<a id="schema_ImaginedItems"></a>
<a id="tocSimagineditems"></a>
<a id="tocsimagineditems"></a>

```json
{
  "items": [],
  "previous_cursor": "string",
  "cursor": "string"
}

```

ImaginedItems

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[[ImaginedItem](#schemaimagineditem)]|false|none|The results.|
|previous_cursor|any|false|none|The cursor of the previous fetched page, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cursor|any|false|none|The cursor to use to fetch the next page. If not given, there are no more results.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_InpaintRequest">InpaintRequest</h2>
<!-- backwards compatibility -->
<a id="schemainpaintrequest"></a>
<a id="schema_InpaintRequest"></a>
<a id="tocSinpaintrequest"></a>
<a id="tocsinpaintrequest"></a>

```json
{
  "mask_image": "string",
  "preserve_transparency": true,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5
}

```

InpaintRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mask_image|any|false|none|The mask image, as a URL or base64 string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|preserve_transparency|any|false|none|If given, the transparency of the non-mask image(s) will be preserved. Useful if your input image has clear parts and you want to keep them clear.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_InputAudio">InputAudio</h2>
<!-- backwards compatibility -->
<a id="schemainputaudio"></a>
<a id="schema_InputAudio"></a>
<a id="tocSinputaudio"></a>
<a id="tocsinputaudio"></a>

```json
{
  "data": "string",
  "format": "wav"
}

```

InputAudio

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|string|true|none|none|
|format|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|format|wav|
|format|mp3|

<h2 id="tocS_JSONSchema">JSONSchema</h2>
<!-- backwards compatibility -->
<a id="schemajsonschema"></a>
<a id="schema_JSONSchema"></a>
<a id="tocSjsonschema"></a>
<a id="tocsjsonschema"></a>

```json
{
  "name": "string",
  "description": "string",
  "schema": {},
  "strict": true
}

```

JSONSchema

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|description|string|false|none|none|
|schema|object|false|none|none|
|strict|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_JsonSchemaResponseFormat">JsonSchemaResponseFormat</h2>
<!-- backwards compatibility -->
<a id="schemajsonschemaresponseformat"></a>
<a id="schema_JsonSchemaResponseFormat"></a>
<a id="tocSjsonschemaresponseformat"></a>
<a id="tocsjsonschemaresponseformat"></a>

```json
{
  "name": "string",
  "description": "string",
  "schema": {},
  "strict": true
}

```

JsonSchemaResponseFormat

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|description|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|schema|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strict|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_LayerInfo">LayerInfo</h2>
<!-- backwards compatibility -->
<a id="schemalayerinfo"></a>
<a id="schema_LayerInfo"></a>
<a id="tocSlayerinfo"></a>
<a id="tocslayerinfo"></a>

```json
{
  "width": 0,
  "height": 0,
  "dpi": 0,
  "z_index": 0,
  "opacity": 100,
  "duration": 0,
  "visible": true,
  "locked": false,
  "start_time": 0,
  "end_time": 0,
  "in_point": 0,
  "out_point": 0,
  "effects": {},
  "children": [
    null
  ]
}

```

LayerInfo

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|Optional. Canvas width.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|Optional. Canvas height.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|dpi|any|false|none|Optional. Canvas height.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|z_index|any|false|none|Optional. Layer z index.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|opacity|integer|false|none|Optional. Layer opacity.|
|duration|any|false|none|If animation or track, the total duration.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|visible|boolean|false|none|Layer visible.|
|locked|boolean|false|none|Layer locked.|
|start_time|any|false|none|If animation or track, the start time.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|end_time|any|false|none|If animation or track, the end time.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|in_point|any|false|none|If animation or track, the in point.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|out_point|any|false|none|If animation or track, the out point.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|effects|any|false|none|Optional. Layer effects.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|any|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|children|any|false|none|Optional. Layer children.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[any]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_LogitsProcessorConstructor">LogitsProcessorConstructor</h2>
<!-- backwards compatibility -->
<a id="schemalogitsprocessorconstructor"></a>
<a id="schema_LogitsProcessorConstructor"></a>
<a id="tocSlogitsprocessorconstructor"></a>
<a id="tocslogitsprocessorconstructor"></a>

```json
{
  "qualname": "string",
  "args": [
    null
  ],
  "kwargs": {}
}

```

LogitsProcessorConstructor

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|qualname|string|true|none|none|
|args|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[any]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|kwargs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_MarsRequest">MarsRequest</h2>
<!-- backwards compatibility -->
<a id="schemamarsrequest"></a>
<a id="schema_MarsRequest"></a>
<a id="tocSmarsrequest"></a>
<a id="tocsmarsrequest"></a>

```json
{
  "messages": [],
  "model": "mobile",
  "frequency_penalty": 1.15,
  "logit_bias": {},
  "logprobs": false,
  "top_logprobs": 0,
  "max_tokens": 300,
  "max_completion_tokens": 0,
  "n": 1,
  "presence_penalty": 1.15,
  "response_format": {
    "type": "text",
    "json_schema": {
      "name": "string",
      "description": "string",
      "schema": {},
      "strict": true
    }
  },
  "seed": -9223372036854776000,
  "stop": [],
  "stream": false,
  "stream_options": {
    "include_usage": true,
    "continuous_usage_stats": false
  },
  "temperature": 0.8,
  "top_p": 1,
  "tools": [
    {
      "type": "function",
      "function": {
        "name": "string",
        "description": "string",
        "parameters": {}
      }
    }
  ],
  "tool_choice": "none",
  "parallel_tool_calls": false,
  "user": "string",
  "best_of": 0,
  "use_beam_search": false,
  "top_k": 50,
  "min_p": 0,
  "repetition_penalty": 0,
  "length_penalty": 1,
  "stop_token_ids": [],
  "include_stop_str_in_output": false,
  "ignore_eos": false,
  "min_tokens": 50,
  "skip_special_tokens": true,
  "spaces_between_special_tokens": true,
  "truncate_prompt_tokens": 1,
  "prompt_logprobs": 0,
  "allowed_token_ids": [
    0
  ],
  "bad_words": [
    "string"
  ],
  "echo": false,
  "add_generation_prompt": true,
  "continue_final_message": false,
  "add_special_tokens": false,
  "documents": [
    {
      "property1": "string",
      "property2": "string"
    }
  ],
  "chat_template": "string",
  "chat_template_kwargs": {},
  "mm_processor_kwargs": {},
  "guided_json": "string",
  "guided_regex": "string",
  "guided_choice": [
    "string"
  ],
  "guided_grammar": "string",
  "structural_tag": "string",
  "guided_decoding_backend": "string",
  "guided_whitespace_pattern": "string",
  "priority": 0,
  "request_id": "string",
  "logits_processors": [
    "string"
  ],
  "return_tokens_as_token_ids": true,
  "cache_salt": "string",
  "kv_transfer_params": {},
  "vllm_xargs": {
    "property1": "string",
    "property2": "string"
  },
  "identity": "string",
  "prompt": "string",
  "query": "",
  "typical": 0,
  "token_repetition_penalty": 1.05,
  "guided_decoding": {
    "json": "string",
    "regex": "string",
    "choice": [
      "string"
    ],
    "grammar": "string",
    "json_object": true,
    "backend": "string",
    "backend_was_auto": false,
    "disable_fallback": false,
    "disable_any_whitespace": false,
    "disable_additional_properties": false,
    "whitespace_pattern": "string",
    "structural_tag": "string"
  },
  "sent_at": 0,
  "publish_to": "string",
  "token_repetition_range": -1,
  "token_repetition_decay": 0,
  "top_a": 0,
  "tfs": 0,
  "next": [
    "string"
  ],
  "n_tokens": 0,
  "do_voice": false,
  "voice_id": null,
  "template": "Hi how are you?",
  "parameters": {}
}

```

MarsRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|messages|[anyOf]|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionDeveloperMessageParam](#schemachatcompletiondevelopermessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionSystemMessageParam](#schemachatcompletionsystemmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionUserMessageParam](#schemachatcompletionusermessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionAssistantMessageParam](#schemachatcompletionassistantmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionToolMessageParam](#schemachatcompletiontoolmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionFunctionMessageParam](#schemachatcompletionfunctionmessageparam)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|false|none|The model to use. If using the combined endpoint, must be one of the available models. If using a model-specific endpoint, this value will be ignored and overridden by the path.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|frequency_penalty|any|false|none|Frequency penalty is a way to prevent word repetitions.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logit_bias|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_tokens|any|false|none|The maximum tokens to return. This is a hard limit.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_completion_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|n|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|presence_penalty|any|false|none|Presence penalty is a way to prevent topic repetitions.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|response_format|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ResponseFormat](#schemaresponseformat)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[StructuralTagResponseFormat](#schemastructuraltagresponseformat)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stop|any|false|none|A list of strings to stop generations at. Will override min_tokens.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stream|any|false|none|Whether to return the response streaming. Defaults to false.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stream_options|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[StreamOptions](#schemastreamoptions)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|temperature|any|false|none|The temperature. Like creativity.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_p|any|false|none|The top percentage of tokens to sample from at each step.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tools|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[[ChatCompletionToolsParam](#schemachatcompletiontoolsparam)]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tool_choice|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[vllm__entrypoints__openai__protocol__ChatCompletionNamedToolChoiceParam](#schemavllm__entrypoints__openai__protocol__chatcompletionnamedtoolchoiceparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parallel_tool_calls|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|best_of|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|use_beam_search|boolean|false|none|none|
|top_k|any|false|none|The top K most likely tokens to sample from at each step.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|min_p|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|repetition_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|length_penalty|number|false|none|none|
|stop_token_ids|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[integer]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|include_stop_str_in_output|boolean|false|none|none|
|ignore_eos|boolean|false|none|none|
|min_tokens|any|false|none|The minimum tokens to return. This is a soft limit -- if the model hits certain stop strings it may stop earlier, but it will *attempt* to return a response at least this long.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|skip_special_tokens|boolean|false|none|none|
|spaces_between_special_tokens|boolean|false|none|none|
|truncate_prompt_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt_logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|allowed_token_ids|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[integer]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bad_words|[string]|false|none|none|
|echo|boolean|false|none|If true, the new message will be prepended with the last message if they belong to the same role.|
|add_generation_prompt|boolean|false|none|none|
|continue_final_message|boolean|false|none|none|
|add_special_tokens|boolean|false|none|If true, special tokens (e.g. BOS) will be added to the prompt on top of what is added by the chat template. For most models, the chat template takes care of adding the special tokens so this should be set to false (as is the default).|
|documents|any|false|none|A list of dicts representing documents that will be accessible to the model if it is performing RAG (retrieval-augmented generation). If the template does not support RAG, this argument will have no effect. We recommend that each document should be a dict containing "title" and "text" keys.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[object]|false|none|none|
|»» **additionalProperties**|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_template|any|false|none|A Jinja template to use for this conversion. As of transformers v4.44, default chat template is no longer allowed, so you must provide a chat template if the tokenizer does not define one.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_template_kwargs|any|false|none|Additional keyword args to pass to the template renderer. Will be accessible by the chat template.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mm_processor_kwargs|any|false|none|Additional kwargs to pass to the HF processor.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guided_json|any|false|none|If specified, the output will follow the JSON schema.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[BaseModel](#schemabasemodel)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guided_regex|any|false|none|If specified, the output will follow the regex pattern.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guided_choice|any|false|none|If specified, the output will be exactly one of the choices.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guided_grammar|any|false|none|If specified, the output will follow the context free grammar.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|structural_tag|any|false|none|If specified, the output will follow the structural tag schema.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guided_decoding_backend|any|false|none|If specified, will override the default guided decoding backend of the server for this specific request. If set, must be either 'outlines' / 'lm-format-enforcer'|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guided_whitespace_pattern|any|false|none|If specified, will override the default whitespace pattern for guided json decoding.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|priority|integer|false|none|none|
|request_id|string|false|none|The request_id related to this request. If the caller does not set it, a random_uuid will be generated. This id is used through out the inference process and return in response.|
|logits_processors|any|false|none|A list of either qualified names of logits processors, or constructor objects, to apply when sampling. A constructor is a JSON object with a required 'qualname' field specifying the qualified name of the processor class/factory, and optional 'args' and 'kwargs' fields containing positional and keyword arguments. For example: {'qualname': 'my_module.MyLogitsProcessor', 'args': [1, 2], 'kwargs': {'param': 'value'}}.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[anyOf]|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[LogitsProcessorConstructor](#schemalogitsprocessorconstructor)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|return_tokens_as_token_ids|any|false|none|If specified with 'logprobs', tokens are represented  as strings of the form 'token_id:{token_id}' so that tokens that are not JSON-encodable can be identified.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cache_salt|any|false|none|If specified, the prefix cache will be salted with the provided string to prevent an attacker to guess prompts in multi-user environments. The salt should be random, protected from access by 3rd parties, and long enough to be unpredictable (e.g., 43 characters base64-encoded, corresponding to 256 bit). Not supported by vLLM engine V0.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|kv_transfer_params|any|false|none|KVTransfer parameters used for disaggregated serving.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|vllm_xargs|any|false|none|Additional request parameters with string or numeric values, used by custom extensions.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|identity|string|false|none|For internal sanity-checking.|
|prompt|any|false|none|The prompt to use.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|string|false|none|The raw query string, already pre-parsed.|
|typical|number|false|none|The typical|
|token_repetition_penalty|any|false|none|Repetition Penalty as a way to prevent word repetitions|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guided_decoding|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[GuidedDecodingParams](#schemaguideddecodingparams)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sent_at|integer|false|none|The UTC seconds sent at.|
|publish_to|any|false|none|Result topic.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|token_repetition_range|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|token_repetition_decay|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_a|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tfs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|next|any|false|none|The next queue to send it on to.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|n_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|do_voice|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|voice_id|any|false|none|Which voice_id to use. None for the default.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|template|any|false|none|The template to use. Example: "Tell me more about {{user}}."|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parameters|any|false|none|The params for the template. These will be directly replaced in the template. E.g. for the template example above,  parameters of {"{{user}}": "Jake"} would make the raw prompt given to the model "Tell me more about Jake."|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_Model">Model</h2>
<!-- backwards compatibility -->
<a id="schemamodel"></a>
<a id="schema_Model"></a>
<a id="tocSmodel"></a>
<a id="tocsmodel"></a>

```json
{
  "id": "asha",
  "object": "model",
  "owned_by": "string",
  "permission": []
}

```

Model

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|The unique identifier of the model. Also generally its name.|
|object|string|false|none|Always 'model'. Included for OpenAI compatibility.|
|owned_by|string|true|none|none|
|permission|[string]|false|none|none|

<h2 id="tocS_Models">Models</h2>
<!-- backwards compatibility -->
<a id="schemamodels"></a>
<a id="schema_Models"></a>
<a id="tocSmodels"></a>
<a id="tocsmodels"></a>

```json
{
  "data": []
}

```

Models

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[Model](#schemamodel)]|false|none|The models available for use.|

<h2 id="tocS_MusicGenType">MusicGenType</h2>
<!-- backwards compatibility -->
<a id="schemamusicgentype"></a>
<a id="schema_MusicGenType"></a>
<a id="tocSmusicgentype"></a>
<a id="tocsmusicgentype"></a>

```json
"instrumental"

```

MusicGenType

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|MusicGenType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|MusicGenType|instrumental|
|MusicGenType|vocals|
|MusicGenType|mixed|

<h2 id="tocS_MusicGenerationRequest">MusicGenerationRequest</h2>
<!-- backwards compatibility -->
<a id="schemamusicgenerationrequest"></a>
<a id="schema_MusicGenerationRequest"></a>
<a id="tocSmusicgenerationrequest"></a>
<a id="tocsmusicgenerationrequest"></a>

```json
{
  "lyrics": "string",
  "genre": "automatic",
  "music_type": "mixed",
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "tags": [
    "string"
  ],
  "title": "string",
  "cfg_coefficient": 1.5,
  "temperature": 0.9,
  "top_k": 30,
  "lyrics_prompt": "string"
}

```

MusicGenerationRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lyrics|any|false|none|The song's lyrics, if relevant. Each part should begin with a structure tag ([verse], [chorus], [bridge], [intro-short], [intro-medium], [intro-long], [outro-short], [outro-medium], [outro-long], [inst-short], [inst-medium], [inst-long], [silence]) and a newline, and end with two newlines. These segments should not contain lyrics: ([intro], [intro-short], [intro-medium], [inst], [inst-short], [inst-medium], [outro], [outro-short], [outro-medium])|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|genre|any|false|none|The musical genre.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[MusicGenre](#schemamusicgenre)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|music_type|any|false|none|Whether to make instrumental music, only vocals, or a fully mixed song. If requesting 'vocals' or 'mixed', lyrics MUST be provided.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[MusicGenType](#schemamusicgentype)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tags|any|false|none|For future use.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|any|false|none|For future use.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cfg_coefficient|any|false|none|The CFG Coefficient. Increments of 0.1. Advanced setting.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|temperature|any|false|none|The temperature. Increments of 0.1. Advanced setting.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_k|any|false|none|The top k. Advanced setting.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lyrics_prompt|any|false|none|For future use.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_MusicGenre">MusicGenre</h2>
<!-- backwards compatibility -->
<a id="schemamusicgenre"></a>
<a id="schema_MusicGenre"></a>
<a id="tocSmusicgenre"></a>
<a id="tocsmusicgenre"></a>

```json
"pop"

```

MusicGenre

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|MusicGenre|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|MusicGenre|pop|
|MusicGenre|rhythm_and_blues|
|MusicGenre|dance|
|MusicGenre|jazz|
|MusicGenre|folk|
|MusicGenre|rock|
|MusicGenre|chinese_modern|
|MusicGenre|eastern_traditional|
|MusicGenre|eastern_opera|
|MusicGenre|metal|
|MusicGenre|reggae|
|MusicGenre|automatic|

<h2 id="tocS_OAuthUserStub">OAuthUserStub</h2>
<!-- backwards compatibility -->
<a id="schemaoauthuserstub"></a>
<a id="schema_OAuthUserStub"></a>
<a id="tocSoauthuserstub"></a>
<a id="tocsoauthuserstub"></a>

```json
{
  "identity": "string",
  "username": "string",
  "scopes": [],
  "credits": 0,
  "credits_reset": "2025-08-14T23:44:22Z",
  "credits_reset_in": "4 hours, 10 minutes",
  "subscription": "string",
  "note": "string"
}

```

OAuthUserStub

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|identity|string|true|none|The user's unique identifier.|
|username|string|true|none|The user's username.|
|scopes|[string]|false|none|What scopes the user has access to.|
|credits|integer|false|none|The current number of credits remaining.|
|credits_reset|any|false|none|When the credits next reset, in ISO 8601 timestamp format in UTC.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|credits_reset_in|string|false|none|A human-readable version of when credits reset.|
|subscription|any|false|none|None, Basic, Full, or Max.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|note|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_OrderMediaBy">OrderMediaBy</h2>
<!-- backwards compatibility -->
<a id="schemaordermediaby"></a>
<a id="schema_OrderMediaBy"></a>
<a id="tocSordermediaby"></a>
<a id="tocsordermediaby"></a>

```json
"created_at"

```

OrderMediaBy

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|OrderMediaBy|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|OrderMediaBy|created_at|
|OrderMediaBy|updated_at|
|OrderMediaBy|uuid|

<h2 id="tocS_Output3DType">Output3DType</h2>
<!-- backwards compatibility -->
<a id="schemaoutput3dtype"></a>
<a id="schema_Output3DType"></a>
<a id="tocSoutput3dtype"></a>
<a id="tocsoutput3dtype"></a>

```json
"glb"

```

Output3DType

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Output3DType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|Output3DType|glb|
|Output3DType|vrm|

<h2 id="tocS_Rejection">Rejection</h2>
<!-- backwards compatibility -->
<a id="schemarejection"></a>
<a id="schema_Rejection"></a>
<a id="tocSrejection"></a>
<a id="tocsrejection"></a>

```json
{
  "reason": "unknown",
  "location": "string"
}

```

Rejection

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reason|[RejectionReason](#schemarejectionreason)|false|none|none|
|location|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_RejectionReason">RejectionReason</h2>
<!-- backwards compatibility -->
<a id="schemarejectionreason"></a>
<a id="schema_RejectionReason"></a>
<a id="tocSrejectionreason"></a>
<a id="tocsrejectionreason"></a>

```json
"unknown"

```

RejectionReason

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|RejectionReason|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|RejectionReason|unknown|
|RejectionReason|explicit_text|
|RejectionReason|explicit_image|
|RejectionReason|malformed_image|
|RejectionReason|out_of_credits|

<h2 id="tocS_RemoveBGRequest">RemoveBGRequest</h2>
<!-- backwards compatibility -->
<a id="schemaremovebgrequest"></a>
<a id="schema_RemoveBGRequest"></a>
<a id="tocSremovebgrequest"></a>
<a id="tocsremovebgrequest"></a>

```json
{
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "image": "",
  "alpha_matting": false,
  "post_process_mask": false,
  "alpha_matting_foreground_threshold": 240,
  "alpha_matting_background_threshold": 20,
  "alpha_matting_erode_size": 5
}

```

RemoveBGRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|image|any|false|none|Deprecated; please use 'init_image'.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|alpha_matting|any|false|none|Whether to perform alpha matting.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|post_process_mask|any|false|none|Whether to post process the mask image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|alpha_matting_foreground_threshold|any|false|none|Threshold for alpha matting foreground.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|alpha_matting_background_threshold|any|false|none|Threshold for alpha matting background.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|alpha_matting_erode_size|any|false|none|Erode size for alpha matting.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_ResponseFormat">ResponseFormat</h2>
<!-- backwards compatibility -->
<a id="schemaresponseformat"></a>
<a id="schema_ResponseFormat"></a>
<a id="tocSresponseformat"></a>
<a id="tocsresponseformat"></a>

```json
{
  "type": "text",
  "json_schema": {
    "name": "string",
    "description": "string",
    "schema": {},
    "strict": true
  }
}

```

ResponseFormat

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|json_schema|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[JsonSchemaResponseFormat](#schemajsonschemaresponseformat)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|text|
|type|json_object|
|type|json_schema|

<h2 id="tocS_ResponseFormatJSONObject">ResponseFormatJSONObject</h2>
<!-- backwards compatibility -->
<a id="schemaresponseformatjsonobject"></a>
<a id="schema_ResponseFormatJSONObject"></a>
<a id="tocSresponseformatjsonobject"></a>
<a id="tocsresponseformatjsonobject"></a>

```json
{
  "type": "json_object"
}

```

ResponseFormatJSONObject

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|

<h2 id="tocS_ResponseFormatJSONSchema">ResponseFormatJSONSchema</h2>
<!-- backwards compatibility -->
<a id="schemaresponseformatjsonschema"></a>
<a id="schema_ResponseFormatJSONSchema"></a>
<a id="tocSresponseformatjsonschema"></a>
<a id="tocsresponseformatjsonschema"></a>

```json
{
  "json_schema": {
    "name": "string",
    "description": "string",
    "schema": {},
    "strict": true
  },
  "type": "json_schema"
}

```

ResponseFormatJSONSchema

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|json_schema|[JSONSchema](#schemajsonschema)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_ResponseFormatText">ResponseFormatText</h2>
<!-- backwards compatibility -->
<a id="schemaresponseformattext"></a>
<a id="schema_ResponseFormatText"></a>
<a id="tocSresponseformattext"></a>
<a id="tocsresponseformattext"></a>

```json
{
  "type": "text"
}

```

ResponseFormatText

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|

<h2 id="tocS_RigType">RigType</h2>
<!-- backwards compatibility -->
<a id="schemarigtype"></a>
<a id="schema_RigType"></a>
<a id="tocSrigtype"></a>
<a id="tocsrigtype"></a>

```json
"biped"

```

RigType

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|RigType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|RigType|biped|
|RigType|quadruped|
|RigType|unknown|
|RigType|none|

<h2 id="tocS_RunningGeneration">RunningGeneration</h2>
<!-- backwards compatibility -->
<a id="schemarunninggeneration"></a>
<a id="schema_RunningGeneration"></a>
<a id="tocSrunninggeneration"></a>
<a id="tocsrunninggeneration"></a>

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}

```

RunningGeneration

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|generation_uuid|any|false|none|The unique identity of the generation, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cost|any|false|none|Cost in credits, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_RunningGenerationCheck">RunningGenerationCheck</h2>
<!-- backwards compatibility -->
<a id="schemarunninggenerationcheck"></a>
<a id="schema_RunningGenerationCheck"></a>
<a id="tocSrunninggenerationcheck"></a>
<a id="tocsrunninggenerationcheck"></a>

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0,
  "request_type": "string"
}

```

RunningGenerationCheck

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|generation_uuid|any|false|none|The unique identity of the generation, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cost|any|false|none|Cost in credits, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|request_type|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_STTResponse">STTResponse</h2>
<!-- backwards compatibility -->
<a id="schemasttresponse"></a>
<a id="schema_STTResponse"></a>
<a id="tocSsttresponse"></a>
<a id="tocssttresponse"></a>

```json
{
  "reference_text": ""
}

```

STTResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reference_text|string|false|none|The transcribed text.|

<h2 id="tocS_Speed">Speed</h2>
<!-- backwards compatibility -->
<a id="schemaspeed"></a>
<a id="schema_Speed"></a>
<a id="tocSspeed"></a>
<a id="tocsspeed"></a>

```json
"turbo"

```

Speed

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Speed|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|Speed|turbo|
|Speed|normal|

<h2 id="tocS_StreamOptions">StreamOptions</h2>
<!-- backwards compatibility -->
<a id="schemastreamoptions"></a>
<a id="schema_StreamOptions"></a>
<a id="tocSstreamoptions"></a>
<a id="tocsstreamoptions"></a>

```json
{
  "include_usage": true,
  "continuous_usage_stats": false
}

```

StreamOptions

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|include_usage|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|continuous_usage_stats|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_StructuralTag">StructuralTag</h2>
<!-- backwards compatibility -->
<a id="schemastructuraltag"></a>
<a id="schema_StructuralTag"></a>
<a id="tocSstructuraltag"></a>
<a id="tocsstructuraltag"></a>

```json
{
  "begin": "string",
  "schema": {},
  "end": "string"
}

```

StructuralTag

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|begin|string|true|none|none|
|schema|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|end|string|true|none|none|

<h2 id="tocS_StructuralTagResponseFormat">StructuralTagResponseFormat</h2>
<!-- backwards compatibility -->
<a id="schemastructuraltagresponseformat"></a>
<a id="schema_StructuralTagResponseFormat"></a>
<a id="tocSstructuraltagresponseformat"></a>
<a id="tocsstructuraltagresponseformat"></a>

```json
{
  "type": "structural_tag",
  "structures": [
    {
      "begin": "string",
      "schema": {},
      "end": "string"
    }
  ],
  "triggers": [
    "string"
  ]
}

```

StructuralTagResponseFormat

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|structures|[[StructuralTag](#schemastructuraltag)]|true|none|none|
|triggers|[string]|true|none|none|

<h2 id="tocS_TextToImage">TextToImage</h2>
<!-- backwards compatibility -->
<a id="schematexttoimage"></a>
<a id="schema_TextToImage"></a>
<a id="tocStexttoimage"></a>
<a id="tocstexttoimage"></a>

```json
{
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5
}

```

TextToImage

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_TextToSpeechRequest">TextToSpeechRequest</h2>
<!-- backwards compatibility -->
<a id="schematexttospeechrequest"></a>
<a id="schema_TextToSpeechRequest"></a>
<a id="tocStexttospeechrequest"></a>
<a id="tocstexttospeechrequest"></a>

```json
{
  "transcript": "A wizard's job is to vex chumps quickly in fog.",
  "voice": "bright_female_20s",
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "model": null,
  "voice_id": null,
  "remove_silence": true,
  "stream": false,
  "character_id": null
}

```

TextToSpeechRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transcript|any|false|none|The text to read out.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|voice|any|false|none|Select a voice to use.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Voice](#schemavoice)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|false|none|Which model to use. z, or None for the default.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|voice_id|any|false|none|Which voice_id to use. None for the default.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_silence|any|false|none|Whether to remove gaps from the resulting audio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stream|any|false|none|Whether to stream the response.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|character_id|any|false|none|The character's voice to use. Overrides voice id. Must be given as the 'username/project-slug' id.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_TimedResponse">TimedResponse</h2>
<!-- backwards compatibility -->
<a id="schematimedresponse"></a>
<a id="schema_TimedResponse"></a>
<a id="tocStimedresponse"></a>
<a id="tocstimedresponse"></a>

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "cost": 0
}

```

TimedResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|TimedResponse|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[RunningGeneration](#schemarunninggeneration)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[GalleryItem](#schemagalleryitem)|false|none|none|

<h2 id="tocS_UpscaleBase">UpscaleBase</h2>
<!-- backwards compatibility -->
<a id="schemaupscalebase"></a>
<a id="schema_UpscaleBase"></a>
<a id="tocSupscalebase"></a>
<a id="tocsupscalebase"></a>

```json
{
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "aspect_ratio": null,
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "image": "",
  "preserve_transparency": true
}

```

UpscaleBase

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The aspect ratio. If given, this will override the width and height. Values are '1:1', '16:9', '21:9', '2:3', '3:2', '3:4', '4:3', '4:5', '5:4', '9:16', and '9:21'.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|image|any|false|none|Deprecated; please use 'init_image'.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|preserve_transparency|any|false|none|If given, this transparency will be preserved.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_UserError">UserError</h2>
<!-- backwards compatibility -->
<a id="schemausererror"></a>
<a id="schema_UserError"></a>
<a id="tocSusererror"></a>
<a id="tocsusererror"></a>

```json
{
  "error": "",
  "errorCode": 400,
  "code": 0
}

```

UserError

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|string|false|none|none|
|errorCode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_ValidationError">ValidationError</h2>
<!-- backwards compatibility -->
<a id="schemavalidationerror"></a>
<a id="schema_ValidationError"></a>
<a id="tocSvalidationerror"></a>
<a id="tocsvalidationerror"></a>

```json
{
  "loc": [
    "string"
  ],
  "msg": "string",
  "type": "string"
}

```

ValidationError

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|loc|[anyOf]|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|msg|string|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_VideoRequest">VideoRequest</h2>
<!-- backwards compatibility -->
<a id="schemavideorequest"></a>
<a id="schema_VideoRequest"></a>
<a id="tocSvideorequest"></a>
<a id="tocsvideorequest"></a>

```json
{
  "end_image": "string",
  "fps": 8,
  "chat_id": "string",
  "uuid": "string",
  "mode": "string",
  "sub_mode": "string",
  "width": 1024,
  "height": 1024,
  "item_id": "string",
  "extension_source": "string",
  "parent_image": "string",
  "aspect_ratio": "w1h1",
  "seed": -1,
  "prompt": "",
  "negative_prompt": "",
  "num_inference_steps": 30,
  "remove_background": false,
  "init_image": "https://example.com/some_image_url.png",
  "strength": 0.7,
  "guidance_scale": 3.5,
  "loop": false,
  "num_frames": 12
}

```

VideoRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|end_image|any|false|none|The final frame image for image-to-video, as a URL or base64 string. If you want a video to loop, give the same start and end image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fps|any|false|none|The number of frames per second.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|chat_id|any|false|none|If this is inside of a chat, include its ID as a string.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sub_mode|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|any|false|none|The width. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|height|any|false|none|The height. Overridden by aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|item_id|any|false|none|The item_id, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|extension_source|any|false|none|If an extension is requesting this, include its ID.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parent_image|any|false|none|The UUID of the parent image, if any.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|aspect_ratio|any|false|none|The desired aspect ratio.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[AspectRatio](#schemaaspectratio)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|Use this only if reproducible results are important.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|false|none|It should be descriptive of exactly what you want, and fairly detailed.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|negative_prompt|any|false|none|What you don't want in the result.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_inference_steps|any|false|none|Larger values may produce better outputs at the cost of longer generation times. Values over 50 are usually overkill.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|remove_background|any|false|none|Whether to remove the background of any image(s) before/after this operation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|init_image|any|false|none|Base64 image string, or a URL to an image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|strength|any|false|none|The strength of any image-to-image transformation.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|guidance_scale|any|false|none|How strongly the prompt affects the output.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|loop|any|false|none|Whether to loop the image.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|num_frames|any|false|none|The number of frames to generate.|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_Voice">Voice</h2>
<!-- backwards compatibility -->
<a id="schemavoice"></a>
<a id="schema_Voice"></a>
<a id="tocSvoice"></a>
<a id="tocsvoice"></a>

```json
"bright_female_20s"

```

Voice

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Voice|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|Voice|bright_female_20s|
|Voice|gentle_female_30s|
|Voice|whispery_female_40s|
|Voice|formal_female_30s|
|Voice|professional_female_30s|
|Voice|resonant_male_40s|
|Voice|light_male_20s|
|Voice|animated_male_20s|
|Voice|calm_female_20s|

<h2 id="tocS_VoiceClone">VoiceClone</h2>
<!-- backwards compatibility -->
<a id="schemavoiceclone"></a>
<a id="schema_VoiceClone"></a>
<a id="tocSvoiceclone"></a>
<a id="tocsvoiceclone"></a>

```json
{
  "uuid": "string",
  "version": 0,
  "user_id": 0,
  "name": "string",
  "is_done": true,
  "is_failed": true,
  "transcript": "string",
  "sample": "string",
  "reference_text": "string",
  "model": "string",
  "example": "string",
  "e2_example": "string",
  "f5_example": "string",
  "z_example": "string",
  "created_at": "string",
  "updated_at": "string"
}

```

VoiceClone

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|string|true|none|none|
|version|integer|true|none|none|
|user_id|integer|true|none|none|
|name|string|true|none|none|
|is_done|boolean|true|none|none|
|is_failed|boolean|true|none|none|
|transcript|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sample|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reference_text|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|example|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|e2_example|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|f5_example|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|z_example|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created_at|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|updated_at|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_Voices">Voices</h2>
<!-- backwards compatibility -->
<a id="schemavoices"></a>
<a id="schema_Voices"></a>
<a id="tocSvoices"></a>
<a id="tocsvoices"></a>

```json
{
  "voices": []
}

```

Voices

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|voices|[[VoiceClone](#schemavoiceclone)]|false|none|none|

<h2 id="tocS_WebSearchOptions">WebSearchOptions</h2>
<!-- backwards compatibility -->
<a id="schemawebsearchoptions"></a>
<a id="schema_WebSearchOptions"></a>
<a id="tocSwebsearchoptions"></a>
<a id="tocswebsearchoptions"></a>

```json
{
  "search_context_size": "low",
  "user_location": {
    "approximate": {
      "city": "string",
      "country": "string",
      "region": "string",
      "timezone": "string"
    },
    "type": "approximate"
  }
}

```

WebSearchOptions

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|search_context_size|string|false|none|none|
|user_location|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[WebSearchOptionsUserLocation](#schemawebsearchoptionsuserlocation)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|search_context_size|low|
|search_context_size|medium|
|search_context_size|high|

<h2 id="tocS_WebSearchOptionsUserLocation">WebSearchOptionsUserLocation</h2>
<!-- backwards compatibility -->
<a id="schemawebsearchoptionsuserlocation"></a>
<a id="schema_WebSearchOptionsUserLocation"></a>
<a id="tocSwebsearchoptionsuserlocation"></a>
<a id="tocswebsearchoptionsuserlocation"></a>

```json
{
  "approximate": {
    "city": "string",
    "country": "string",
    "region": "string",
    "timezone": "string"
  },
  "type": "approximate"
}

```

WebSearchOptionsUserLocation

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|approximate|[WebSearchOptionsUserLocationApproximate](#schemawebsearchoptionsuserlocationapproximate)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_WebSearchOptionsUserLocationApproximate">WebSearchOptionsUserLocationApproximate</h2>
<!-- backwards compatibility -->
<a id="schemawebsearchoptionsuserlocationapproximate"></a>
<a id="schema_WebSearchOptionsUserLocationApproximate"></a>
<a id="tocSwebsearchoptionsuserlocationapproximate"></a>
<a id="tocswebsearchoptionsuserlocationapproximate"></a>

```json
{
  "city": "string",
  "country": "string",
  "region": "string",
  "timezone": "string"
}

```

WebSearchOptionsUserLocationApproximate

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|city|string|false|none|none|
|country|string|false|none|none|
|region|string|false|none|none|
|timezone|string|false|none|none|

<h2 id="tocS_openai__types__chat__chat_completion_message_tool_call_param__Function">openai__types__chat__chat_completion_message_tool_call_param__Function</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__chat__chat_completion_message_tool_call_param__function"></a>
<a id="schema_openai__types__chat__chat_completion_message_tool_call_param__Function"></a>
<a id="tocSopenai__types__chat__chat_completion_message_tool_call_param__function"></a>
<a id="tocsopenai__types__chat__chat_completion_message_tool_call_param__function"></a>

```json
{
  "arguments": "string",
  "name": "string"
}

```

Function

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|arguments|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocS_openai__types__chat__chat_completion_named_tool_choice_param__ChatCompletionNamedToolChoiceParam">openai__types__chat__chat_completion_named_tool_choice_param__ChatCompletionNamedToolChoiceParam</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__chat__chat_completion_named_tool_choice_param__chatcompletionnamedtoolchoiceparam"></a>
<a id="schema_openai__types__chat__chat_completion_named_tool_choice_param__ChatCompletionNamedToolChoiceParam"></a>
<a id="tocSopenai__types__chat__chat_completion_named_tool_choice_param__chatcompletionnamedtoolchoiceparam"></a>
<a id="tocsopenai__types__chat__chat_completion_named_tool_choice_param__chatcompletionnamedtoolchoiceparam"></a>

```json
{
  "function": {
    "name": "string"
  },
  "type": "function"
}

```

ChatCompletionNamedToolChoiceParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|function|[openai__types__chat__chat_completion_named_tool_choice_param__Function](#schemaopenai__types__chat__chat_completion_named_tool_choice_param__function)|true|none|none|
|type|string|true|none|none|

<h2 id="tocS_openai__types__chat__chat_completion_named_tool_choice_param__Function">openai__types__chat__chat_completion_named_tool_choice_param__Function</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__chat__chat_completion_named_tool_choice_param__function"></a>
<a id="schema_openai__types__chat__chat_completion_named_tool_choice_param__Function"></a>
<a id="tocSopenai__types__chat__chat_completion_named_tool_choice_param__function"></a>
<a id="tocsopenai__types__chat__chat_completion_named_tool_choice_param__function"></a>

```json
{
  "name": "string"
}

```

Function

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|

<h2 id="tocS_openai__types__chat__completion_create_params__CompletionCreateParamsNonStreaming">openai__types__chat__completion_create_params__CompletionCreateParamsNonStreaming</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__chat__completion_create_params__completioncreateparamsnonstreaming"></a>
<a id="schema_openai__types__chat__completion_create_params__CompletionCreateParamsNonStreaming"></a>
<a id="tocSopenai__types__chat__completion_create_params__completioncreateparamsnonstreaming"></a>
<a id="tocsopenai__types__chat__completion_create_params__completioncreateparamsnonstreaming"></a>

```json
{
  "messages": [
    {
      "content": "string",
      "role": "developer",
      "name": "string"
    }
  ],
  "model": "string",
  "audio": {
    "format": "wav",
    "voice": "string"
  },
  "frequency_penalty": 0,
  "function_call": "none",
  "functions": [
    {
      "name": "string",
      "description": "string",
      "parameters": {}
    }
  ],
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": true,
  "max_completion_tokens": 0,
  "max_tokens": 0,
  "metadata": {
    "property1": "string",
    "property2": "string"
  },
  "modalities": [
    "text"
  ],
  "n": 0,
  "parallel_tool_calls": true,
  "prediction": {
    "content": "string",
    "type": "content"
  },
  "presence_penalty": 0,
  "reasoning_effort": "low",
  "response_format": {
    "type": "text"
  },
  "seed": 0,
  "service_tier": "auto",
  "stop": "string",
  "store": true,
  "stream_options": {
    "include_usage": true
  },
  "temperature": 0,
  "tool_choice": "none",
  "tools": [
    {
      "function": {
        "name": "string",
        "description": "string",
        "parameters": {},
        "strict": true
      },
      "type": "function"
    }
  ],
  "top_logprobs": 0,
  "top_p": 0,
  "user": "string",
  "web_search_options": {
    "search_context_size": "low",
    "user_location": {
      "approximate": {
        "city": "string",
        "country": "string",
        "region": "string",
        "timezone": "string"
      },
      "type": "approximate"
    }
  },
  "stream": false
}

```

CompletionCreateParamsNonStreaming

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|messages|[anyOf]|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionDeveloperMessageParam](#schemachatcompletiondevelopermessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionSystemMessageParam](#schemachatcompletionsystemmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionUserMessageParam](#schemachatcompletionusermessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionAssistantMessageParam](#schemachatcompletionassistantmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionToolMessageParam](#schemachatcompletiontoolmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionFunctionMessageParam](#schemachatcompletionfunctionmessageparam)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|audio|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionAudioParam](#schemachatcompletionaudioparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|frequency_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|function_call|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionFunctionCallOptionParam](#schemachatcompletionfunctioncalloptionparam)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|functions|[[openai__types__chat__completion_create_params__Function](#schemaopenai__types__chat__completion_create_params__function)]|false|none|none|
|logit_bias|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_completion_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|metadata|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|modalities|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|n|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parallel_tool_calls|boolean|false|none|none|
|prediction|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionPredictionContentParam](#schemachatcompletionpredictioncontentparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|presence_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reasoning_effort|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|response_format|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ResponseFormatText](#schemaresponseformattext)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ResponseFormatJSONSchema](#schemaresponseformatjsonschema)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ResponseFormatJSONObject](#schemaresponseformatjsonobject)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|service_tier|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stop|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|store|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stream_options|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionStreamOptionsParam](#schemachatcompletionstreamoptionsparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|temperature|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tool_choice|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[openai__types__chat__chat_completion_named_tool_choice_param__ChatCompletionNamedToolChoiceParam](#schemaopenai__types__chat__chat_completion_named_tool_choice_param__chatcompletionnamedtoolchoiceparam)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tools|[[ChatCompletionToolParam](#schemachatcompletiontoolparam)]|false|none|none|
|top_logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_p|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|string|false|none|none|
|web_search_options|[WebSearchOptions](#schemawebsearchoptions)|false|none|none|
|stream|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|gpt-4.1|
|*anonymous*|gpt-4.1-mini|
|*anonymous*|gpt-4.1-nano|
|*anonymous*|gpt-4.1-2025-04-14|
|*anonymous*|gpt-4.1-mini-2025-04-14|
|*anonymous*|gpt-4.1-nano-2025-04-14|
|*anonymous*|o4-mini|
|*anonymous*|o4-mini-2025-04-16|
|*anonymous*|o3|
|*anonymous*|o3-2025-04-16|
|*anonymous*|o3-mini|
|*anonymous*|o3-mini-2025-01-31|
|*anonymous*|o1|
|*anonymous*|o1-2024-12-17|
|*anonymous*|o1-preview|
|*anonymous*|o1-preview-2024-09-12|
|*anonymous*|o1-mini|
|*anonymous*|o1-mini-2024-09-12|
|*anonymous*|gpt-4o|
|*anonymous*|gpt-4o-2024-11-20|
|*anonymous*|gpt-4o-2024-08-06|
|*anonymous*|gpt-4o-2024-05-13|
|*anonymous*|gpt-4o-audio-preview|
|*anonymous*|gpt-4o-audio-preview-2024-10-01|
|*anonymous*|gpt-4o-audio-preview-2024-12-17|
|*anonymous*|gpt-4o-audio-preview-2025-06-03|
|*anonymous*|gpt-4o-mini-audio-preview|
|*anonymous*|gpt-4o-mini-audio-preview-2024-12-17|
|*anonymous*|gpt-4o-search-preview|
|*anonymous*|gpt-4o-mini-search-preview|
|*anonymous*|gpt-4o-search-preview-2025-03-11|
|*anonymous*|gpt-4o-mini-search-preview-2025-03-11|
|*anonymous*|chatgpt-4o-latest|
|*anonymous*|codex-mini-latest|
|*anonymous*|gpt-4o-mini|
|*anonymous*|gpt-4o-mini-2024-07-18|
|*anonymous*|gpt-4-turbo|
|*anonymous*|gpt-4-turbo-2024-04-09|
|*anonymous*|gpt-4-0125-preview|
|*anonymous*|gpt-4-turbo-preview|
|*anonymous*|gpt-4-1106-preview|
|*anonymous*|gpt-4-vision-preview|
|*anonymous*|gpt-4|
|*anonymous*|gpt-4-0314|
|*anonymous*|gpt-4-0613|
|*anonymous*|gpt-4-32k|
|*anonymous*|gpt-4-32k-0314|
|*anonymous*|gpt-4-32k-0613|
|*anonymous*|gpt-3.5-turbo|
|*anonymous*|gpt-3.5-turbo-16k|
|*anonymous*|gpt-3.5-turbo-0301|
|*anonymous*|gpt-3.5-turbo-0613|
|*anonymous*|gpt-3.5-turbo-1106|
|*anonymous*|gpt-3.5-turbo-0125|
|*anonymous*|gpt-3.5-turbo-16k-0613|
|*anonymous*|none|
|*anonymous*|auto|
|*anonymous*|low|
|*anonymous*|medium|
|*anonymous*|high|
|*anonymous*|auto|
|*anonymous*|default|
|*anonymous*|flex|
|*anonymous*|scale|
|*anonymous*|none|
|*anonymous*|auto|
|*anonymous*|required|

<h2 id="tocS_openai__types__chat__completion_create_params__CompletionCreateParamsStreaming">openai__types__chat__completion_create_params__CompletionCreateParamsStreaming</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__chat__completion_create_params__completioncreateparamsstreaming"></a>
<a id="schema_openai__types__chat__completion_create_params__CompletionCreateParamsStreaming"></a>
<a id="tocSopenai__types__chat__completion_create_params__completioncreateparamsstreaming"></a>
<a id="tocsopenai__types__chat__completion_create_params__completioncreateparamsstreaming"></a>

```json
{
  "messages": [
    {
      "content": "string",
      "role": "developer",
      "name": "string"
    }
  ],
  "model": "string",
  "audio": {
    "format": "wav",
    "voice": "string"
  },
  "frequency_penalty": 0,
  "function_call": "none",
  "functions": [
    {
      "name": "string",
      "description": "string",
      "parameters": {}
    }
  ],
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": true,
  "max_completion_tokens": 0,
  "max_tokens": 0,
  "metadata": {
    "property1": "string",
    "property2": "string"
  },
  "modalities": [
    "text"
  ],
  "n": 0,
  "parallel_tool_calls": true,
  "prediction": {
    "content": "string",
    "type": "content"
  },
  "presence_penalty": 0,
  "reasoning_effort": "low",
  "response_format": {
    "type": "text"
  },
  "seed": 0,
  "service_tier": "auto",
  "stop": "string",
  "store": true,
  "stream_options": {
    "include_usage": true
  },
  "temperature": 0,
  "tool_choice": "none",
  "tools": [
    {
      "function": {
        "name": "string",
        "description": "string",
        "parameters": {},
        "strict": true
      },
      "type": "function"
    }
  ],
  "top_logprobs": 0,
  "top_p": 0,
  "user": "string",
  "web_search_options": {
    "search_context_size": "low",
    "user_location": {
      "approximate": {
        "city": "string",
        "country": "string",
        "region": "string",
        "timezone": "string"
      },
      "type": "approximate"
    }
  },
  "stream": true
}

```

CompletionCreateParamsStreaming

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|messages|[anyOf]|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionDeveloperMessageParam](#schemachatcompletiondevelopermessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionSystemMessageParam](#schemachatcompletionsystemmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionUserMessageParam](#schemachatcompletionusermessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionAssistantMessageParam](#schemachatcompletionassistantmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionToolMessageParam](#schemachatcompletiontoolmessageparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionFunctionMessageParam](#schemachatcompletionfunctionmessageparam)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|audio|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionAudioParam](#schemachatcompletionaudioparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|frequency_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|function_call|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionFunctionCallOptionParam](#schemachatcompletionfunctioncalloptionparam)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|functions|[[openai__types__chat__completion_create_params__Function](#schemaopenai__types__chat__completion_create_params__function)]|false|none|none|
|logit_bias|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_completion_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|metadata|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|modalities|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|n|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parallel_tool_calls|boolean|false|none|none|
|prediction|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionPredictionContentParam](#schemachatcompletionpredictioncontentparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|presence_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reasoning_effort|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|response_format|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ResponseFormatText](#schemaresponseformattext)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ResponseFormatJSONSchema](#schemaresponseformatjsonschema)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ResponseFormatJSONObject](#schemaresponseformatjsonobject)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|service_tier|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stop|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|store|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stream_options|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionStreamOptionsParam](#schemachatcompletionstreamoptionsparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|temperature|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tool_choice|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[openai__types__chat__chat_completion_named_tool_choice_param__ChatCompletionNamedToolChoiceParam](#schemaopenai__types__chat__chat_completion_named_tool_choice_param__chatcompletionnamedtoolchoiceparam)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tools|[[ChatCompletionToolParam](#schemachatcompletiontoolparam)]|false|none|none|
|top_logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_p|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|string|false|none|none|
|web_search_options|[WebSearchOptions](#schemawebsearchoptions)|false|none|none|
|stream|boolean|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|gpt-4.1|
|*anonymous*|gpt-4.1-mini|
|*anonymous*|gpt-4.1-nano|
|*anonymous*|gpt-4.1-2025-04-14|
|*anonymous*|gpt-4.1-mini-2025-04-14|
|*anonymous*|gpt-4.1-nano-2025-04-14|
|*anonymous*|o4-mini|
|*anonymous*|o4-mini-2025-04-16|
|*anonymous*|o3|
|*anonymous*|o3-2025-04-16|
|*anonymous*|o3-mini|
|*anonymous*|o3-mini-2025-01-31|
|*anonymous*|o1|
|*anonymous*|o1-2024-12-17|
|*anonymous*|o1-preview|
|*anonymous*|o1-preview-2024-09-12|
|*anonymous*|o1-mini|
|*anonymous*|o1-mini-2024-09-12|
|*anonymous*|gpt-4o|
|*anonymous*|gpt-4o-2024-11-20|
|*anonymous*|gpt-4o-2024-08-06|
|*anonymous*|gpt-4o-2024-05-13|
|*anonymous*|gpt-4o-audio-preview|
|*anonymous*|gpt-4o-audio-preview-2024-10-01|
|*anonymous*|gpt-4o-audio-preview-2024-12-17|
|*anonymous*|gpt-4o-audio-preview-2025-06-03|
|*anonymous*|gpt-4o-mini-audio-preview|
|*anonymous*|gpt-4o-mini-audio-preview-2024-12-17|
|*anonymous*|gpt-4o-search-preview|
|*anonymous*|gpt-4o-mini-search-preview|
|*anonymous*|gpt-4o-search-preview-2025-03-11|
|*anonymous*|gpt-4o-mini-search-preview-2025-03-11|
|*anonymous*|chatgpt-4o-latest|
|*anonymous*|codex-mini-latest|
|*anonymous*|gpt-4o-mini|
|*anonymous*|gpt-4o-mini-2024-07-18|
|*anonymous*|gpt-4-turbo|
|*anonymous*|gpt-4-turbo-2024-04-09|
|*anonymous*|gpt-4-0125-preview|
|*anonymous*|gpt-4-turbo-preview|
|*anonymous*|gpt-4-1106-preview|
|*anonymous*|gpt-4-vision-preview|
|*anonymous*|gpt-4|
|*anonymous*|gpt-4-0314|
|*anonymous*|gpt-4-0613|
|*anonymous*|gpt-4-32k|
|*anonymous*|gpt-4-32k-0314|
|*anonymous*|gpt-4-32k-0613|
|*anonymous*|gpt-3.5-turbo|
|*anonymous*|gpt-3.5-turbo-16k|
|*anonymous*|gpt-3.5-turbo-0301|
|*anonymous*|gpt-3.5-turbo-0613|
|*anonymous*|gpt-3.5-turbo-1106|
|*anonymous*|gpt-3.5-turbo-0125|
|*anonymous*|gpt-3.5-turbo-16k-0613|
|*anonymous*|none|
|*anonymous*|auto|
|*anonymous*|low|
|*anonymous*|medium|
|*anonymous*|high|
|*anonymous*|auto|
|*anonymous*|default|
|*anonymous*|flex|
|*anonymous*|scale|
|*anonymous*|none|
|*anonymous*|auto|
|*anonymous*|required|

<h2 id="tocS_openai__types__chat__completion_create_params__Function">openai__types__chat__completion_create_params__Function</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__chat__completion_create_params__function"></a>
<a id="schema_openai__types__chat__completion_create_params__Function"></a>
<a id="tocSopenai__types__chat__completion_create_params__function"></a>
<a id="tocsopenai__types__chat__completion_create_params__function"></a>

```json
{
  "name": "string",
  "description": "string",
  "parameters": {}
}

```

Function

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|description|string|false|none|none|
|parameters|object|false|none|none|

<h2 id="tocS_openai__types__completion_create_params__CompletionCreateParamsNonStreaming">openai__types__completion_create_params__CompletionCreateParamsNonStreaming</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__completion_create_params__completioncreateparamsnonstreaming"></a>
<a id="schema_openai__types__completion_create_params__CompletionCreateParamsNonStreaming"></a>
<a id="tocSopenai__types__completion_create_params__completioncreateparamsnonstreaming"></a>
<a id="tocsopenai__types__completion_create_params__completioncreateparamsnonstreaming"></a>

```json
{
  "model": "string",
  "prompt": "string",
  "best_of": 0,
  "echo": true,
  "frequency_penalty": 0,
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": 0,
  "max_tokens": 0,
  "n": 0,
  "presence_penalty": 0,
  "seed": 0,
  "stop": "string",
  "stream_options": {
    "include_usage": true
  },
  "suffix": "string",
  "temperature": 0,
  "top_p": 0,
  "user": "string",
  "stream": false
}

```

CompletionCreateParamsNonStreaming

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[integer]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[array]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|best_of|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|echo|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|frequency_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logit_bias|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|n|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|presence_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stop|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stream_options|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionStreamOptionsParam](#schemachatcompletionstreamoptionsparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|suffix|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|temperature|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_p|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|string|false|none|none|
|stream|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|gpt-3.5-turbo-instruct|
|*anonymous*|davinci-002|
|*anonymous*|babbage-002|

<h2 id="tocS_openai__types__completion_create_params__CompletionCreateParamsStreaming">openai__types__completion_create_params__CompletionCreateParamsStreaming</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__completion_create_params__completioncreateparamsstreaming"></a>
<a id="schema_openai__types__completion_create_params__CompletionCreateParamsStreaming"></a>
<a id="tocSopenai__types__completion_create_params__completioncreateparamsstreaming"></a>
<a id="tocsopenai__types__completion_create_params__completioncreateparamsstreaming"></a>

```json
{
  "model": "string",
  "prompt": "string",
  "best_of": 0,
  "echo": true,
  "frequency_penalty": 0,
  "logit_bias": {
    "property1": 0,
    "property2": 0
  },
  "logprobs": 0,
  "max_tokens": 0,
  "n": 0,
  "presence_penalty": 0,
  "seed": 0,
  "stop": "string",
  "stream_options": {
    "include_usage": true
  },
  "suffix": "string",
  "temperature": 0,
  "top_p": 0,
  "user": "string",
  "stream": true
}

```

CompletionCreateParamsStreaming

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|prompt|any|true|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[integer]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[array]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|best_of|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|echo|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|frequency_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logit_bias|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» **additionalProperties**|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|logprobs|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|max_tokens|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|n|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|presence_penalty|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|seed|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|integer|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stop|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[string]|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stream_options|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[ChatCompletionStreamOptionsParam](#schemachatcompletionstreamoptionsparam)|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|suffix|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|temperature|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|top_p|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|number|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|string|false|none|none|
|stream|boolean|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|gpt-3.5-turbo-instruct|
|*anonymous*|davinci-002|
|*anonymous*|babbage-002|

<h2 id="tocS_openai__types__shared_params__function_definition__FunctionDefinition">openai__types__shared_params__function_definition__FunctionDefinition</h2>
<!-- backwards compatibility -->
<a id="schemaopenai__types__shared_params__function_definition__functiondefinition"></a>
<a id="schema_openai__types__shared_params__function_definition__FunctionDefinition"></a>
<a id="tocSopenai__types__shared_params__function_definition__functiondefinition"></a>
<a id="tocsopenai__types__shared_params__function_definition__functiondefinition"></a>

```json
{
  "name": "string",
  "description": "string",
  "parameters": {},
  "strict": true
}

```

FunctionDefinition

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|description|string|false|none|none|
|parameters|object|false|none|none|
|strict|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|boolean|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

<h2 id="tocS_vllm__entrypoints__openai__protocol__ChatCompletionNamedToolChoiceParam">vllm__entrypoints__openai__protocol__ChatCompletionNamedToolChoiceParam</h2>
<!-- backwards compatibility -->
<a id="schemavllm__entrypoints__openai__protocol__chatcompletionnamedtoolchoiceparam"></a>
<a id="schema_vllm__entrypoints__openai__protocol__ChatCompletionNamedToolChoiceParam"></a>
<a id="tocSvllm__entrypoints__openai__protocol__chatcompletionnamedtoolchoiceparam"></a>
<a id="tocsvllm__entrypoints__openai__protocol__chatcompletionnamedtoolchoiceparam"></a>

```json
{
  "function": {
    "name": "string"
  },
  "type": "function"
}

```

ChatCompletionNamedToolChoiceParam

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|function|[ChatCompletionNamedFunction](#schemachatcompletionnamedfunction)|true|none|none|
|type|string|false|none|none|

<h2 id="tocS_vllm__entrypoints__openai__protocol__FunctionDefinition">vllm__entrypoints__openai__protocol__FunctionDefinition</h2>
<!-- backwards compatibility -->
<a id="schemavllm__entrypoints__openai__protocol__functiondefinition"></a>
<a id="schema_vllm__entrypoints__openai__protocol__FunctionDefinition"></a>
<a id="tocSvllm__entrypoints__openai__protocol__functiondefinition"></a>
<a id="tocsvllm__entrypoints__openai__protocol__functiondefinition"></a>

```json
{
  "name": "string",
  "description": "string",
  "parameters": {}
}

```

FunctionDefinition

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|description|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|parameters|any|false|none|none|

anyOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|

or

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|null|false|none|none|


# Rostro API

Rostro endpoints provide AI-powered features for multimedia generation, character chat management, and content organization. For use as an OpenAI mimic, use the URL: 'https://api.rostro.dev/v1'. For use as an MCP server, use the URL: 'https://proto.rostro.dev/mcp'.

## Base URL

```
https://api.rostro.dev
```

## Authentication

The Rostro API supports three authentication methods:

1. **CH-API-KEY**: API Key authentication using the `CH-API-KEY` header
2. **Authorization**: Bearer token authentication using the `Authorization` header
3. **samwise**: Custom authentication scheme

### Authentication Header Format

```http
Authorization: Bearer <your_token>
```

or

```http
CH-API-KEY: <your_api_key>
```

---

## Endpoints

### POST /tags

**Description**: Get all tags with counts, optionally by namespace.

**Tags**: Read-Only

**Parameters**: None (query parameters in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to TagsQuery schema) | TagsQuery | Yes | Query parameters for tags |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/tags \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```

**Example Response**:

```json
{
  "tags": []
}
```

---

### PUT /api/project/{project_id}/metadata

**Description**: Update the metadata for this project.

**Tags**: Projects

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to CommonMetadataUpdate schema) | CommonMetadataUpdate | Yes | Metadata update information |

**Example Request**:

```bash
curl -X PUT https://api.rostro.dev/api/project/172700/metadata \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### GET /api/gallery

**Description**: Fetch the gallery of all images for all projects.

**Tags**: Projects

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| nsfw | Query | boolean | No | Include NSFW content (default: true) |
| page | Query | integer | No | Page number (default: 1) |
| limit | Query | integer | No | Results per page (default: 24) |
| count | Query | boolean | No | Whether to return the total count or not (default: true) |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/gallery?page=1&limit=24&nsfw=true&count=true" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "items": [],
  "total": 0,
  "page": 1,
  "limit": 24
}
```

---

### GET /api/gallery/project/{project_id}

**Description**: Fetch the gallery of images for this project.

**Tags**: Projects

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |
| nsfw | Query | boolean | No | Include NSFW content (default: true) |
| page | Query | integer | No | Page number (default: 1) |
| limit | Query | integer | No | Results per page (default: 24) |
| count | Query | boolean | No | Whether to return the total count or not (default: true) |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/gallery/project/172700?page=1&limit=24" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "items": [],
  "total": 0
}
```

---

### POST /api/gallery/upload

**Description**: Upload to the gallery of images.

**Tags**: Projects

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to ImageUploadRequest schema) | ImageUploadRequest | Yes | Image upload data |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/gallery/upload \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```

**Example Response**:

```json
{
  "uuid": "3e41a43b-4ffc-41dd-8ad8-5cb6846b9160",
  "url": "https://example.com/image.jpg"
}
```

---

### POST /api/infer/emotion

**Description**: Infer the emotion of a string.

**Tags**: Unstable

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to EmotionRequest schema) | EmotionRequest | Yes | Text to analyze for emotion |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/infer/emotion \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"text": "I am very happy today!"}'
```

**Example Response**:

```json
{
  "emotion": "joy",
  "confidence": 0.95
}
```

---

### DELETE /api/gallery/{uuid}

**Description**: Delete an image from the gallery.

**Tags**: Projects

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| uuid | Path | string | Yes | Image UUID (example: "3e41a43b-4ffc-41dd-8ad8-5cb6846b9160") |
| projectId | Query | integer | No | Optional. The project to dissociate it from. Used when the requester does not own the image, but owns the associated project |

**Example Request**:

```bash
curl -X DELETE "https://api.rostro.dev/api/gallery/3e41a43b-4ffc-41dd-8ad8-5cb6846b9160" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/tags/{project_id}/{tagname}

**Description**: Add a tag to this entity.

**Tags**: Unstable

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |
| tagname | Path | string | Yes | Tag name (example: "HOT") |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/tags/172700/HOT \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### DELETE /api/tags/{project_id}/{tagname}

**Description**: Remove a tag from this entity.

**Tags**: Unstable

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |
| tagname | Path | string | Yes | Tag name (example: "HOT") |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/api/tags/172700/HOT \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### GET /api/users/{username}

**Description**: Get the profile for this user.

**Tags**: Read-Only

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username (example: "You") |
| nsfw | Query | string | No | true or false |
| nsfl | Query | boolean | No | true or false (default: true) |
| exclude_mine | Query | boolean | No | Whether to exclude your private and unlisted projects (default: false) |
| include_projects | Query | boolean | No | Whether to also fetch their projects (default: true) |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/users/You?include_projects=true" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "username": "You",
  "projects": []
}
```

---

### GET /api/leaderboard/v1

**Description**: Get the user leaderboard.

**Tags**: Read-Only

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| order_by | Query | LeaderSortEnum | No | The field to order by (default: "avg_msgs_chat") |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/leaderboard/v1?order_by=avg_msgs_chat" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "leaders": []
}
```

---

### POST /lore

**Description**: Make a RAG lore request.

**Tags**: Lore

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to LoreQuery schema) | LoreQuery | Yes | Lore query parameters |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/lore \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```

**Example Response**:

```json
{
  "results": []
}
```

---

### POST /lore/item

**Description**: Add an unstructured item.

**Tags**: Lore

**Parameters**: None (multipart form data)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to Body_add_lore_item_lore_item_post schema) | multipart/form-data | Yes | Lore item data |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/lore/item \
  -H "Authorization: Bearer <token>" \
  -F "file=@lore_item.txt"
```

**Example Response**:

```json
{
  "uuid": "1b6c5288-731c-4345-a756-1b02ee8e080f",
  "content": "..."
}
```

---

### GET /lore/items

**Description**: Get unstructured items for these owners.

**Tags**: Read-Only

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to LoreFetch schema) | LoreFetch | Yes | Owner IDs to fetch lore items for |

**Example Request**:

```bash
curl -X GET https://api.rostro.dev/lore/items \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"owner_ids": [2108776]}'
```

**Example Response**:

```json
{
  "items": []
}
```

---

### DELETE /lore/{owner_id}/item/{uuid}

**Description**: Remove an unstructured item.

**Tags**: Lore

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| uuid | Path | string | Yes | Item UUID (example: "1b6c5288-731c-4345-a756-1b02ee8e080f") |
| owner_id | Path | integer | Yes | Owner ID (minimum: 1, example: 2108776) |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/lore/2108776/item/1b6c5288-731c-4345-a756-1b02ee8e080f \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### GET /search

**Description**: Do Internal Search

**Tags**: None specified

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| search | Query | string | No | Full-text search of definitions (max 300 chars) |
| exact_search | Query | string | No | Full-text exact search of definitions (max 300 chars) |
| name_like | Query | string | No | Simple name search (max 200 chars) |
| first | Query | integer | No | Number of results per page (max 500, default: 40) |
| min_users_chatted | Query | integer | No | Minimum number of users chatted with it |
| tags | Query | string | No | Comma-separated list of tags to include (example: 'OC,CAI', max 3000 chars, default: "") |
| exclude_tags | Query | string | No | Comma-separated list of tags to exclude (example: 'NSFL,Furry', max 3000 chars, default: "") |
| page | Query | integer | No | Page number of results (default: 1) |
| sort | Query | SortEnum | No | Field to sort by (default: "download_count") |
| asc | Query | boolean | No | Whether to sort ascending (True) or descending (False) (default: false) |
| include_forks | Query | boolean | No | Whether to return forks or only root items (default: false) |
| nsfw | Query | boolean | No | Whether to include NSFW items (default: false) |
| nsfl | Query | boolean | No | Whether to include NSFL items (default: false) |
| nsfw_only | Query | boolean | No | Whether to include only NSFW items (default: false) |
| require_images | Query | boolean | No | Exclude results without usage gallery images (default: false) |
| require_example_dialogues | Query | boolean | No | Exclude results without example dialogues (default: false) |
| require_alternate_greetings | Query | boolean | No | Exclude results without alternate greetings (default: false) |
| require_custom_prompt | Query | boolean | No | Exclude results without a custom main/NSFW prompt (default: false) |
| max_days_ago | Query | integer | No | Maximum age in days of the log |
| exclude_mine | Query | boolean | No | Exclude your private and unlisted projects (default: false) |
| only_mine | Query | AccessLevel | No | Whether to only get your projects |
| min_tokens | Query | integer | No | Minimum token count (default: 200) |
| max_tokens | Query | integer | No | Maximum token count |
| require_expressions | Query | boolean | No | Whether to require an expression pack (default: false) |
| require_lore | Query | boolean | No | Require either an embedded or linked lorebook (default: false) |
| mine_first | Query | boolean | No | Return your projects and your liked projects first (default: false) |
| require_lore_embedded | Query | boolean | No | Require an embedded lorebook (default: false) |
| require_lore_linked | Query | boolean | No | Require a linked lorebook (default: false) |
| my_favorites | Query | boolean | No | Only return items you have favorited (default: false) |
| topics | Query | string | No | Comma-separated list of tags to include (max 3000 chars, default: "") |
| excludetopics | Query | string | No | Comma-separated list of tags to exclude (max 3000 chars, default: "") |
| special_mode | Query | Special | No | Special mode filter |
| creator_id | Query | integer | No | Creator ID to filter by |
| namespace | Query | string | No | Namespace filter |
| username | Query | string | No | Username filter |
| inclusive_or | Query | boolean | No | For multiple tags, return matches for ANY (True) or ALL (False) tags (default: false) |
| recommended_verified | Query | boolean | No | Only return recommended and verified projects (default: false) |
| min_tags | Query | integer | No | Exclude results with less than this many tags |
| count | Query | boolean | No | Whether to return the total count or not (default: false) |
| min_ai_rating | Query | integer | No | Minimum rating of the card |
| language | Query | string | No | If included, only returns cards in this language |
| cursor | Query | string | No | Pagination cursor |
| max_messages | Query | integer | No | Maximum number of messages |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/search?search=fantasy&page=1&first=40&nsfw=false" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "results": [],
  "total": 0,
  "page": 1
}
```

---

### POST /search

**Description**: Do Internal Search Bypass

**Tags**: None specified

**Parameters**: Same as GET /search

**Example Request**:

```bash
curl -X POST "https://api.rostro.dev/search?search=fantasy&page=1" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "results": [],
  "total": 0
}
```

---

### POST /minisearch

**Description**: A quick search just by names.

**Tags**: None specified

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to MiniSearch schema) | MiniSearch | Yes | Mini search query |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/minisearch \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"query": "character"}'
```

**Example Response**:

```json
{
  "results": []
}
```

---

### POST /imagine

**Description**: A unified endpoint for multimedia asset generation.

**Tags**: Imagine

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| return_immediate | Query | boolean | No | Return immediately without waiting for generation (default: false) |

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to GenerationRequest schema) | GenerationRequest | Yes | Generation request parameters |

**Example Request**:

```bash
curl -X POST "https://api.rostro.dev/imagine?return_immediate=false" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"prompt": "A fantasy landscape"}'
```

**Example Response**:

```json
{
  "generation_uuid": "b9ae-6f64957f986a",
  "primary_media_url": "https://example.com/generated.jpg",
  "is_done": true,
  "is_failed": false
}
```

---

### POST /imagine/history

**Description**: A unified endpoint for fetching multimedia asset generation history.

**Tags**: Imagine

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to HistoryRequest schema) | HistoryRequest | Yes | History request parameters |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/imagine/history \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```

**Example Response**:

```json
{
  "items": [],
  "cursor": null,
  "previous_cursor": null
}
```

---

### POST /imagine/history/delete

**Description**: Delete the media with these uuids.

**Tags**: Imagine

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to DeletionRequest schema) | DeletionRequest | Yes | UUIDs to delete |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/imagine/history/delete \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"uuids": ["b9ae-6f64957f986a"]}'
```

**Example Response**:

```json
{
  "successes": ["b9ae-6f64957f986a"],
  "failures": []
}
```

---

### GET /api/project/{project_id}/ratings

**Description**: Get the ratings for this project.

**Tags**: Read-Only

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |

**Example Request**:

```bash
curl -X GET https://api.rostro.dev/api/project/172700/ratings \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "ratings": [],
  "average": 0
}
```

---

### POST /api/project/{project_id}/ratings/disable

**Description**: Disable ratings for this project.

**Tags**: Projects

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/project/172700/ratings/disable \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/project/{project_id}/ratings/enable

**Description**: Enable ratings for this project.

**Tags**: Projects

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/project/172700/ratings/enable \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/project/{project_id}/rate

**Description**: Make or update a rating for this project.

**Tags**: Projects

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to UserRating schema) | UserRating | Yes | Rating information |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/project/172700/rate \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"rating": 5}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### GET /api/account

**Description**: Get user account information.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| stripe_url | Query | boolean | No | Whether to make a stripe billing link (example: true) |
| tokens | Query | boolean | No | Whether to return token information (default: true, example: true) |
| blocks | Query | boolean | No | Whether to return blocked user and tag information (default: true, example: true) |
| nocache | Query | string | No | Do not cache results. For forcing the browser to reload. Does not change the API response |
| no_cache | Query | string | No | Do not cache results. For forcing the browser to reload. Does not change the API response |
| badges | Query | boolean | No | Whether to fetch user badges (default: false) |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/account?tokens=true&blocks=true" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "username": "user",
  "email": "user@example.com",
  "tokens": 1000,
  "blocked_users": [],
  "blocked_tags": []
}
```

---

### DELETE /api/account

**Description**: Delete this account completely and irreversibly.

**Tags**: User Account

**Parameters**: None

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/api/account \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/account/block/{block_type}/{name}

**Description**: Block yourself from viewing these in search.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| block_type | Path | Blockable | Yes | Type of item to block |
| name | Path | string | Yes | Name of item to block |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/account/block/tag/NSFW \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### DELETE /api/account/block/{block_type}/{name}

**Description**: Unblock yourself from viewing these in search.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| block_type | Path | Blockable | Yes | Type of item to unblock |
| name | Path | string | Yes | Name of item to unblock |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/api/account/block/tag/NSFW \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/account/blacklist

**Description**: Prevent users from commenting specific words/phrases on your pages.

**Tags**: User Account

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to WordBlacklist schema) | WordBlacklist | Yes | Word/phrase to blacklist |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/account/blacklist \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"word": "spam"}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/account/blacklist/remove

**Description**: Remove a word from your blacklist.

**Tags**: User Account

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to WordBlacklist schema) | WordBlacklist | Yes | Word/phrase to remove from blacklist |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/account/blacklist/remove \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"word": "spam"}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/account/sort/{order}

**Description**: Set a default sort order in search.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| order | Path | SortEnum | Yes | Sort order to set as default |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/account/sort/download_count \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### GET /api/self

**Description**: Get truncated user account information.

**Tags**: User Account

**Parameters**: None

**Example Request**:

```bash
curl -X GET https://api.rostro.dev/api/self \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "username": "user",
  "id": 12345
}
```

---

### DELETE /follow/tag/{tagname}

**Description**: Unfollow a tag.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| tagname | Path | string | Yes | Tag name to unfollow |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/follow/tag/Fantasy \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /follow/tag/{tagname}

**Description**: Follow a tag.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| tagname | Path | string | Yes | Tag name to follow |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/follow/tag/Fantasy \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### DELETE /api/follow/{username}

**Description**: Unfollow a username.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username to unfollow (example: "You") |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/api/follow/You \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/follow/{username}

**Description**: Follow a username.

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username to follow (example: "You") |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/follow/You \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/follows/{username}

**Description**: Get who a given username follows.

**Tags**: Read-Only

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username (example: "You") |
| page | Query | integer | No | Page to return (default: 1) |
| count | Query | boolean | No | Whether to return the total count or not (default: true) |
| asc | Query | boolean | No | Whether to sort ascending (True) or descending (False) (default: false) |
| min_ai_rating | Query | integer | No | Minimum rating of the card |
| nsfw | Query | boolean | No | Whether to include NSFW items (default: true) |
| nsfl | Query | boolean | No | Whether to include NSFL items (default: true) |

**Example Request**:

```bash
curl -X POST "https://api.rostro.dev/api/follows/You?page=1" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "follows": [],
  "total": 0
}
```

---

### GET /api/follows/{username}

**Description**: Get who a given username follows.

**Tags**: Read-Only

**Parameters**: Same as POST /api/follows/{username}

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/follows/You?page=1" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "follows": [],
  "total": 0
}
```

---

### GET /api/followers/{username}

**Description**: Get who follows a given username.

**Tags**: Read-Only

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username (example: "You") |
| page | Query | integer | No | Page to return (default: 1) |
| count | Query | boolean | No | Whether to return the total count or not (default: true) |
| asc | Query | boolean | No | Whether to sort ascending (True) or descending (False) (default: false) |
| min_ai_rating | Query | integer | No | Minimum rating of the card |
| nsfw | Query | boolean | No | Whether to include NSFW items (default: true) |
| nsfl | Query | boolean | No | Whether to include NSFL items (default: true) |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/followers/You?page=1" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "followers": [],
  "total": 0
}
```

---

### GET /api/timeline/v1

**Description**: Get recent updates from people you follow.

**Tags**: Read-Only

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| page | Query | integer | No | Page to return (default: 1) |
| count | Query | boolean | No | Whether to return the total count or not (default: true) |
| asc | Query | boolean | No | Whether to sort ascending (True) or descending (False) (default: false) |
| min_ai_rating | Query | integer | No | Minimum rating of the card |
| nsfw | Query | boolean | No | Whether to include NSFW items (default: true) |
| nsfl | Query | boolean | No | Whether to include NSFL items (default: true) |

**Example Request**:

```bash
curl -X GET "https://api.rostro.dev/api/timeline/v1?page=1" \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "items": [],
  "total": 0
}
```

---

### GET /atproto/{username}

**Description**: Get the configured atproto for this username for Bluesky.

**Tags**: Read-Only

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username (example: "You") |

**Example Request**:

```bash
curl -X GET https://api.rostro.dev/atproto/You
```

**Example Response**:

```json
{
  "atproto": "did:plc:..."
}
```

---

### POST /api/core/characters

**Description**: Create char

**Tags**: Chat

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to CharacterCreate schema) | CharacterCreate | Yes | Character creation data |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/core/characters \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"name": "MyCharacter"}'
```

**Example Response**:

```json
{
  "message": "success",
  "character_id": 12345
}
```

---

### DELETE /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}

**Description**: Remove a linked lorebook for a character.

**Tags**: Chat

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username (example: "You") |
| pathname | Path | string | Yes | Project Slug or ID (example: "expressions-extension-5cb6846b9160") |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 12338) |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/api/core/characters/link/You/expressions-extension-5cb6846b9160/lorebook/12338 \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}

**Description**: Add a linked lorebook for a character.

**Tags**: Chat

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username (example: "You") |
| pathname | Path | string | Yes | Project Slug or ID (example: "expressions-extension-5cb6846b9160") |
| project_id | Path | integer | Yes | Project ID (minimum: 1, example: 172700) |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/core/characters/link/You/expressions-extension-5cb6846b9160/lorebook/172700 \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### PUT /api/core/characters/{username}/{pathname}

**Description**: Update char

**Tags**: Chat

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| username | Path | string | Yes | Username (example: "You") |
| pathname | Path | string | Yes | Project Slug or ID (example: "expressions-extension-5cb6846b9160") |

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to CharacterUpdate schema) | CharacterUpdate | Yes | Character update data |

**Example Request**:

```bash
curl -X PUT https://api.rostro.dev/api/core/characters/You/expressions-extension-5cb6846b9160 \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"name": "UpdatedCharacter"}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/self/username

**Description**: Attempt to change your username.

**Tags**: Unstable

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to UsernameChangeRequest schema) | UsernameChangeRequest | Yes | New username |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/self/username \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"username": "NewUsername"}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /api/check/username

**Description**: Check if username is taken.

**Tags**: Unstable

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to UsernameChangeRequest schema) | UsernameChangeRequest | Yes | Username to check |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/api/check/username \
  -H "Content-Type: application/json" \
  -d '{"username": "TestUser"}'
```

**Example Response**:

```json
{
  "available": true
}
```

---

### POST /config/{config_id}/{sub_id}

**Description**: Upsert a config

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| config_id | Path | string | Yes | Configuration ID (example: "3242362") |
| sub_id | Path | string | Yes | Sub ID |

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to ConfigUpsert schema) | ConfigUpsert | Yes | Configuration data |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/config/3242362/sub1 \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### DELETE /config/{config_id}/{sub_id}

**Description**: Delete config

**Tags**: User Account

**Parameters**:

| Name | In (Path/Query) | Type | Required | Description |
| :--- | :--- | :--- | :--- | :--- |
| config_id | Path | string | Yes | Configuration ID (example: "3242362") |
| sub_id | Path | string | Yes | Sub ID |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/config/3242362/sub1 \
  -H "Authorization: Bearer <token>"
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### POST /config

**Description**: Upsert configs

**Tags**: User Account

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to ConfigsUpsert schema) | ConfigsUpsert | Yes | Multiple configuration data |

**Example Request**:

```bash
curl -X POST https://api.rostro.dev/config \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"configs": []}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

### DELETE /config

**Description**: Delete configs

**Tags**: User Account

**Parameters**: None (data in request body)

**Request Body**:

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| (Refer to ConfigsDelete schema) | ConfigsDelete | Yes | Configuration IDs to delete |

**Example Request**:

```bash
curl -X DELETE https://api.rostro.dev/config \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"config_ids": []}'
```

**Example Response**:

```json
{
  "message": "success"
}
```

---

## Error Handling

The Rostro API uses standard HTTP status codes to indicate the success or failure of requests:

| Status Code | Description |
| :--- | :--- |
| 200 | Successful Response - Request completed successfully |
| 400 | Bad Request - The request was malformed or invalid |
| 401 | Unauthorized - Authentication credentials are missing or invalid |
| 403 | Forbidden - The authenticated user doesn't have permission to access this resource |
| 404 | Not Found - The requested resource doesn't exist |
| 422 | Validation Error - Request validation failed (check request body/parameters) |
| 500 | Internal Server Error - An error occurred on the server |

### Error Response Format

Error responses follow these schema formats:

**UserError** (400, 401, 403, 404):
```json
{
  "detail": "Error message describing what went wrong"
}
```

**APIError** (500):
```json
{
  "detail": "Internal server error message"
}
```

**HTTPValidationError** (422):
```json
{
  "detail": [
    {
      "loc": ["body", "field_name"],
      "msg": "Validation error message",
      "type": "value_error"
    }
  ]
}
```

---

## Schemas

### Core Response Schemas

**APIResponse**
- Generic success response
- Fields: `message` (string)

**Account**
- User account information
- Fields: username, email, tokens, blocked users, blocked tags, etc.

**AccountLite**
- Truncated user account information
- Fields: username, id

**Gallery**
- Gallery response with items
- Fields: items (array), total, page, limit

**GalleryItem**
- Individual gallery item
- Fields: uuid, url, metadata

**Tags**
- Tags collection
- Fields: tags (array with counts)

**LoreResult**
- Lore query results
- Fields: results (array)

**LoreItem**
- Individual lore item
- Fields: uuid, content, owner_id

**LoreItems**
- Collection of lore items
- Fields: items (array)

**ImaginedItem**
- Generated media item
- Fields: generation_uuid, cost, primary_media_url, description, is_done, is_failed, uuid, user_id, secondary_media_urls, error, note

**ImaginedItems**
- Collection of generated media
- Fields: items (array), previous_cursor, cursor

**DeletionResponse**
- Deletion operation results
- Fields: successes (array), failures (array)

**RatingsResponse**
- Project ratings
- Fields: ratings (array), average

**FollowsObject**
- User follows information
- Fields: follows (array), total

**SearchResults**
- Search results
- Fields: items (array), total, page

**WrappedSearch**
- Wrapped search results with metadata
- Fields: results, total, page, cursor

**MiniSearchResponse**
- Mini search results
- Fields: results (array)

**LeaderResults**
- Leaderboard results
- Fields: leaders (array)

### Request Schemas

**TagsQuery**
- Query parameters for tags search
- Used in POST /tags

**CommonMetadataUpdate**
- Project metadata update
- Used in PUT /api/project/{project_id}/metadata

**ImageUploadRequest**
- Image upload data
- Used in POST /api/gallery/upload

**EmotionRequest**
- Emotion analysis request
- Fields: text (string)

**LoreQuery**
- Lore query parameters
- Used in POST /lore

**LoreFetch**
- Lore fetch parameters
- Fields: owner_ids (array)

**GenerationRequest**
- Media generation request
- Used in POST /imagine

**HistoryRequest**
- Generation history request
- Used in POST /imagine/history

**DeletionRequest**
- Media deletion request
- Fields: uuids (array)

**UserRating**
- User rating data
- Fields: rating (integer)

**CharacterCreate**
- Character creation data
- Fields: name, description, etc.

**CharacterUpdate**
- Character update data
- Fields: name, description, etc.

**UsernameChangeRequest**
- Username change/check request
- Fields: username (string)

**ConfigUpsert**
- Configuration upsert data
- Fields: config data

**ConfigsUpsert**
- Multiple configurations upsert
- Fields: configs (array)

**ConfigsDelete**
- Configuration deletion request
- Fields: config_ids (array)

**WordBlacklist**
- Word blacklist data
- Fields: word (string)

**MiniSearch**
- Mini search query
- Fields: query (string)

### Enum Schemas

**SortEnum**
- Sorting options (e.g., download_count, creation_date, etc.)

**LeaderSortEnum**
- Leaderboard sorting options (e.g., avg_msgs_chat)

**AccessLevel**
- Access level options (public, private, unlisted)

**Special**
- Special mode filter options

**Blockable**
- Blockable item types (user, tag)

### Complex Schemas

**LayerInfo**
- Layer information for projects
- Fields: width, height, dpi, z_index, opacity, duration, visible, locked, start_time, end_time, in_point, out_point, effects, children

**Rejection**
- Rejection information for failed generations
- Fields: reason (RejectionReason enum), location

**RejectionReason**
- Enum: unknown, explicit_text, explicit_image, malformed_image, out_of_credits

**HTTPValidationError**
- Validation error details
- Fields: detail (array of validation errors)

---

## Notes

- **API Version**: 0.5.9
- **Base URLs**: 
  - Main API: `https://api.rostro.dev`
  - OpenAI Mimic: `https://api.rostro.dev/v1`
  - MCP Server: `https://proto.rostro.dev/mcp`
- **Terms of Service**: https://rostro.dev/tos
- **Support Email**: support@rostro.dev
- All endpoints require authentication unless otherwise specified
- Most endpoints support pagination using `page` parameter
- NSFW/NSFL filtering is available on many endpoints
- The API uses standard REST conventions
- Rate limiting may apply (not specified in OpenAPI spec)
- All timestamps should be in ISO 8601 format
- File uploads use multipart/form-data encoding

---

## Additional Information

For more detailed information about specific schemas, refer to the `components/schemas` section of the OpenAPI specification. Many endpoints share common parameters and response formats, particularly around pagination, filtering, and error handling.

The API is organized into several functional areas:
- **Projects**: Managing character projects and metadata
- **Gallery**: Image management and uploads
- **Lore**: RAG-based lore system for characters
- **Imagine**: Multimedia asset generation
- **Chat**: Character chat management
- **User Account**: User profile and preferences
- **Search**: Content discovery and filtering
- **Social**: Following, tags, and timeline features

For integration support or questions, contact support@rostro.dev.

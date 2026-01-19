> Rostro endpoints. For use as an OpenAI mimic, use the URL: https://api.rostro.dev/v1. For use as an MCP server, use the URL: https://proto.rostro.dev/mcp.
> 
Base URL
 * OpenAI Mimic: https://api.rostro.dev/v1
 * MCP Server: https://proto.rostro.dev/mcp
 * Standard API: https://api.rostro.dev
Authentication
The API utilizes API Keys and Bearer tokens. You generally need to include one of the following headers with your request:
 * Authorization: Bearer <your_token>
 * CH-API-KEY: <your_api_key>
 * samwise: <token> (Internal/Specific use)
Code Snippet:
# Using Authorization Header
curl -H "Authorization: Bearer YOUR_TOKEN" https://api.rostro.dev/v1/models

# Using API Key Header
curl -H "CH-API-KEY: YOUR_API_KEY" https://api.rostro.dev/v1/models

Endpoints
POST /tags
Description: Get all tags with counts, optionally by namespace.
Parameters:
None
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| namespace | string | No | Optional namespace to filter tags. |
| limit | integer | No | Limit the number of tags returned. |
Example Request:
curl -X POST "https://api.rostro.dev/tags" \
  -H "Content-Type: application/json" \
  -d '{ "namespace": "creatures", "limit": 10 }'

Example Response:
{
  "tags": [
    { "name": "dragon", "count": 42 },
    { "name": "elf", "count": 15 }
  ]
}

PUT /api/project/{project_id}/metadata
Description: Update the metadata for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | The ID of the project (e.g., 172700). |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| title | string | No | New title. |
| description | string | No | New description. |
| tags | array | No | List of tag strings. |
Example Request:
curl -X PUT "https://api.rostro.dev/api/project/172700/metadata" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "title": "New Title", "tags": ["fantasy", "wip"] }'

Example Response:
{ "success": true, "message": "Metadata updated." }

GET /api/gallery
Description: Fetch the gallery of all images for all projects.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| nsfw | Query | boolean | No | Include NSFW content. Default: true. |
| page | Query | integer | No | Page number. Default: 1. |
| limit | Query | integer | No | Items per page. Default: 24. |
| count | Query | boolean | No | Return total count. Default: true. |
Example Request:
curl -X GET "https://api.rostro.dev/api/gallery?nsfw=false&limit=10" \
  -H "Authorization: Bearer <token>"

Example Response:
{
  "count": 100,
  "nodes": [ { "uuid": "img-1", "primary_image_path": "/path/img.png" } ],
  "page": 1
}

GET /api/gallery/project/{project_id}
Description: Fetch the gallery of images for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | The Project ID. |
| nsfw | Query | boolean | No | Include NSFW content. |
| page | Query | integer | No | Page number. |
| limit | Query | integer | No | Items per page. |
| count | Query | boolean | No | Return total count. |
Example Request:
curl -X GET "https://api.rostro.dev/api/gallery/project/172700" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "count": 5, "nodes": [], "page": 1 }

POST /api/gallery/upload
Description: Upload to the gallery of images.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| image | string | Yes | Base64 encoded image string or URL. |
| project_id | integer | Yes | Project ID to attach to. |
| caption | string | No | Optional caption. |
Example Request:
curl -X POST "https://api.rostro.dev/api/gallery/upload" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "project_id": 172700, "image": "data:image/png;base64,..." }'

Example Response:
{ "uuid": "abc-123", "primary_image_path": "/img.png" }

POST /api/infer/emotion
Description: Infer the emotion of a string.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| text | string | Yes | Text to analyze. |
Example Request:
curl -X POST "https://api.rostro.dev/api/infer/emotion" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "text": "I am so happy!" }'

Example Response:
{ "emotion": "joy", "score": 0.9 }

DELETE /api/gallery/{uuid}
Description: Delete an image from the gallery.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| uuid | Path | string | Yes | Image UUID. |
| projectId | Query | integer | No | Optional project ID to dissociate from (if not owner). |
Example Request:
curl -X DELETE "https://api.rostro.dev/api/gallery/3e41a43b-..." \
  -H "Authorization: Bearer <token>"

Example Response:
{ "success": true }

POST /api/tags/{project_id}/{tagname}
Description: Add a tag to this entity.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| tagname | Path | string | Yes | Tag name. |
Example Request:
curl -X POST "https://api.rostro.dev/api/tags/172700/cool" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "success": true }

DELETE /api/tags/{project_id}/{tagname}
Description: Remove a tag from this entity.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| tagname | Path | string | Yes | Tag name. |
Example Request:
curl -X DELETE "https://api.rostro.dev/api/tags/172700/cool" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "success": true }

GET /api/users/{username}
Description: Get the profile for this user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username (or "You"). |
| nsfw | Query | string | No | Filter NSFW. |
| nsfl | Query | boolean | No | Filter NSFL. Default: true. |
| exclude_mine | Query | boolean | No | Exclude private projects. Default: false. |
| include_projects | Query | boolean | No | Include projects in response. Default: true. |
Example Request:
curl -X GET "https://api.rostro.dev/api/users/You" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "username": "You", "bio": "..." }

GET /api/leaderboard/v1
Description: Get the user leaderboard.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| order_by | Query | string | No | Sort field. Default: avg_msgs_chat. |
Example Request:
curl -X GET "https://api.rostro.dev/api/leaderboard/v1" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "users": [ { "username": "TopUser", "score": 9000 } ] }

POST /lore
Description: Make a RAG lore request.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| query | string | Yes | The query string. |
| filters | object | No | Optional filters. |
Example Request:
curl -X POST "https://api.rostro.dev/lore" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "query": "history of the world" }'

Example Response:
{ "results": [ { "text": "...", "score": 0.8 } ] }

POST /lore/item
Description: Add an unstructured item.
Request Body:
Multipart Form Data
| Field | Type | Required | Description |
|---|---|---|---|
| file | file | Yes | The file or text content to upload. |
| metadata | string | No | JSON metadata. |
Example Request:
curl -X POST "https://api.rostro.dev/lore/item" \
  -H "Authorization: Bearer <token>" \
  -F "file=@lore.txt"

Example Response:
{ "uuid": "lore-uuid", "status": "indexed" }

GET /lore/items
Description: Get unstructured items for these owners.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| owner_ids | array | Yes | List of owner IDs. |
Example Request:
curl -X GET "https://api.rostro.dev/lore/items" \
  -H "Authorization: Bearer <token>" \
  -d '{ "owner_ids": [123] }'

Example Response:
{ "items": [] }

DELETE /lore/{owner_id}/item/{uuid}
Description: Remove an unstructured item.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| uuid | Path | string | Yes | Item UUID. |
| owner_id | Path | integer | Yes | Owner ID. |
Example Request:
curl -X DELETE "https://api.rostro.dev/lore/123/item/uuid-456" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "success": true }

GET /search
Description: Do Internal Search.
Parameters (Subset of common params):
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| search | Query | string | No | Full-text search string. |
| tags | Query | string | No | Comma-separated tags. |
| sort | Query | string | No | Sort field (e.g., download_count). |
| page | Query | integer | No | Page number. |
| nsfw | Query | boolean | No | Include NSFW. |
Example Request:
curl -X GET "https://api.rostro.dev/search?search=rpg&sort=download_count" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "results": [], "count": 0 }

POST /search
Description: Do Internal Search Bypass (Post method).
Parameters: Same as GET /search.
Example Request:
curl -X POST "https://api.rostro.dev/search?search=rpg" \
  -H "Authorization: Bearer <token>"

POST /minisearch
Description: A quick search just by names.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| name | string | Yes | Name to search for. |
Example Request:
curl -X POST "https://api.rostro.dev/minisearch" \
  -H "Content-Type: application/json" \
  -d '{ "name": "Gandalf" }'

Example Response:
{ "results": [ { "name": "Gandalf", "id": 1 } ] }

POST /imagine
Description: A unified endpoint for multimedia asset generation.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| return_immediate | Query | boolean | No | Default false. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| prompt | string | No | Description of generation. |
| generation_type | string | No | e.g., text_to_image. |
| width | integer | No | Canvas width. |
| height | integer | No | Canvas height. |
| model | string | No | Model name. |
Example Request:
curl -X POST "https://api.rostro.dev/imagine" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "prompt": "cyberpunk city", "generation_type": "text_to_image" }'

Example Response:
{ "generation_uuid": "gen-1", "is_done": true, "primary_media_url": "url.png" }

POST /imagine/history
Description: Fetch generation history.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| first | integer | No | Number of results (default 10). |
| generated_only | boolean | No | Only return generated items. |
Example Request:
curl -X POST "https://api.rostro.dev/imagine/history" \
  -H "Authorization: Bearer <token>" \
  -d '{ "first": 5 }'

Example Response:
{ "items": [] }

POST /imagine/history/delete
Description: Delete media by UUIDs.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| uuids | array | No | List of UUID strings. |
Example Request:
curl -X POST "https://api.rostro.dev/imagine/history/delete" \
  -H "Authorization: Bearer <token>" \
  -d '{ "uuids": ["uuid-1"] }'

Example Response:
{ "successes": ["uuid-1"], "failures": [] }

GET /api/project/{project_id}/ratings
Description: Get ratings for a project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X GET "https://api.rostro.dev/api/project/172700/ratings" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "ratings": [], "average": 4.5 }

POST /api/project/{project_id}/ratings/disable
Description: Disable ratings for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X POST "https://api.rostro.dev/api/project/172700/ratings/disable" \
  -H "Authorization: Bearer <token>"

POST /api/project/{project_id}/ratings/enable
Description: Enable ratings for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X POST "https://api.rostro.dev/api/project/172700/ratings/enable" \
  -H "Authorization: Bearer <token>"

POST /api/project/{project_id}/rate
Description: Make or update a rating.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| rating | integer | Yes | Star rating (1-5). |
| comment | string | No | Review text. |
Example Request:
curl -X POST "https://api.rostro.dev/api/project/172700/rate" \
  -H "Authorization: Bearer <token>" \
  -d '{ "rating": 5, "comment": "Good!" }'

GET /api/account
Description: Get user account information.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| tokens | Query | boolean | No | Return tokens. Default: true. |
Example Request:
curl -X GET "https://api.rostro.dev/api/account" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "username": "Me", "credits": 500 }

DELETE /api/account
Description: Delete this account completely.
Example Request:
curl -X DELETE "https://api.rostro.dev/api/account" \
  -H "Authorization: Bearer <token>"

POST /api/account/block/{block_type}/{name}
Description: Block a user or tag.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| block_type | Path | string | Yes | e.g. user. |
| name | Path | string | Yes | Name to block. |
Example Request:
curl -X POST "https://api.rostro.dev/api/account/block/user/BadGuy" \
  -H "Authorization: Bearer <token>"

DELETE /api/account/block/{block_type}/{name}
Description: Unblock a user or tag.
Parameters: Same as POST.
Example Request:
curl -X DELETE "https://api.rostro.dev/api/account/block/user/BadGuy" \
  -H "Authorization: Bearer <token>"

POST /api/account/blacklist
Description: Blacklist a word/phrase.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| word | string | Yes | The word to blacklist. |
Example Request:
curl -X POST "https://api.rostro.dev/api/account/blacklist" \
  -H "Authorization: Bearer <token>" \
  -d '{ "word": "spam" }'

POST /api/account/blacklist/remove
Description: Remove a word from blacklist.
Request Body: Same as POST.
Example Request:
curl -X POST "https://api.rostro.dev/api/account/blacklist/remove" \
  -H "Authorization: Bearer <token>" \
  -d '{ "word": "spam" }'

POST /api/account/sort/{order}
Description: Set default sort order.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| order | Path | string | Yes | Sort enum. |
Example Request:
curl -X POST "https://api.rostro.dev/api/account/sort/newest" \
  -H "Authorization: Bearer <token>"

GET /api/self
Description: Get truncated user info.
Example Request:
curl -X GET "https://api.rostro.dev/api/self" \
  -H "Authorization: Bearer <token>"

POST /follow/tag/{tagname}
Description: Follow a tag.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| tagname | Path | string | Yes | Tag name. |
Example Request:
curl -X POST "https://api.rostro.dev/follow/tag/anime" \
  -H "Authorization: Bearer <token>"

DELETE /follow/tag/{tagname}
Description: Unfollow a tag.
Example Request:
curl -X DELETE "https://api.rostro.dev/follow/tag/anime" \
  -H "Authorization: Bearer <token>"

POST /api/follow/{username}
Description: Follow a user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
Example Request:
curl -X POST "https://api.rostro.dev/api/follow/User1" \
  -H "Authorization: Bearer <token>"

DELETE /api/follow/{username}
Description: Unfollow a user.
Example Request:
curl -X DELETE "https://api.rostro.dev/api/follow/User1" \
  -H "Authorization: Bearer <token>"

POST /api/follows/{username}
Description: Get who a user follows.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| page | Query | integer | No | Page number. |
Example Request:
curl -X POST "https://api.rostro.dev/api/follows/You?page=1" \
  -H "Authorization: Bearer <token>"

Example Response:
{ "count": 10, "users": [] }

GET /api/follows/{username}
Description: Get who a user follows (GET).
Parameters: Same as POST.
GET /api/followers/{username}
Description: Get who follows a user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| page | Query | integer | No | Page number. |
Example Request:
curl -X GET "https://api.rostro.dev/api/followers/You?page=1" \
  -H "Authorization: Bearer <token>"

GET /api/timeline/v1
Description: Get recent updates from people you follow.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| page | Query | integer | No | Page number. |
Example Request:
curl -X GET "https://api.rostro.dev/api/timeline/v1" \
  -H "Authorization: Bearer <token>"

GET /atproto/{username}
Description: Get Bluesky config for user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
Example Request:
curl -X GET "https://api.rostro.dev/atproto/You"

POST /api/core/characters
Description: Create a character.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| name | string | Yes | Character name. |
| description | string | No | Description. |
Example Request:
curl -X POST "https://api.rostro.dev/api/core/characters" \
  -H "Authorization: Bearer <token>" \
  -d '{ "name": "Hero" }'

POST /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}
Description: Add linked lorebook to character.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| pathname | Path | string | Yes | Character slug. |
| project_id | Path | integer | Yes | Lorebook Project ID. |
Example Request:
curl -X POST "https://api.rostro.dev/api/core/characters/link/You/char1/lorebook/123" \
  -H "Authorization: Bearer <token>"

DELETE /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}
Description: Remove linked lorebook.
Parameters: Same as POST.
PUT /api/core/characters/{username}/{pathname}
Description: Update character.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| pathname | Path | string | Yes | Character slug. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| name | string | No | New name. |
Example Request:
curl -X PUT "https://api.rostro.dev/api/core/characters/You/char1" \
  -H "Authorization: Bearer <token>" \
  -d '{ "name": "Super Hero" }'

POST /api/self/username
Description: Attempt to change username.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| new_username | string | Yes | Requested name. |
Example Request:
curl -X POST "https://api.rostro.dev/api/self/username" \
  -H "Authorization: Bearer <token>" \
  -d '{ "new_username": "CoolName" }'

POST /api/check/username
Description: Check if username is taken.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| new_username | string | Yes | Name to check. |
Example Request:
curl -X POST "https://api.rostro.dev/api/check/username" \
  -d '{ "new_username": "CoolName" }'

POST /config/{config_id}/{sub_id}
Description: Upsert a config.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| config_id | Path | string | Yes | Config ID. |
| sub_id | Path | string | Yes | Sub ID. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| value | object | Yes | Config value. |
Example Request:
curl -X POST "https://api.rostro.dev/config/user/settings" \
  -H "Authorization: Bearer <token>" \
  -d '{ "value": { "theme": "dark" } }'

DELETE /config/{config_id}/{sub_id}
Description: Delete config.
Parameters: Same as POST.
POST /engine/api/editor/scene/{scene_id}/events
Description: Home Scene Event.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| scene_id | Path | string | Yes | The ID of the scene. |
Request Body:
This endpoint accepts a dynamic JSON object (Dictionary/Map) with additional properties.
| Field | Type | Required | Description |
|---|---|---|---|
| (Key) | Any | No | Dynamic key-value pairs representing the event data. |
Example Request:
curl -X POST "https://api.rostro.dev/engine/api/editor/scene/scene-123/events" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "type": "click",
    "target": "button_start",
    "timestamp": 1678900000
  }'

Example Response:
{}

POST /engine/api/editor/scene/{scene_id}/opened
Description: Home Scene Opened.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| scene_id | Path | string | Yes | The ID of the scene. |
Example Request:
curl -X POST "https://api.rostro.dev/engine/api/editor/scene/scene-123/opened" \
  -H "Authorization: Bearer <token>"

Example Response:
{}

POST /engine/api/editor/scene/{scene_id}/tips/{tip}
Description: Home Scene Tip.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| scene_id | Path | string | Yes | The ID of the scene. |
| tip | Path | string | Yes | The tip identifier. |
Example Request:
curl -X POST "https://api.rostro.dev/engine/api/editor/scene/scene-123/tips/welcome" \
  -H "Authorization: Bearer <token>"

Example Response:
{}

GET /engine/api/file
Description: Home File.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| url | Query | string | Yes | The file URL. |
Example Request:
curl -X GET "https://api.rostro.dev/engine/api/file?url=file:///projects/test/main.js" \
  -H "Authorization: Bearer <token>"

Example Response:
{}

GET /engine/api/assets
Description: Assets List.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| search | Query | string | No | Search term. |
| sort | Query | string | No | Sort field. |
| limit | Query | integer | No | Limit results. |
Example Request:
curl -X GET "https://api.rostro.dev/engine/api/assets?limit=10" \
  -H "Authorization: Bearer <token>"

Example Response:
{}

POST /engine/api/assets
Description: Asset Create.
Request Body:
Multipart Form Data
| Field | Type | Required | Description |
|---|---|---|---|
| file | file | Yes | The asset file. |
| metadata | string | No | Metadata JSON. |
Example Request:
curl -X POST "https://api.rostro.dev/engine/api/assets" \
  -H "Authorization: Bearer <token>" \
  -F "file=@image.png"

POST /chub/{model}/v1/chat/completions
Description: OpenAI Mimic API endpoint for chat completions. The {model} in the path overrides the body parameter.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| model | Path | string | Yes | The inference model to use (e.g., gpt-4). |
Request Body:
Standard OpenAI Chat Completion schema.
| Field | Type | Required | Description |
|---|---|---|---|
| messages | array | Yes | List of message objects. |
| stream | boolean | No | Whether to stream the response. |
Example Request:
curl -X POST "https://api.rostro.dev/chub/gpt-4/v1/chat/completions" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "messages": [{"role": "user", "content": "Hello!"}],
    "stream": false
  }'

Example Response:
{
  "id": "chatcmpl-123",
  "object": "chat.completion",
  "created": 1677652288,
  "model": "gpt-4",
  "choices": [{
    "index": 0,
    "message": { "role": "assistant", "content": "Hello there!" },
    "finish_reason": "stop"
  }]
}

Error Handling
| Code | Meaning | Description |
|---|---|---|
| 200 | OK | Request succeeded. |
| 400 | Bad Request | Invalid syntax or parameters (e.g., malformed JSON). |
| 401 | Unauthorized | Missing or invalid authentication token. |
| 403 | Forbidden | Valid token but insufficient permissions. |
| 404 | Not Found | Resource or endpoint does not exist. |
| 422 | Validation Error | Request body failed schema validation (e.g., missing fields). |
| 500 | Internal Server Error | Server failed to process the request. |


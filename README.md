# Rostro API

> Rostro endpoints. For use as an OpenAI mimic, use the URL: `https://api.rostro.dev/v1`. For use as an MCP server, use the URL: `https://proto.rostro.dev/mcp`.

## Base URLs

| Environment | URL |
| :--- | :--- |
| **OpenAI Mimic** | `https://api.rostro.dev/v1` |
| **MCP Server** | `https://proto.rostro.dev/mcp` |
| **Standard API** | `https://api.rostro.dev` |

## Authentication

The API authentication is handled via HTTP Headers. You must include one of the following headers in your requests:

1.  **Authorization**: Standard Bearer token.
2.  **CH-API-KEY**: Custom header for API keys.
3.  **samwise**: Internal/Specific token usage.

### Code Snippets

**Using Bearer Token:**
```bash
curl -H "Authorization: Bearer <your_token>" [https://api.rostro.dev/api/account](https://api.rostro.dev/api/account)

Using API Key:
curl -H "CH-API-KEY: <your_api_key>" [https://api.rostro.dev/api/account](https://api.rostro.dev/api/account)

Endpoints
POST /tags
Description: Get all tags with counts, optionally by namespace.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| namespace | string | No | Optional namespace to filter tags. |
| limit | integer | No | Limit the number of tags returned. |
Example Request:
curl -X POST "[https://api.rostro.dev/tags](https://api.rostro.dev/tags)" \
  -H "Content-Type: application/json" \
  -d '{ "namespace": "fantasy", "limit": 20 }'

Example Response:
{
  "tags": [
    { "name": "elf", "count": 120 },
    { "name": "orc", "count": 85 }
  ]
}

PUT /api/project/{project_id}/metadata
Description: Update the metadata for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID (e.g. 172700). |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| title | string | No | New title. |
| description | string | No | New description. |
| tags | array | No | List of tags. |
Example Request:
curl -X PUT "[https://api.rostro.dev/api/project/172700/metadata](https://api.rostro.dev/api/project/172700/metadata)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "title": "New Title", "description": "Updated info" }'

GET /api/gallery
Description: Fetch the gallery of all images for all projects.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| nsfw | Query | boolean | No | Include NSFW content (default: true). |
| page | Query | integer | No | Page number (default: 1). |
| limit | Query | integer | No | Limit per page (default: 24). |
| count | Query | boolean | No | Return total count. |
Example Request:
curl -X GET "[https://api.rostro.dev/api/gallery?limit=10&page=1](https://api.rostro.dev/api/gallery?limit=10&page=1)" \
  -H "Authorization: Bearer <token>"

Example Response:
{
  "count": 500,
  "nodes": [ { "uuid": "img-uuid", "primary_image_path": "url" } ],
  "page": 1
}

GET /api/gallery/project/{project_id}
Description: Fetch the gallery of images for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| nsfw | Query | boolean | No | Include NSFW content. |
| page | Query | integer | No | Page number. |
| limit | Query | integer | No | Limit per page. |
| count | Query | boolean | No | Return total count. |
Example Request:
curl -X GET "[https://api.rostro.dev/api/gallery/project/172700](https://api.rostro.dev/api/gallery/project/172700)" \
  -H "Authorization: Bearer <token>"

POST /api/gallery/upload
Description: Upload to the gallery of images.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| image | string | Yes | Base64 encoded image or URL. |
| project_id | integer | Yes | Project ID to attach to. |
| caption | string | No | Optional caption. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/gallery/upload](https://api.rostro.dev/api/gallery/upload)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "project_id": 172700, "image": "data:image/png;base64,..." }'

Example Response:
{
  "uuid": "new-uuid",
  "primary_image_path": "https://path/to/image.png"
}

POST /api/infer/emotion
Description: Infer the emotion of a string.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| text | string | Yes | The text to analyze. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/infer/emotion](https://api.rostro.dev/api/infer/emotion)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "text": "I am so happy today!" }'

Example Response:
{
  "emotion": "joy",
  "confidence": 0.98
}

DELETE /api/gallery/{uuid}
Description: Delete an image from the gallery.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| uuid | Path | string | Yes | Image UUID. |
| projectId | Query | integer | No | Optional Project ID to dissociate it from. |
Example Request:
curl -X DELETE "[https://api.rostro.dev/api/gallery/3e41a43b-4ffc-41dd-8ad8-5cb6846b9160](https://api.rostro.dev/api/gallery/3e41a43b-4ffc-41dd-8ad8-5cb6846b9160)" \
  -H "Authorization: Bearer <token>"

POST /api/tags/{project_id}/{tagname}
Description: Add a tag to this entity.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| tagname | Path | string | Yes | Tag name. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/tags/172700/cool](https://api.rostro.dev/api/tags/172700/cool)" \
  -H "Authorization: Bearer <token>"

DELETE /api/tags/{project_id}/{tagname}
Description: Remove a tag from this entity.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| tagname | Path | string | Yes | Tag name. |
Example Request:
curl -X DELETE "[https://api.rostro.dev/api/tags/172700/cool](https://api.rostro.dev/api/tags/172700/cool)" \
  -H "Authorization: Bearer <token>"

GET /api/users/{username}
Description: Get the profile for this user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username (or "You"). |
| nsfw | Query | string | No | true or false. |
| nsfl | Query | boolean | No | true or false (default: true). |
| exclude_mine | Query | boolean | No | Exclude private projects. |
| include_projects | Query | boolean | No | Include their projects. |
Example Request:
curl -X GET "[https://api.rostro.dev/api/users/You](https://api.rostro.dev/api/users/You)" \
  -H "Authorization: Bearer <token>"

Example Response:
{
  "username": "User",
  "bio": "Developer",
  "stats": {}
}

GET /api/leaderboard/v1
Description: Get the user leaderboard.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| order_by | Query | string | No | Field to order by (default: avg_msgs_chat). |
Example Request:
curl -X GET "[https://api.rostro.dev/api/leaderboard/v1](https://api.rostro.dev/api/leaderboard/v1)" \
  -H "Authorization: Bearer <token>"

POST /lore
Description: Make a RAG lore request.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| query | string | Yes | The query string. |
| limit | integer | No | Max results. |
Example Request:
curl -X POST "[https://api.rostro.dev/lore](https://api.rostro.dev/lore)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "query": "history of kingdom" }'

Example Response:
{
  "results": [ { "content": "The kingdom was founded in...", "score": 0.89 } ]
}

POST /lore/item
Description: Add an unstructured item.
Request Body:
Multipart Form Data
| Field | Type | Required | Description |
|---|---|---|---|
| file | file | Yes | File or text content. |
| metadata | string | No | JSON metadata. |
Example Request:
curl -X POST "[https://api.rostro.dev/lore/item](https://api.rostro.dev/lore/item)" \
  -H "Authorization: Bearer <token>" \
  -F "file=@lore.txt"

GET /lore/items
Description: Get unstructured items for these owners.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| owner_ids | array | Yes | List of owner IDs. |
Example Request:
curl -X GET "[https://api.rostro.dev/lore/items](https://api.rostro.dev/lore/items)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "owner_ids": [123] }'

DELETE /lore/{owner_id}/item/{uuid}
Description: Remove an unstructured item.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| uuid | Path | string | Yes | Item UUID. |
| owner_id | Path | integer | Yes | Owner ID. |
Example Request:
curl -X DELETE "[https://api.rostro.dev/lore/123/item/abc-uuid](https://api.rostro.dev/lore/123/item/abc-uuid)" \
  -H "Authorization: Bearer <token>"

GET /search
Description: Do Internal Search.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| search | Query | string | No | Full-text search string. |
| exact_search | Query | string | No | Full-text exact search. |
| name_like | Query | string | No | Simple name search. |
| first | Query | integer | No | Results per page (default: 40). |
| tags | Query | string | No | Comma-separated tags. |
| sort | Query | string | No | Sort field. |
| nsfw | Query | boolean | No | Include NSFW. |
| page | Query | integer | No | Page number. |
Example Request:
curl -X GET "[https://api.rostro.dev/search?search=dragon&sort=download_count](https://api.rostro.dev/search?search=dragon&sort=download_count)" \
  -H "Authorization: Bearer <token>"

POST /search
Description: Do Internal Search Bypass (Post method).
Parameters: Same as GET /search.
Example Request:
curl -X POST "[https://api.rostro.dev/search?search=dragon](https://api.rostro.dev/search?search=dragon)" \
  -H "Authorization: Bearer <token>"

POST /minisearch
Description: A quick search just by names.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| name | string | Yes | Name to search. |
Example Request:
curl -X POST "[https://api.rostro.dev/minisearch](https://api.rostro.dev/minisearch)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "name": "Gandalf" }'

POST /imagine
Description: A unified endpoint for multimedia asset generation.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| return_immediate | Query | boolean | No | Return immediately (default: false). |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| prompt | string | No | Generation prompt. |
| generation_type | string | No | Type (e.g. text_to_image). |
| width | integer | No | Canvas width. |
| height | integer | No | Canvas height. |
| model | string | No | Model name. |
Example Request:
curl -X POST "[https://api.rostro.dev/imagine](https://api.rostro.dev/imagine)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "prompt": "cyberpunk city", "generation_type": "text_to_image" }'

Example Response:
{
  "generation_uuid": "uuid",
  "primary_media_url": "[https://cdn.url/img.png](https://cdn.url/img.png)",
  "is_done": true
}

POST /imagine/history
Description: Fetch multimedia asset generation history.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| first | integer | No | Number of results (default: 10). |
| generated_only | boolean | No | Only return generated images. |
Example Request:
curl -X POST "[https://api.rostro.dev/imagine/history](https://api.rostro.dev/imagine/history)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "first": 5 }'

POST /imagine/history/delete
Description: Delete the media with these uuids.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| uuids | array | No | List of UUID strings. |
Example Request:
curl -X POST "[https://api.rostro.dev/imagine/history/delete](https://api.rostro.dev/imagine/history/delete)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "uuids": ["uuid-1"] }'

GET /api/project/{project_id}/ratings
Description: Get the ratings for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X GET "[https://api.rostro.dev/api/project/172700/ratings](https://api.rostro.dev/api/project/172700/ratings)" \
  -H "Authorization: Bearer <token>"

POST /api/project/{project_id}/ratings/disable
Description: Disable ratings for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/project/172700/ratings/disable](https://api.rostro.dev/api/project/172700/ratings/disable)" \
  -H "Authorization: Bearer <token>"

POST /api/project/{project_id}/ratings/enable
Description: Enable ratings for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/project/172700/ratings/enable](https://api.rostro.dev/api/project/172700/ratings/enable)" \
  -H "Authorization: Bearer <token>"

POST /api/project/{project_id}/rate
Description: Make or update a rating for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| rating | integer | Yes | Rating value (1-5). |
| comment | string | No | Review comment. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/project/172700/rate](https://api.rostro.dev/api/project/172700/rate)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "rating": 5, "comment": "Good!" }'

GET /api/account
Description: Get user account information.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| tokens | Query | boolean | No | Return token info. |
| blocks | Query | boolean | No | Return block info. |
Example Request:
curl -X GET "[https://api.rostro.dev/api/account](https://api.rostro.dev/api/account)" \
  -H "Authorization: Bearer <token>"

DELETE /api/account
Description: Delete this account completely and irreversibly.
Example Request:
curl -X DELETE "[https://api.rostro.dev/api/account](https://api.rostro.dev/api/account)" \
  -H "Authorization: Bearer <token>"

POST /api/account/block/{block_type}/{name}
Description: Block yourself from viewing these in search.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| block_type | Path | string | Yes | e.g. user. |
| name | Path | string | Yes | Name to block. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/account/block/user/BadUser](https://api.rostro.dev/api/account/block/user/BadUser)" \
  -H "Authorization: Bearer <token>"

DELETE /api/account/block/{block_type}/{name}
Description: Unblock yourself from viewing these in search.
Parameters: Same as POST.
Example Request:
curl -X DELETE "[https://api.rostro.dev/api/account/block/user/BadUser](https://api.rostro.dev/api/account/block/user/BadUser)" \
  -H "Authorization: Bearer <token>"

POST /api/account/blacklist
Description: Prevent users from commenting specific words.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| word | string | Yes | The word to blacklist. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/account/blacklist](https://api.rostro.dev/api/account/blacklist)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "word": "spam" }'

POST /api/account/blacklist/remove
Description: Remove a word from your blacklist.
Request Body: Same as above.
Example Request:
curl -X POST "[https://api.rostro.dev/api/account/blacklist/remove](https://api.rostro.dev/api/account/blacklist/remove)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "word": "spam" }'

POST /api/account/sort/{order}
Description: Set a default sort order in search.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| order | Path | string | Yes | Sort enum. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/account/sort/download_count](https://api.rostro.dev/api/account/sort/download_count)" \
  -H "Authorization: Bearer <token>"

GET /api/self
Description: Get truncated user account information.
Example Request:
curl -X GET "[https://api.rostro.dev/api/self](https://api.rostro.dev/api/self)" \
  -H "Authorization: Bearer <token>"

POST /follow/tag/{tagname}
Description: Follow a tag.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| tagname | Path | string | Yes | Tag name. |
Example Request:
curl -X POST "[https://api.rostro.dev/follow/tag/anime](https://api.rostro.dev/follow/tag/anime)" \
  -H "Authorization: Bearer <token>"

DELETE /follow/tag/{tagname}
Description: Unfollow a tag.
Parameters: Same as POST.
Example Request:
curl -X DELETE "[https://api.rostro.dev/follow/tag/anime](https://api.rostro.dev/follow/tag/anime)" \
  -H "Authorization: Bearer <token>"

POST /api/follow/{username}
Description: Follow a username.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/follow/User1](https://api.rostro.dev/api/follow/User1)" \
  -H "Authorization: Bearer <token>"

DELETE /api/follow/{username}
Description: Unfollow a username.
Parameters: Same as POST.
Example Request:
curl -X DELETE "[https://api.rostro.dev/api/follow/User1](https://api.rostro.dev/api/follow/User1)" \
  -H "Authorization: Bearer <token>"

POST /api/follows/{username}
Description: Get who a given username follows.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| page | Query | integer | No | Page number. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/follows/You?page=1](https://api.rostro.dev/api/follows/You?page=1)" \
  -H "Authorization: Bearer <token>"

GET /api/follows/{username}
Description: Get who a given username follows (GET version).
Parameters: Same as POST.
GET /api/followers/{username}
Description: Get who follows a given username.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| page | Query | integer | No | Page number. |
Example Request:
curl -X GET "[https://api.rostro.dev/api/followers/You?page=1](https://api.rostro.dev/api/followers/You?page=1)" \
  -H "Authorization: Bearer <token>"

GET /api/timeline/v1
Description: Get recent updates from people you follow.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| page | Query | integer | No | Page number. |
Example Request:
curl -X GET "[https://api.rostro.dev/api/timeline/v1](https://api.rostro.dev/api/timeline/v1)" \
  -H "Authorization: Bearer <token>"

GET /atproto/{username}
Description: Get the configured atproto for this username for Bluesky.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
Example Request:
curl -X GET "[https://api.rostro.dev/atproto/You](https://api.rostro.dev/atproto/You)"

POST /api/core/characters
Description: Create char.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| name | string | Yes | Character name. |
| description | string | Yes | Description. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/core/characters](https://api.rostro.dev/api/core/characters)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "name": "Hero", "description": "A brave hero." }'

POST /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}
Description: Add a linked lorebook for a character.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| pathname | Path | string | Yes | Character Slug. |
| project_id | Path | integer | Yes | Lorebook Project ID. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/core/characters/link/You/char/lorebook/123](https://api.rostro.dev/api/core/characters/link/You/char/lorebook/123)" \
  -H "Authorization: Bearer <token>"

DELETE /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}
Description: Remove a linked lorebook for a character.
Parameters: Same as POST.
PUT /api/core/characters/{username}/{pathname}
Description: Update char.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| pathname | Path | string | Yes | Character Slug. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| name | string | No | New name. |
| description | string | No | New description. |
Example Request:
curl -X PUT "[https://api.rostro.dev/api/core/characters/You/char](https://api.rostro.dev/api/core/characters/You/char)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "name": "Super Hero" }'

POST /api/self/username
Description: Attempt to change your username.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| new_username | string | Yes | Requested username. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/self/username](https://api.rostro.dev/api/self/username)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "new_username": "NewMe" }'

POST /api/check/username
Description: Check if username is taken.
Request Body: Same as above.
Example Request:
curl -X POST "[https://api.rostro.dev/api/check/username](https://api.rostro.dev/api/check/username)" \
  -d '{ "new_username": "NewMe" }'

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
| value | object | Yes | Arbitrary JSON config value. |
Example Request:
curl -X POST "[https://api.rostro.dev/config/user/settings](https://api.rostro.dev/config/user/settings)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "value": { "theme": "dark" } }'

DELETE /config/{config_id}/{sub_id}
Description: Delete config.
Parameters: Same as POST.
POST /config
Description: Upsert multiple configs.
Request Body:
JSON object containing multiple config upserts.
DELETE /config
Description: Delete multiple configs.
POST /config/fetch
Description: Fetch configs.
Request Body:
JSON object with fetch criteria.
GET /oauth/userinfo
Description: Fetches information about the user's account.
Example Request:
curl -X GET "[https://api.rostro.dev/oauth/userinfo](https://api.rostro.dev/oauth/userinfo)" \
  -H "Authorization: Bearer <token>"

Example Response:
{
  "identity": "user-123",
  "username": "MyUser",
  "credits": 100
}

POST /api/media/video/upload
Description: Upload a video or animation.
Request Body:
Multipart Form Data
| Field | Type | Required | Description |
|---|---|---|---|
| file | file | Yes | Video file. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/media/video/upload](https://api.rostro.dev/api/media/video/upload)" \
  -H "Authorization: Bearer <token>" \
  -F "file=@video.mp4"

POST /api/favorites/{project_id}
Description: Favorite a project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/favorites/172700](https://api.rostro.dev/api/favorites/172700)" \
  -H "Authorization: Bearer <token>"

DELETE /api/favorites/{project_id}
Description: Unfavorite a project.
Parameters: Same as POST.
GET /api/projects/similar/{project_id}/{no_nsfl_enum}/{no_nsfw_enum}
Description: Get recommended projects for a project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| no_nsfl_enum | Path | string | Yes | Boolean string. |
| no_nsfw_enum | Path | string | Yes | Boolean string. |
GET /api/favorites
Description: Get favorited projects.
Example Request:
curl -X GET "[https://api.rostro.dev/api/favorites](https://api.rostro.dev/api/favorites)" \
  -H "Authorization: Bearer <token>"

POST /api/reports
Description: Report a project.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| project_id | integer | Yes | Project ID. |
| reason | string | Yes | Report reason. |
POST /api/ratings/reports
Description: Report a rating.
DELETE /api/project/{project_id}
Description: Delete a project permanently.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
DELETE /api/project/{username}/{pathname}
Description: Delete a project permanently (by path).
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| pathname | Path | string | Yes | Project slug. |
DELETE /api/project/{namespace}/{username}/{pathname}
Description: Delete a project permanently (full path).
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| namespace | Path | string | Yes | Namespace. |
| username | Path | string | Yes | Username. |
| pathname | Path | string | Yes | Project slug. |
GET /api/characters/{project_id}/expressions
Description: Get expression packs for the character.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
POST /api/characters/{project_id}/expressions
Description: Upsert an expression pack.
DELETE /api/characters/{project_id}/expressions/{tagname}
Description: Delete an expression pack.
GET /api/notifications
Description: Get user account notifications.
POST /api/notifications
Description: Get user account notifications (POST variant).
DELETE /api/notifications
Description: Dismiss all user account notifications.
DELETE /api/notifications/{notification_id}
Description: Dismiss a notification.
DELETE /api/notifications/announcement/{announcement_id}
Description: Dismiss an announcement.
GET /api/badges
Description: Get all badges.
GET /api/badges/{badge_id}
Description: Get a specific badge.
POST /api/core/chats
Description: Create a new chat.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| characters | array | Yes | List of character IDs. |
Example Request:
curl -X POST "[https://api.rostro.dev/api/core/chats](https://api.rostro.dev/api/core/chats)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "characters": ["You/Char1"] }'

GET /api/core/chats
Description: Search (or get all) chats for user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| limit | Query | integer | No | Max chats. |
| search | Query | string | No | Search term. |
POST /api/core/chats/import
Description: Create a new chat from import.
GET /api/core/chats/{chat_id}/messages/{msgid}
Description: Get chat message.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| chat_id | Path | integer | Yes | Chat ID. |
| msgid | Path | integer | Yes | Message ID. |
GET /api/core/chats/{username}/{pathname}/public
Description: Get all public chats for a character.
GET /api/core/chats/{chat_id}/public
Description: Get all public chats for a character by ID.
DELETE /api/core/chats/{chat_id}
Description: Delete chat.
PATCH /api/core/chats/{chat_id}
Description: Update chat.
POST /api/core/chats/bulk/delete
Description: Delete chats in bulk.
POST /live/invite
Description: Make an invite link.
PATCH /live/permissions
Description: Change the permissions of a live user.
POST /live
Description: Get a new live token.
POST /api/core/chats/v2/{chat_id}/messages/content
Description: Get the text of these messages.
DELETE /api/core/chats/{chat_id}/character/{char_id}
Description: Remove character from chat.
POST /api/core/chats/{chat_id}/character/{char_id}
Description: Add character to chat.
POST /api/core/chats/{chat_id}/characters
Description: Add characters to chat.
POST /api/core/chats/{chat_id}/characters/remove
Description: Remove characters from chat.
POST /api/core/chats/{chat_id}/user/{tagname}
Description: Invite user to chat.
DELETE /api/core/chats/{chat_id}/user/{user_id}
Description: Remove user from chat.
GET /api/core/chats/v2/{chat_id}/metatree
Description: Get minimized chat tree by id.
GET /api/core/chats/v2/{chat_id}
Description: Get chat tree by id.
POST /api/core/chats/v2/{chat_id}/messages/atomic
Description: Make a number of operations on messages in an atomic manner.
GET /api/personas
Description: Get personas for a user.
POST /api/personas
Description: Create a new persona.
POST /api/personas/{persona_id}
Description: Update an existing persona.
DELETE /api/personas/{persona_id}
Description: Delete an existing persona.
GET /api/logs/{log_id}/comments
Description: Get the comments on a log.
POST /api/logs/{log_id}/comment
Description: Make or update a comment on a log.
DELETE /logs/{log_id}/comment/{rid}
Description: Delete a comment on a log.
POST /api/logs/{log_id}/react/{rid}
Description: React to a log.
DELETE /api/logs/{log_id}/react/{rid}
Description: Unreact to a log.
POST /reactions/react/{rid}
Description: React to a log.
DELETE /reactions/react/{rid}
Description: Unreact to a log.
GET /api/logs/search
Description: Search (or get all) public logs.
POST /api/suggestions/tags
Description: Create a list of suggested tags for a character.
POST /request/merge
Description: Use to request that two tags be merged.
POST /api/core/lorebooks
Description: Create lorebook.
PUT /api/core/lorebooks/{project_id}
Description: Update lorebook.
POST /api/core/extensions/context
Description: Get semantically related messages from earlier in the chat.
POST /api/chats
Description: Create a new chat, or retrieve latest.
GET /api/core/chats/{chat_id}/users/{user_id}
Description: Get user information for this chat.
POST /presets
Description: Create preset.
POST /presets/active/{preset_id}
Description: Set active preset.
POST /presets/active
Description: Get active preset.
GET /api/account/tokens
Description: Get user account active tokens.
POST /api/account/tokens
Description: Create a new token for the inference API.
POST /account/tokens/projects
Description: Create a new token for the projects API.
POST /api/account/tokens/core
Description: Create a new token for the inference API (core).
DELETE /api/account/token/{token_id}
Description: Revoke a token.
POST /extensions
Description: Create extension.
POST /extension/{extension_id}/files
Description: Atomic file operations on extensions.
POST /minifetch/extension/{extension_id}
Description: A quick extension fetch.
POST /minifetch/extensions/{extension_id}
Description: A quick extensions fetch.
POST /extension/{extension_id}/upload
Description: Upload a zip file.
POST /api/storage/stage/{stage_id}/fetch
Description: Fetch stage storage (Experimental).
POST /api/storage/stage/{stage_id}
Description: Update stage storage (Experimental).
GET /images/costs
Description: Get current costs.
GET /images/mine
Description: Get all images generated under your account.
POST /images/inpaint
Description: Inpaint an image.
POST /images/removebg_mask
Description: Remove background.
POST /music
Description: Create a new music piece.
POST /tts
Description: Text to speech.
GET /voices
Description: Get my voices.
DELETE /voices/{voice_id}
Description: Delete voice.
POST /voice_clone
Description: Create or update a voice clone.
POST /images/text2img
Description: Create an image from a prompt.
POST /images/img2img
Description: Create a new image from a base one.
POST /images/animate
Description: Create a new animation.
POST /video
Description: Create a new video from a prompt.
POST /foley
Description: Create a new sound effect.
POST /images/upscale
Description: Upscale an image.
POST /check
Description: Check on a running task.
POST /imagine/check
Description: Check on a running generation.
POST /stt
Description: Speech to Text.
POST /chub/{model}/v1/chat/completions
Description: OpenAI Mimic API endpoint for chat completions.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| model | Path | string | Yes | Inference model. |
Request Body: CompletionCreateParams
Example Request:
curl -X POST "[https://api.rostro.dev/chub/gpt-4/v1/chat/completions](https://api.rostro.dev/chub/gpt-4/v1/chat/completions)" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "messages": [{"role": "user", "content": "Hi"}], "stream": false }'

POST /chub/{model}/v1/completions
Description: OpenAI Mimic API for completions.
POST /{model}/v1/completions
Description: OpenAI Mimic API for completions.
POST /v1/completions
Description: OpenAI Mimic API for completions.
POST /{model}/v1/chat/completions
Description: OpenAI Mimic API for chat completions.
GET /chub/{model}/v1/models
Description: Fetch available models (filtered by path).
GET /{model}/v1/models
Description: Fetch available models (filtered by path).
POST /v1/chat/completions
Description: OpenAI Mimic API for chat completions (Model ambiguous).
GET /v1/models
Description: Fetch list of all available models.
POST /prompt
Description: Generic completions endpoint.
PATCH /imagine/project/{uuid}
Description: Update imagine project.
GET /imagine/project/{uuid}
Description: Get imagine project.
POST /model3d
Description: Create a 3D model.
POST /images/expressions
Description: Create a sprite pack.
POST /live/voice
Description: Request live voice chat.
DELETE /live/voice/{chat_id}/{agent_id}
Description: End live voice chat.
GET /api/{namespace}/{creator_name}/{project_name}
Description: Fetch Project.
GET /api/{space}/{project_id}
Description: Fetch Character ID.
GET /api/public/{namespace}/{creator_name}/{project_name}
Description: Fetch Project (Public).
GET /api/public/{space}/{project_id}
Description: Fetch Character ID (Public).
GET /forks/project/{project_id}
Description: Get forks for this project.
POST /api/project/{project_id}/fork/v2
Description: Fork a character (V2).
POST /engine/api/apps
Description: App Create.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| (Any) | object | Yes | Arbitrary app data. |
Example Request:
curl -X POST "[https://api.rostro.dev/engine/api/apps](https://api.rostro.dev/engine/api/apps)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "name": "MyApp" }'

GET /engine/api/apps
Description: App List.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| tags | Query | string | No | Filter by tags. |
Example Request:
curl -X GET "[https://api.rostro.dev/engine/api/apps](https://api.rostro.dev/engine/api/apps)" \
  -H "Authorization: Bearer <token>"

DELETE /engine/api/apps/{app_id}
Description: App Delete.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| app_id | Path | string | Yes | App ID. |
Example Request:
curl -X DELETE "[https://api.rostro.dev/engine/api/apps/app-1](https://api.rostro.dev/engine/api/apps/app-1)" \
  -H "Authorization: Bearer <token>"

GET /engine/api/apps/{app_id}
Description: App Get.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| app_id | Path | string | Yes | App ID. |
POST /engine/api/apps/download
Description: App Download.
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| (Any) | object | Yes | Download criteria. |
GET /engine/api/assets
Description: Assets List.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| search | Query | string | No | Search string. |
| regex | Query | boolean | No | Use regex. |
| sort | Query | string | No | Sort field. |
| order | Query | integer | No | Sort order. |
| skip | Query | integer | No | Pagination skip. |
| limit | Query | integer | No | Pagination limit. |
| tags | Query | string | No | Tags filter. |
Example Request:
curl -X GET "[https://api.rostro.dev/engine/api/assets?limit=10](https://api.rostro.dev/engine/api/assets?limit=10)" \
  -H "Authorization: Bearer <token>"

POST /engine/api/assets
Description: Asset Create.
Request Body:
Multipart Form Data
| Field | Type | Required | Description |
|---|---|---|---|
| file | file | Yes | Asset file. |
| metadata | string | No | JSON metadata. |
Example Request:
curl -X POST "[https://api.rostro.dev/engine/api/assets](https://api.rostro.dev/engine/api/assets)" \
  -H "Authorization: Bearer <token>" \
  -F "file=@image.png"

DELETE /engine/api/assets
Description: Asset Delete.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| branchId | Query | string | No | Branch ID. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| assets | array | Yes | List of asset IDs (strings). |
Example Request:
curl -X DELETE "[https://api.rostro.dev/engine/api/assets](https://api.rostro.dev/engine/api/assets)" \
  -H "Authorization: Bearer <token>" \
  -d '["asset-1", "asset-2"]'

GET /engine/api/assets/{asset_id}
Description: Asset Get.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| asset_id | Path | string | Yes | Asset ID. |
PUT /engine/api/assets/{asset_id}
Description: Asset Update.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| asset_id | Path | string | Yes | Asset ID. |
Request Body:
Multipart Form Data
| Field | Type | Required | Description |
|---|---|---|---|
| file | file | No | New file content. |
| metadata | string | No | New metadata. |
GET /engine/api/assets/{asset_id}/file/{filename}
Description: Asset Get File.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| asset_id | Path | string | Yes | Asset ID. |
| filename | Path | string | Yes | Filename. |
| branchId | Query | string | No | Branch ID. |
| immutableBackup | Query | string | No | Backup flag. |
GET /engine/api/assets/{asset_id}/thumbnail/{size}
Description: Asset Get Thumbnail.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| asset_id | Path | string | Yes | Asset ID. |
| size | Path | string | Yes | Size identifier. |
| branchId | Query | string | No | Branch ID. |
POST /engine/api/assets/{asset_id}/reimport
Description: Asset Reimport.
POST /engine/api/assets/{asset_id}/duplicate
Description: Asset Duplicate.
POST /engine/api/assets/paste
Description: Asset Paste.
POST /engine/api/checkpoints
Description: Checkpoint Create.
GET /engine/api/checkpoints/{checkpoint_id}
Description: Checkpoint Get.
POST /engine/api/checkpoints/{checkpoint_id}/restore
Description: Checkpoint Restore.
POST /engine/api/checkpoints/{checkpoint_id}/hardreset
Description: Checkpoint Hard Reset.
GET /engine/api/entities
Description: Entities List.
POST /engine/api/entities
Description: Entity Create.
GET /engine/api/entities/{entity_id}
Description: Entity Get.
PUT /engine/api/entities/{entity_id}
Description: Entity Update.
DELETE /engine/api/entities/{entity_id}
Description: Entity Delete.
GET /engine/api/editor/project/{project_id}/branch
Description: Home Branch.
GET /engine/api/file
Description: Home File.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| url | Query | string | Yes | File URL. |
Example Request:
curl -X GET "[https://api.rostro.dev/engine/api/file?url=file:///](https://api.rostro.dev/engine/api/file?url=file:///)..." \
  -H "Authorization: Bearer <token>"

POST /engine/api/editor/scene/{scene_id}/opened
Description: Home Scene Opened.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| scene_id | Path | string | Yes | Scene ID. |
POST /engine/api/editor/scene/{scene_id}/events
Description: Home Scene Event.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| scene_id | Path | string | Yes | Scene ID. |
Request Body:
| Field | Type | Required | Description |
|---|---|---|---|
| (Any) | object | Yes | Event properties. |
Example Request:
curl -X POST "[https://api.rostro.dev/engine/api/editor/scene/sc-1/events](https://api.rostro.dev/engine/api/editor/scene/sc-1/events)" \
  -H "Authorization: Bearer <token>" \
  -d '{ "type": "click", "timestamp": 12345 }'

POST /engine/api/editor/scene/{scene_id}/tips/{tip}
Description: Home Scene Tip.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| scene_id | Path | string | Yes | Scene ID. |
| tip | Path | string | Yes | Tip identifier. |
POST /engine/api/projects
Description: Project Create.
PUT /engine/api/projects/{project_id}
Description: Project Update.
GET /engine/api/projects/{project_id}
Description: Project Get.
DELETE /engine/api/projects/{project_id}
Description: Project Delete.
POST /engine/api/projects/import
Description: Project Import.
POST /engine/api/projects/{project_id}/export
Description: Project Export.
POST /engine/api/projects/{project_id}/unlock
Description: Project Unlock.
POST /engine/api/projects/{project_id}/transfer
Description: Project Transfer.
POST /engine/api/projects/{project_id}/accept_transfer
Description: Project Accept Transfer.
POST /engine/api/projects/{project_id}/decline_transfer
Description: Project Decline Transfer.
GET /engine/api/projects/{project_id}/activity
Description: Project Activity.
GET /engine/api/projects/{project_id}/collaborators
Description: Project Collab List.
POST /engine/api/projects/{project_id}/collaborators
Description: Project Collab Create.
PUT /engine/api/projects/{project_id}/collaborators/{collab_id}
Description: Project Collab Update.
DELETE /engine/api/projects/{project_id}/collaborators/{collab_id}
Description: Project Collab Delete.
POST /engine/api/projects/{project_id}/image
Description: Project Image.
GET /engine/api/projects/{project_id}/assets
Description: Project Assets.
GET /engine/api/projects/{project_id}/scenes
Description: Project Scenes.
GET /engine/api/projects/{project_id}/branches
Description: Project Branches.
GET /engine/api/projects/{project_id}/apps
Description: Project Apps.
GET /engine/api/projects/{project_id}/repositories
Description: Project Repo.
GET /engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles
Description: Project Repo Sourcefiles List.
GET /engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles/{relative_path}
Description: Project Repo Sourcefile.
DELETE /engine/api/projects/{project_id}/repositories/{repo_service}/sourcefiles/{file_name}
Description: Project Repo Sourcefiles Delete.
POST /engine/api/scenes
Description: Scene Create.
DELETE /engine/api/scenes/{scene_id}
Description: Scene Delete.
GET /engine/api/scenes/{scene_id}
Description: Scene Get.
GET /engine/api/editor/scene/{scene_id}
Description: Edit Scene.
POST /engine/api/upload/start-upload
Description: Upload Start.
POST /engine/api/upload/signed-urls
Description: Upload Urls.
POST /engine/api/upload/complete-upload
Description: Upload Complete.
POST /engine/api/watch
Description: Watch Create.
DELETE /engine/api/watch/{watch_id}
Description: Watch Delete.
Error Handling
| Code | Meaning | Description |
|---|---|---|
| 200 | OK | Request succeeded. |
| 400 | Bad Request | Invalid syntax or parameters. |
| 401 | Unauthorized | Authentication failed or missing. |
| 403 | Forbidden | Valid token but insufficient permissions. |
| 404 | Not Found | Resource or endpoint does not exist. |
| 422 | Validation Error | Request body failed schema validation. |
| 500 | Internal Server Error | Server failed to process the request. |



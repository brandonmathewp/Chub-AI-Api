> Rostro endpoints. For use as an OpenAI mimic, use the URL: https://api.rostro.dev/v1. For use as an MCP server, use the URL: https://proto.rostro.dev/mcp.
> 
Base URL
 * OpenAI Mimic: https://api.rostro.dev/v1
 * MCP Server: https://proto.rostro.dev/mcp
 * Standard API: https://api.rostro.dev (Implied from context, though the spec focuses on the mimic URLs)
Authentication
The API utilizes API Keys and Bearer tokens for security. Most endpoints require one of the following security schemes:
 * Authorization Header: Standard bearer token or API key.
 * CH-API-KEY Header: Custom header for API key.
Example Request Header:
Authorization: Bearer <your_token>

OR
CH-API-KEY: <your_api_key>

Endpoints
POST /tags
Description: Get all tags with counts, optionally by namespace.
Request Body: TagsQuery
| Field | Type | Required | Description |
|---|---|---|---|
| namespace | string | No | Optional namespace filter. |
Example Request:
curl -X POST "https://api.rostro.dev/tags" \
  -H "Content-Type: application/json" \
  -d '{
    "namespace": "general"
  }'

Example Response:
{
  "tags": [
    { "name": "horror", "count": 150 },
    { "name": "scifi", "count": 89 }
  ]
}

PUT /api/project/{project_id}/metadata
Description: Update the metadata for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID (e.g., 172700) |
Request Body: CommonMetadataUpdate
| Field | Type | Required | Description |
|---|---|---|---|
| title | string | No | New title for the project. |
| description | string | No | New description. |
| tags | array | No | List of tags. |
Example Request:
curl -X PUT "https://api.rostro.dev/api/project/172700/metadata" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "New Project Title",
    "description": "Updated description"
  }'

Example Response:
{
  "success": true,
  "message": "Metadata updated successfully"
}

GET /api/gallery
Description: Fetch the gallery of all images for all projects.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| nsfw | Query | boolean | No | Include NSFW content (default: true). |
| page | Query | integer | No | Page number (default: 1). |
| limit | Query | integer | No | Items per page (default: 24). |
| count | Query | boolean | No | Return total count (default: true). |
Example Request:
curl -X GET "https://api.rostro.dev/api/gallery?nsfw=true&page=1&limit=24" \
  -H "Authorization: Bearer <token>"

Example Response:
{
  "count": 100,
  "nodes": [
    { "uuid": "img-uuid-1", "primary_image_path": "path/to/img.png" }
  ],
  "page": 1
}

GET /api/gallery/project/{project_id}
Description: Fetch the gallery of images for a specific project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| nsfw | Query | boolean | No | Include NSFW content. |
| page | Query | integer | No | Page number. |
| limit | Query | integer | No | Items per page. |
| count | Query | boolean | No | Return total count. |
Example Request:
curl -X GET "https://api.rostro.dev/api/gallery/project/172700?page=1" \
  -H "Authorization: Bearer <token>"

POST /api/gallery/upload
Description: Upload to the gallery of images.
Request Body: ImageUploadRequest
| Field | Type | Required | Description |
|---|---|---|---|
| image | string | Yes | Base64 encoded image or URL. |
| project_id | integer | Yes | ID of the project to attach to. |
| caption | string | No | Image caption. |
Example Request:
curl -X POST "https://api.rostro.dev/api/gallery/upload" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "project_id": 172700,
    "image": "data:image/png;base64,..."
  }'

Example Response:
{
  "uuid": "new-image-uuid",
  "primary_image_path": "https://cdn.rostro.dev/img.png",
  "user_owned": true
}

POST /api/infer/emotion
Description: Infer the emotion of a string.
Request Body: EmotionRequest
| Field | Type | Required | Description |
|---|---|---|---|
| text | string | Yes | The text to analyze. |
Example Request:
curl -X POST "https://api.rostro.dev/api/infer/emotion" \
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
| projectId | Query | integer | No | Optional Project ID to dissociate. |
Example Request:
curl -X DELETE "https://api.rostro.dev/api/gallery/3e41a43b-4ffc-41dd-8ad8-5cb6846b9160" \
  -H "Authorization: Bearer <token>"

POST /api/tags/{project_id}/{tagname}
Description: Add a tag to an entity.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| tagname | Path | string | Yes | Tag name (e.g., HOT). |
Example Request:
curl -X POST "https://api.rostro.dev/api/tags/172700/HOT" \
  -H "Authorization: Bearer <token>"

DELETE /api/tags/{project_id}/{tagname}
Description: Remove a tag from an entity.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
| tagname | Path | string | Yes | Tag name. |
Example Request:
curl -X DELETE "https://api.rostro.dev/api/tags/172700/HOT" \
  -H "Authorization: Bearer <token>"

GET /api/users/{username}
Description: Get the profile for this user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Target username. |
| nsfw | Query | string | No | true or false. |
| nsfl | Query | boolean | No | true or false. |
| exclude_mine | Query | boolean | No | Exclude private/unlisted projects. |
| include_projects | Query | boolean | No | Fetch projects with profile. |
Example Request:
curl -X GET "https://api.rostro.dev/api/users/You?nsfw=true" \
  -H "Authorization: Bearer <token>"

GET /api/leaderboard/v1
Description: Get the user leaderboard.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| order_by | Query | string | No | Field to order by (default: avg_msgs_chat). |
Example Request:
curl -X GET "https://api.rostro.dev/api/leaderboard/v1" \
  -H "Authorization: Bearer <token>"

POST /lore
Description: Make a RAG lore request.
Request Body: LoreQuery
| Field | Type | Required | Description |
|---|---|---|---|
| query | string | Yes | The search query for lore. |
| limit | integer | No | Max results. |
Example Request:
curl -X POST "https://api.rostro.dev/lore" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "query": "history of the kingdom" }'

POST /lore/item
Description: Add an unstructured lore item.
Request Body: Multipart/Form-Data
| Field | Type | Required | Description |
|---|---|---|---|
| content | file/string | Yes | The content of the lore item. |
| metadata | string | No | JSON string of metadata. |
Example Request:
curl -X POST "https://api.rostro.dev/lore/item" \
  -H "Authorization: Bearer <token>" \
  -F "content=Ancient scroll text..."

GET /lore/items
Description: Get unstructured items for owners.
Request Body: LoreFetch
| Field | Type | Required | Description |
|---|---|---|---|
| owner_ids | array | Yes | List of owner IDs to fetch lore for. |
Example Request:
curl -X GET "https://api.rostro.dev/lore/items" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "owner_ids": [123, 456] }'

DELETE /lore/{owner_id}/item/{uuid}
Description: Remove an unstructured lore item.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| uuid | Path | string | Yes | Item UUID. |
| owner_id | Path | integer | Yes | Owner ID. |
Example Request:
curl -X DELETE "https://api.rostro.dev/lore/2108776/item/1b6c5288-731c-4345-a756-1b02ee8e080f" \
  -H "Authorization: Bearer <token>"

GET /search
Description: Do Internal Search.
Parameters (Selection):
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| search | Query | string | No | Full-text search of definitions. |
| tags | Query | string | No | Comma-separated tags (e.g., 'OC,CAI'). |
| sort | Query | string | No | Sort field (default: download_count). |
| nsfw | Query | boolean | No | Include NSFW. |
| page | Query | integer | No | Page number. |
Example Request:
curl -X GET "https://api.rostro.dev/search?search=wizard&sort=download_count" \
  -H "Authorization: Bearer <token>"

POST /search
Description: Do Internal Search Bypass (Post method for same search functionality).
Parameters: Same as GET /search.
Example Request:
curl -X POST "https://api.rostro.dev/search?search=wizard" \
  -H "Authorization: Bearer <token>"

POST /minisearch
Description: A quick search just by names.
Request Body: MiniSearch
| Field | Type | Required | Description |
|---|---|---|---|
| query | string | Yes | Name to search for. |
Example Request:
curl -X POST "https://api.rostro.dev/minisearch" \
  -H "Content-Type: application/json" \
  -d '{ "query": "Gandalf" }'

POST /imagine
Description: A unified endpoint for multimedia asset generation.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| return_immediate | Query | boolean | No | Default: false. |
Request Body: GenerationRequest
| Field | Type | Required | Description |
|---|---|---|---|
| prompt | string | No | Description of what to generate. |
| generation_type | string | No | Type (text_to_image, text_to_speech, etc.). |
| width | integer | No | Canvas width. |
| height | integer | No | Canvas height. |
| model | string | No | Model to use. |
Example Request:
curl -X POST "https://api.rostro.dev/imagine" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "A futuristic city skyline",
    "generation_type": "text_to_image"
  }'

Example Response:
{
  "generation_uuid": "b9ae-6f64957f986a",
  "is_done": true,
  "primary_media_url": "https://cdn.rostro.dev/gen/image.png"
}

POST /imagine/history
Description: A unified endpoint for fetching multimedia asset generation history.
Request Body: HistoryRequest
| Field | Type | Required | Description |
|---|---|---|---|
| first | integer | No | Number of results (default: 10). |
| generated_only | boolean | No | Return only generated images. |
Example Request:
curl -X POST "https://api.rostro.dev/imagine/history" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "first": 5 }'

POST /imagine/history/delete
Description: Delete the media with these uuids.
Request Body: DeletionRequest
| Field | Type | Required | Description |
|---|---|---|---|
| uuids | array | No | List of UUID strings to delete. |
Example Request:
curl -X POST "https://api.rostro.dev/imagine/history/delete" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "uuids": ["uuid-1", "uuid-2"] }'

GET /api/project/{project_id}/ratings
Description: Get the ratings for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X GET "https://api.rostro.dev/api/project/172700/ratings" \
  -H "Authorization: Bearer <token>"

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
Description: Make or update a rating for this project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Request Body: UserRating
| Field | Type | Required | Description |
|---|---|---|---|
| rating | integer | Yes | Star rating (e.g. 1-5). |
| comment | string | No | Optional review comment. |
Example Request:
curl -X POST "https://api.rostro.dev/api/project/172700/rate" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "rating": 5, "comment": "Great!" }'

GET /api/account
Description: Get user account information.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| stripe_url | Query | boolean | No | Return stripe billing link. |
| tokens | Query | boolean | No | Return token info (default: true). |
| blocks | Query | boolean | No | Return blocked info (default: true). |
Example Request:
curl -X GET "https://api.rostro.dev/api/account" \
  -H "Authorization: Bearer <token>"

Example Response:
{
  "username": "MyUser",
  "email": "me@example.com",
  "credits": 500
}

DELETE /api/account
Description: Delete this account completely and irreversibly.
Example Request:
curl -X DELETE "https://api.rostro.dev/api/account" \
  -H "Authorization: Bearer <token>"

POST /api/account/block/{block_type}/{name}
Description: Block yourself from viewing these in search.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| block_type | Path | string | Yes | Type of block (e.g., user, tag). |
| name | Path | string | Yes | Name of the entity to block. |
Example Request:
curl -X POST "https://api.rostro.dev/api/account/block/user/BadUser" \
  -H "Authorization: Bearer <token>"

DELETE /api/account/block/{block_type}/{name}
Description: Unblock yourself from viewing these in search.
Parameters: Same as POST.
Example Request:
curl -X DELETE "https://api.rostro.dev/api/account/block/user/BadUser" \
  -H "Authorization: Bearer <token>"

POST /api/account/blacklist
Description: Prevent users from commenting specific words/phrases on your pages.
Request Body: WordBlacklist
| Field | Type | Required | Description |
|---|---|---|---|
| word | string | Yes | The word to blacklist. |
Example Request:
curl -X POST "https://api.rostro.dev/api/account/blacklist" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "word": "spam" }'

POST /api/account/blacklist/remove
Description: Remove a word from your blacklist.
Request Body: WordBlacklist
Example Request:
curl -X POST "https://api.rostro.dev/api/account/blacklist/remove" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "word": "spam" }'

POST /api/account/sort/{order}
Description: Set a default sort order in search.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| order | Path | string | Yes | Sort order enum (e.g. download_count). |
Example Request:
curl -X POST "https://api.rostro.dev/api/account/sort/download_count" \
  -H "Authorization: Bearer <token>"

GET /api/self
Description: Get truncated user account information.
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
curl -X POST "https://api.rostro.dev/follow/tag/fantasy" \
  -H "Authorization: Bearer <token>"

DELETE /follow/tag/{tagname}
Description: Unfollow a tag.
Parameters: Same as POST.
Example Request:
curl -X DELETE "https://api.rostro.dev/follow/tag/fantasy" \
  -H "Authorization: Bearer <token>"

POST /api/follow/{username}
Description: Follow a username.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
Example Request:
curl -X POST "https://api.rostro.dev/api/follow/someuser" \
  -H "Authorization: Bearer <token>"

DELETE /api/follow/{username}
Description: Unfollow a username.
Parameters: Same as POST.
Example Request:
curl -X DELETE "https://api.rostro.dev/api/follow/someuser" \
  -H "Authorization: Bearer <token>"

POST /api/follows/{username}
Description: Get who a given username follows.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| page | Query | integer | No | Page number. |
Example Request:
curl -X POST "https://api.rostro.dev/api/follows/You?page=1" \
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
curl -X GET "https://api.rostro.dev/api/followers/You?page=1" \
  -H "Authorization: Bearer <token>"

GET /api/timeline/v1
Description: Get recent updates from people you follow.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| page | Query | integer | No | Page number. |
| nsfw | Query | boolean | No | Include NSFW. |
Example Request:
curl -X GET "https://api.rostro.dev/api/timeline/v1" \
  -H "Authorization: Bearer <token>"

GET /atproto/{username}
Description: Get the configured atproto for this username for Bluesky.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
Example Request:
curl -X GET "https://api.rostro.dev/atproto/You"

POST /api/core/characters
Description: Create char.
Request Body: CharacterCreate
| Field | Type | Required | Description |
|---|---|---|---|
| name | string | Yes | Character Name. |
| description | string | Yes | Character Description. |
Example Request:
curl -X POST "https://api.rostro.dev/api/core/characters" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "name": "Hero", "description": "A brave hero." }'

POST /api/core/characters/link/{username}/{pathname}/lorebook/{project_id}
Description: Add a linked lorebook for a character.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| username | Path | string | Yes | Username. |
| pathname | Path | string | Yes | Project Slug. |
| project_id | Path | integer | Yes | Project ID of lorebook. |
Example Request:
curl -X POST "https://api.rostro.dev/api/core/characters/link/You/char-slug/lorebook/123" \
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
| pathname | Path | string | Yes | Project Slug. |
Request Body: CharacterUpdate
Example Request:
curl -X PUT "https://api.rostro.dev/api/core/characters/You/char-slug" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "description": "Updated description" }'

POST /api/self/username
Description: Attempt to change your username.
Request Body: UsernameChangeRequest
| Field | Type | Required | Description |
|---|---|---|---|
| new_username | string | Yes | Requested username. |
Example Request:
curl -X POST "https://api.rostro.dev/api/self/username" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "new_username": "CoolNewName" }'

POST /api/check/username
Description: Check if username is taken.
Request Body: UsernameChangeRequest
Example Request:
curl -X POST "https://api.rostro.dev/api/check/username" \
  -H "Content-Type: application/json" \
  -d '{ "new_username": "CheckThisName" }'

POST /config/{config_id}/{sub_id}
Description: Upsert a config.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| config_id | Path | string | Yes | Config ID. |
| sub_id | Path | string | Yes | Sub ID. |
Request Body: ConfigUpsert
Example Request:
curl -X POST "https://api.rostro.dev/config/123/main" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "key": "value" }'

DELETE /config/{config_id}/{sub_id}
Description: Delete config.
Parameters: Same as POST.
POST /config
Description: Upsert configs.
Request Body: ConfigsUpsert
DELETE /config
Description: Delete configs.
Request Body: ConfigsDelete
POST /config/fetch
Description: Fetch configs.
Request Body: ConfigFetchRequest
GET /oauth/userinfo
Description: Fetches information about the user's account (identity, scopes, credits).
Example Request:
curl -X GET "https://api.rostro.dev/oauth/userinfo" \
  -H "Authorization: Bearer <token>"

Example Response:
{
  "identity": "user-123",
  "username": "UserOne",
  "scopes": ["read", "write"],
  "credits": 100
}

POST /api/media/video/upload
Description: Upload a video or animation.
Request Body: Multipart/Form-Data
| Field | Type | Required | Description |
|---|---|---|---|
| file | file | Yes | Video file. |
Example Request:
curl -X POST "https://api.rostro.dev/api/media/video/upload" \
  -H "Authorization: Bearer <token>" \
  -F "file=@myvideo.mp4"

POST /api/favorites/{project_id}
Description: Favorite a project.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
Example Request:
curl -X POST "https://api.rostro.dev/api/favorites/172700" \
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
| no_nsfl_enum | Path | string | Yes | Boolean String. |
| no_nsfw_enum | Path | string | Yes | Boolean String. |
GET /api/favorites
Description: Get favorited projects.
Example Request:
curl -X GET "https://api.rostro.dev/api/favorites" \
  -H "Authorization: Bearer <token>"

POST /api/reports
Description: Report a project.
Request Body: ReportSubmission
| Field | Type | Required | Description |
|---|---|---|---|
| project_id | integer | Yes | Project ID. |
| reason | string | Yes | Reason for report. |
POST /api/ratings/reports
Description: Report a rating.
Request Body: ReportRatingSubmission
DELETE /api/project/{project_id}
Description: Delete a project permanently.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
DELETE /api/project/{username}/{pathname}
Description: Delete a project permanently (by path).
DELETE /api/project/{namespace}/{username}/{pathname}
Description: Delete a project permanently (full path).
GET /api/characters/{project_id}/expressions
Description: Get expression packs for the character.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| project_id | Path | integer | Yes | Project ID. |
POST /api/characters/{project_id}/expressions
Description: Upsert an expression pack for the character.
Request Body: Expressions
DELETE /api/characters/{project_id}/expressions/{tagname}
Description: Delete an expression pack for the character.
GET /api/notifications
Description: Get user account notifications.
POST /api/notifications
Description: Get user account notifications (POST variant).
Request Body: NotifsQuery
DELETE /api/notifications
Description: Dismiss all user account notifications.
DELETE /api/notifications/{notification_id}
Description: Dismiss a user account notification.
DELETE /api/notifications/announcement/{announcement_id}
Description: Dismiss an announcement for the current user.
GET /api/badges
Description: Get all badges.
GET /api/badges/{badge_id}
Description: Get a specific badge.
POST /api/core/chats
Description: Create a new chat.
Request Body: NewChatRequest
| Field | Type | Required | Description |
|---|---|---|---|
| characters | array | Yes | List of character IDs/paths. |
Example Request:
curl -X POST "https://api.rostro.dev/api/core/chats" \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{ "characters": ["You/CharName"] }'

GET /api/core/chats
Description: Search (or get all) chats for user.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| limit | Query | integer | No | Max chats. |
| search | Query | string | No | Search term. |
POST /api/core/chats/import
Description: Create a new chat from import.
Request Body: ChatImportRequest
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
Request Body: UpdateChat
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
Description: Get user account active tokens for the inference API.
POST /api/account/tokens
Description: Create a new token for this account for the inference API.
POST /account/tokens/projects
Description: Create a new token for this account for the base API for projects CRUD.
POST /api/account/tokens/core
Description: Create a new token for this account for the inference API.
DELETE /api/account/token/{token_id}
Description: Revoke a token.
POST /extensions
Description: Create extension.
POST /extension/{extension_id}/files
Description: Make a number of operations on files in a pseudo-atomic manner.
POST /minifetch/extension/{extension_id}
Description: A quick extension fetch.
POST /minifetch/extensions/{extension_id}
Description: A quick extensions fetch.
POST /extension/{extension_id}/upload
Description: Upload a zip file to extension.
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
Description: Remove the background from an image.
POST /music
Description: Create a new music piece from a prompt.
POST /tts
Description: Create an audio of the submitted transcript.
GET /voices
Description: Get my voices.
DELETE /voices/{voice_id}
Description: Delete voice.
POST /voice_clone
Description: Create or update a voice clone.
POST /images/text2img
Description: Create an image from a prompt.
POST /images/img2img
Description: Create a new image from a base one and a prompt.
POST /images/animate
Description: Create a new animation from a base image.
POST /video
Description: Create a new video from a prompt.
POST /foley
Description: Create a new sound effect from a prompt.
POST /images/upscale
Description: Upscale an image.
POST /check
Description: Check on a running task.
POST /imagine/check
Description: A unified endpoint for checking on a running generation.
POST /stt
Description: STT (Speech to text) endpoint.
POST /chub/{model}/v1/chat/completions
Description: OpenAI Mimic API endpoint for chat completions. Model selection overridden by path.
Parameters:
| Name | In | Type | Required | Description |
|---|---|---|---|---|
| model | Path | string | Yes | Inference Model. |
Request Body: CompletionCreateParams
POST /chub/{model}/v1/completions
Description: OpenAI Mimic API endpoint for completions.
POST /{model}/v1/completions
Description: OpenAI Mimic API endpoint for completions.
POST /v1/completions
Description: OpenAI Mimic API endpoint for completions.
POST /{model}/v1/chat/completions
Description: OpenAI Mimic API endpoint for chat completions.
GET /chub/{model}/v1/models
Description: Fetch the list of available models.
GET /{model}/v1/models
Description: Fetch the list of available models.
POST /v1/chat/completions
Description: OpenAI Mimic API endpoint for chat completions.
GET /v1/models
Description: Fetch the list of all available models.
POST /prompt
Description: API endpoint for generic completions.
PATCH /imagine/project/{uuid}
Description: Update an existing imagine project or image.
GET /imagine/project/{uuid}
Description: Get an existing imagine project or image.
POST /model3d
Description: Create a new 3D model from a prompt and/or image(s).
POST /images/expressions
Description: Create a sprite pack from an image or a prompt.
POST /live/voice
Description: Request live voice chat.
DELETE /live/voice/{chat_id}/{agent_id}
Description: End live voice chat.
GET /api/{namespace}/{creator_name}/{project_name}
Description: Fetch Project.
GET /api/{space}/{project_id}
Description: Fetch Character Id.
GET /api/public/{namespace}/{creator_name}/{project_name}
Description: Fetch Project (Public).
GET /api/public/{space}/{project_id}
Description: Fetch Character Id (Public).
GET /forks/project/{project_id}
Description: Get forks for this project.
POST /api/project/{project_id}/fork/v2
Description: Fork a character (V2).
POST /engine/api/apps
Description: App Create.
GET /engine/api/apps
Description: App List.
DELETE /engine/api/apps/{app_id}
Description: App Delete.
GET /engine/api/apps/{app_id}
Description: App Get.
POST /engine/api/apps/download
Description: App Download.
GET /engine/api/assets
Description: Assets List.
POST /engine/api/assets
Description: Asset Create.
DELETE /engine/api/assets
Description: Asset Delete.
GET /engine/api/assets/{asset_id}
Description: Asset Get.
PUT /engine/api/assets/{asset_id}
Description: Asset Update.
GET /engine/api/assets/{asset_id}/file/{filename}
Description: Asset Get File.
GET /engine/api/assets/{asset_id}/thumbnail/{size}
Description: Asset Get Thumbnail.
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
POST /engine/api/editor/scene/{scene_id}/opened
Description: Home Scene Opened.
POST /engine/api/editor/scene/{scene_id}/events
Description: Home Scene Event.
POST /engine/api/editor/scene/{scene_id}/tips/{tip}
Description: Home Scene Tip.
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
The API uses standard HTTP status codes.
| Code | Meaning | Description |
|---|---|---|
| 200 | OK | Successful Request. |
| 400 | Bad Request | The server could not understand the request due to invalid syntax or parameters. |
| 401 | Unauthorized | Authentication is required and has failed or has not been yet provided. |
| 403 | Forbidden | The request was valid, but the server is refusing action (e.g. insufficient permissions). |
| 404 | Not Found | The requested resource could not be found. |
| 422 | Validation Error | The request was well-formed but was unable to be followed due to semantic errors (e.g. body validation failed). |
| 500 | Internal Server Error | The server encountered an internal error and was unable to complete your request. |


# Rostro API Documentation

**Version:** 0.5.9

## Table of Contents
- [Overview](#overview)
- [Base URLs](#base-urls)
- [Authentication](#authentication)
- [Endpoints](#endpoints)
  - [Read-Only Endpoints](#read-only-endpoints)
  - [Projects](#projects)
  - [Characters](#characters)
  - [Public Logs](#public-logs)
  - [OpenAI Mimic API](#openai-mimic-api)
  - [User Account](#user-account)
  - [Chat](#chat)
  - [Imagine](#imagine)
  - [Live](#live)
  - [Personas](#personas)
  - [Lore](#lore)
  - [Unstable](#unstable)
- [Data Models](#data-models)
- [Error Handling](#error-handling)
- [Rate Limiting](#rate-limiting)

---

## Overview

The Rostro API provides comprehensive endpoints for AI character interaction, image generation, lorebooks, chat functionality, and OpenAI-compatible inference. The API supports both character-based conversations and standard LLM interactions.

**Key Features:**
- Character creation and management
- Chat and conversation handling
- Image generation and gallery management
- Lorebook and RAG (Retrieval-Augmented Generation)
- OpenAI-compatible endpoints
- Voice and live interaction support
- Public chat logs and character sharing

**Contact:** support@rostro.dev  
**Terms of Service:** https://rostro.dev/tos

---

## Base URLs

The API has two distinct base URLs depending on your use case:

1. **OpenAI Mimic API:** `https://api.rostro.dev/v1`
   - Use this for OpenAI-compatible endpoints
   - Drop-in replacement for OpenAI API clients

2. **MCP Server:** `https://proto.rostro.dev/mcp`
   - Use this for Model Context Protocol server functionality

3. **Standard API:** Base URL for all other endpoints (not explicitly specified in the spec)

---

## Authentication

The API supports three authentication methods:

### 1. API Key Authentication
**Header:** `CH-API-KEY`  
Include your API key in the request header:
```http
CH-API-KEY: your-api-key-here
```

### 2. Bearer Token Authentication
**Header:** `Authorization`  
Include a bearer token:
```http
Authorization: Bearer your-token-here
```

### 3. Samwise Authentication
**Header:** `samwise`  
Alternative authentication method for specific integrations.

---

## Endpoints

### Read-Only Endpoints
These endpoints do not require authentication and are for exploration and download of character and lorebook definitions.

#### POST /tags
Get all tags with counts, optionally by namespace.

**Request Body:**
```json
{
  "namespace": "string (optional)",
  "search": "string (optional)",
  "limit": "integer (optional)",
  "offset": "integer (optional)"
}
```

**Response:** `200 OK`
```json
{
  "tags": [
    {
      "name": "string",
      "count": "integer",
      "namespace": "string"
    }
  ]
}
```

**Error Responses:** 400, 401, 403, 404, 500

---

#### POST /character/search
Search for characters with flexible filters.

**Request Body:**
```json
{
  "search": "string (optional)",
  "tags": ["array of strings (optional)"],
  "exclude_tags": ["array of strings (optional)"],
  "nsfw": "boolean (optional)",
  "aischema": "string (optional)",
  "first": "integer (optional, default: 50)",
  "page": "integer (optional, default: 1)",
  "sort": "string (optional)",
  "min_tokens": "integer (optional)",
  "max_tokens": "integer (optional)",
  "require_images": "boolean (optional)",
  "require_custom_prompt": "boolean (optional)"
}
```

**Response:** `200 OK`
```json
{
  "nodes": [
    {
      "id": "integer",
      "name": "string",
      "description": "string",
      "nsfw": "boolean",
      "avatar_uri": "string",
      "creator": "string",
      "tags": ["array of strings"],
      "token_count": "integer",
      "created_at": "datetime",
      "updated_at": "datetime"
    }
  ],
  "count": "integer",
  "page": "integer",
  "pages": "integer"
}
```

---

#### GET /character/download
Download a character definition by ID or full ID.

**Query Parameters:**
- `id` (integer, optional): Character ID
- `fullid` (string, optional): Full character identifier
- `format` (string, optional): Export format (default: "chara")

**Response:** `200 OK`  
Returns the character definition file

---

#### POST /lorebook/search
Search for lorebooks.

**Request Body:**
```json
{
  "search": "string (optional)",
  "tags": ["array of strings (optional)"],
  "exclude_tags": ["array of strings (optional)"],
  "nsfw": "boolean (optional)",
  "first": "integer (optional, default: 50)",
  "page": "integer (optional, default: 1)",
  "sort": "string (optional)",
  "min_entries": "integer (optional)",
  "max_entries": "integer (optional)"
}
```

**Response:** Similar structure to character search

---

#### GET /lorebook/download
Download a lorebook definition.

**Query Parameters:**
- `id` (integer, required): Lorebook ID
- `format` (string, optional): Export format

---

### Projects

Project endpoints handle common functionality across different project types (characters, lorebooks, etc.).

#### PUT /api/project/{project_id}/metadata
Update the metadata for a project.

**Path Parameters:**
- `project_id` (integer, required, min: 1): The project ID (e.g., 172700)

**Request Body:**
```json
{
  "name": "string (optional)",
  "tagline": "string (optional)",
  "description": "string (optional)",
  "nsfw": "boolean (optional)",
  "tags": ["array of strings (optional)"],
  "avatar": "string (optional, base64 or URL)",
  "public": "boolean (optional)"
}
```

**Response:** `200 OK`
```json
{
  "success": true,
  "message": "string"
}
```

**Authentication:** Required (CH-API-KEY, Authorization, or samwise)

---

#### GET /api/gallery
Fetch the gallery of all images for all projects.

**Query Parameters:**
- `nsfw` (boolean, optional, default: true): Include NSFW content
- `page` (integer, optional, default: 1): Page number
- `limit` (integer, optional, default: 24): Items per page
- `count` (boolean, optional, default: true): Return total count

**Response:** `200 OK`
```json
{
  "items": [
    {
      "id": "integer",
      "project_id": "integer",
      "url": "string",
      "thumbnail_url": "string",
      "nsfw": "boolean",
      "created_at": "datetime",
      "metadata": {}
    }
  ],
  "count": "integer (optional)",
  "page": "integer",
  "pages": "integer"
}
```

---

#### GET /api/gallery/project/{project_id}
Fetch the gallery of images for a specific project.

**Path Parameters:**
- `project_id` (integer, required): Project ID (e.g., 172700)

**Query Parameters:** Same as `/api/gallery`

**Response:** Same structure as `/api/gallery`

---

#### POST /api/gallery/upload
Upload an image to the gallery.

**Request Body:**
```json
{
  "project_id": "integer (required)",
  "image": "string (required, base64)",
  "nsfw": "boolean (optional)",
  "metadata": "object (optional)"
}
```

**Response:** `200 OK`
```json
{
  "id": "integer",
  "project_id": "integer",
  "url": "string",
  "thumbnail_url": "string",
  "nsfw": "boolean",
  "created_at": "datetime"
}
```

**Authentication:** Required

---

### Characters

Character-specific endpoints for CRUD operations.

#### POST /api/character/create
Create a new character.

**Request Body:**
```json
{
  "name": "string (required)",
  "description": "string (optional)",
  "personality": "string (optional)",
  "scenario": "string (optional)",
  "first_message": "string (optional)",
  "example_dialogues": "string (optional)",
  "avatar": "string (optional, base64)",
  "nsfw": "boolean (optional)",
  "tags": ["array of strings (optional)"],
  "public": "boolean (optional)",
  "aischema": "string (optional)"
}
```

**Response:** `200 OK`
```json
{
  "id": "integer",
  "name": "string",
  "fullid": "string",
  "created_at": "datetime"
}
```

**Authentication:** Required

---

#### GET /api/character/{character_id}
Get character details.

**Path Parameters:**
- `character_id` (integer, required): Character ID

**Response:** `200 OK`
```json
{
  "id": "integer",
  "name": "string",
  "description": "string",
  "personality": "string",
  "scenario": "string",
  "first_message": "string",
  "example_dialogues": "string",
  "avatar_uri": "string",
  "nsfw": "boolean",
  "tags": ["array"],
  "public": "boolean",
  "creator": "string",
  "token_count": "integer",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

---

#### PUT /api/character/{character_id}
Update an existing character.

**Path Parameters:**
- `character_id` (integer, required): Character ID

**Request Body:** Same fields as create (all optional)

**Response:** `200 OK`

**Authentication:** Required (must be owner)

---

#### DELETE /api/character/{character_id}
Delete a character.

**Path Parameters:**
- `character_id` (integer, required): Character ID

**Response:** `200 OK`

**Authentication:** Required (must be owner)

---

### Public Logs

Endpoints for accessing and managing public chat logs.

#### POST /api/logs/search
Search public chat logs.

**Request Body:**
```json
{
  "search": "string (optional)",
  "character_id": "integer (optional)",
  "user_id": "integer (optional)",
  "tags": ["array of strings (optional)"],
  "nsfw": "boolean (optional)",
  "first": "integer (optional, default: 50)",
  "page": "integer (optional, default: 1)",
  "sort": "string (optional)"
}
```

**Response:** `200 OK`
```json
{
  "logs": [
    {
      "id": "integer",
      "character_id": "integer",
      "character_name": "string",
      "user_id": "integer",
      "username": "string",
      "title": "string",
      "nsfw": "boolean",
      "tags": ["array"],
      "message_count": "integer",
      "created_at": "datetime"
    }
  ],
  "count": "integer",
  "page": "integer",
  "pages": "integer"
}
```

---

#### GET /api/logs/{log_id}
Get a specific chat log.

**Path Parameters:**
- `log_id` (integer, required): Log ID

**Response:** `200 OK`
```json
{
  "id": "integer",
  "character_id": "integer",
  "messages": [
    {
      "role": "string",
      "content": "string",
      "timestamp": "datetime"
    }
  ],
  "metadata": {}
}
```

---

### OpenAI Mimic API

OpenAI-compatible endpoints for drop-in replacement functionality.

**Base URL:** `https://api.rostro.dev/v1`

---

#### POST /v1/chat/completions
Create a chat completion (non-streaming).

**Request Body:**
```json
{
  "model": "string (required)",
  "messages": [
    {
      "role": "string (required)",
      "content": "string (required)",
      "name": "string (optional)"
    }
  ],
  "temperature": "number (optional, 0-2)",
  "top_p": "number (optional, 0-1)",
  "n": "integer (optional, default: 1)",
  "stream": false,
  "stop": "string or array (optional)",
  "max_tokens": "integer (optional)",
  "presence_penalty": "number (optional, -2 to 2)",
  "frequency_penalty": "number (optional, -2 to 2)",
  "logit_bias": "object (optional)",
  "user": "string (optional)",
  "functions": "array (optional)",
  "function_call": "string or object (optional)",
  "tools": "array (optional)",
  "tool_choice": "string or object (optional)",
  "response_format": "object (optional)",
  "seed": "integer (optional)",
  "web_search_options": "object (optional)"
}
```

**Response:** `200 OK`
```json
{
  "id": "string",
  "object": "chat.completion",
  "created": "integer (unix timestamp)",
  "model": "string",
  "choices": [
    {
      "index": "integer",
      "message": {
        "role": "string",
        "content": "string",
        "function_call": "object (optional)",
        "tool_calls": "array (optional)"
      },
      "finish_reason": "string"
    }
  ],
  "usage": {
    "prompt_tokens": "integer",
    "completion_tokens": "integer",
    "total_tokens": "integer"
  }
}
```

---

#### POST /v1/chat/completions (streaming)
Create a chat completion with streaming.

**Request Body:** Same as non-streaming, but with `"stream": true`

**Response:** Server-Sent Events (SSE)
```
data: {"id":"...","object":"chat.completion.chunk","created":...,"model":"...","choices":[{"index":0,"delta":{"role":"assistant","content":"Hello"},"finish_reason":null}]}

data: {"id":"...","object":"chat.completion.chunk","created":...,"model":"...","choices":[{"index":0,"delta":{"content":" there"},"finish_reason":null}]}

data: [DONE]
```

---

#### POST /v1/completions
Create a text completion (non-streaming).

**Request Body:**
```json
{
  "model": "string (required)",
  "prompt": "string or array (required)",
  "max_tokens": "integer (optional)",
  "temperature": "number (optional, 0-2)",
  "top_p": "number (optional, 0-1)",
  "n": "integer (optional, default: 1)",
  "stream": false,
  "logprobs": "integer (optional)",
  "echo": "boolean (optional)",
  "stop": "string or array (optional)",
  "presence_penalty": "number (optional)",
  "frequency_penalty": "number (optional)",
  "best_of": "integer (optional)",
  "logit_bias": "object (optional)",
  "user": "string (optional)",
  "suffix": "string (optional)",
  "seed": "integer (optional)"
}
```

**Response:** `200 OK`
```json
{
  "id": "string",
  "object": "text_completion",
  "created": "integer",
  "model": "string",
  "choices": [
    {
      "text": "string",
      "index": "integer",
      "logprobs": "object (optional)",
      "finish_reason": "string"
    }
  ],
  "usage": {
    "prompt_tokens": "integer",
    "completion_tokens": "integer",
    "total_tokens": "integer"
  }
}
```

---

#### GET /v1/models
List available models.

**Response:** `200 OK`
```json
{
  "object": "list",
  "data": [
    {
      "id": "string",
      "object": "model",
      "created": "integer",
      "owned_by": "string"
    }
  ]
}
```

---

#### POST /v1/embeddings
Create embeddings for text.

**Request Body:**
```json
{
  "input": "string or array (required)",
  "model": "string (required)",
  "encoding_format": "string (optional, 'float' or 'base64')",
  "dimensions": "integer (optional)",
  "user": "string (optional)"
}
```

**Response:** `200 OK`
```json
{
  "object": "list",
  "data": [
    {
      "object": "embedding",
      "embedding": "array of floats",
      "index": "integer"
    }
  ],
  "model": "string",
  "usage": {
    "prompt_tokens": "integer",
    "total_tokens": "integer"
  }
}
```

---

### User Account

Endpoints for managing user account information.

#### GET /api/user/me
Get current user information.

**Response:** `200 OK`
```json
{
  "id": "integer",
  "username": "string",
  "email": "string",
  "created_at": "datetime",
  "avatar_uri": "string",
  "bio": "string",
  "preferences": {}
}
```

**Authentication:** Required

---

#### PUT /api/user/me
Update user profile.

**Request Body:**
```json
{
  "username": "string (optional)",
  "email": "string (optional)",
  "avatar": "string (optional, base64)",
  "bio": "string (optional)",
  "preferences": "object (optional)"
}
```

**Response:** `200 OK`

**Authentication:** Required

---

### Chat

Endpoints for managing chat sessions and messages.

#### POST /api/chat/session
Create a new chat session.

**Request Body:**
```json
{
  "character_id": "integer (required)",
  "persona_id": "integer (optional)",
  "lorebook_ids": ["array of integers (optional)"],
  "scenario": "string (optional)",
  "custom_prompt": "string (optional)"
}
```

**Response:** `200 OK`
```json
{
  "session_id": "string",
  "character_id": "integer",
  "created_at": "datetime"
}
```

**Authentication:** Required

---

#### POST /api/chat/session/{session_id}/message
Send a message in a chat session.

**Path Parameters:**
- `session_id` (string, required): Chat session ID

**Request Body:**
```json
{
  "content": "string (required)",
  "role": "string (optional, default: 'user')",
  "generate_response": "boolean (optional, default: true)"
}
```

**Response:** `200 OK`
```json
{
  "message_id": "string",
  "content": "string",
  "role": "string",
  "timestamp": "datetime",
  "response": {
    "message_id": "string",
    "content": "string",
    "role": "assistant",
    "timestamp": "datetime"
  }
}
```

---

#### GET /api/chat/session/{session_id}/messages
Get all messages in a chat session.

**Path Parameters:**
- `session_id` (string, required): Chat session ID

**Query Parameters:**
- `limit` (integer, optional, default: 100): Maximum messages to return
- `before` (string, optional): Message ID to fetch before
- `after` (string, optional): Message ID to fetch after

**Response:** `200 OK`
```json
{
  "messages": [
    {
      "message_id": "string",
      "content": "string",
      "role": "string",
      "timestamp": "datetime"
    }
  ]
}
```

---

#### DELETE /api/chat/session/{session_id}
Delete a chat session.

**Path Parameters:**
- `session_id` (string, required): Chat session ID

**Response:** `200 OK`

**Authentication:** Required

---

### Imagine

Endpoints for audiovisual generation (images, audio, video).

#### POST /api/imagine/image
Generate an image.

**Request Body:**
```json
{
  "prompt": "string (required)",
  "negative_prompt": "string (optional)",
  "model": "string (optional)",
  "width": "integer (optional, default: 512)",
  "height": "integer (optional, default: 512)",
  "steps": "integer (optional, default: 30)",
  "guidance_scale": "number (optional, default: 7.5)",
  "seed": "integer (optional)",
  "num_images": "integer (optional, default: 1)",
  "nsfw": "boolean (optional)"
}
```

**Response:** `200 OK`
```json
{
  "images": [
    {
      "url": "string",
      "seed": "integer",
      "prompt": "string"
    }
  ]
}
```

**Authentication:** Required

---

#### POST /api/imagine/audio
Generate audio (text-to-speech, music, etc.).

**Request Body:**
```json
{
  "prompt": "string (required)",
  "type": "string (required, e.g., 'tts', 'music')",
  "voice": "string (optional)",
  "duration": "number (optional)",
  "model": "string (optional)"
}
```

**Response:** `200 OK`
```json
{
  "url": "string",
  "duration": "number",
  "type": "string"
}
```

**Authentication:** Required

---

### Live

Endpoints for multi-user and live voice interactions.

#### POST /api/live/room
Create a live room.

**Request Body:**
```json
{
  "name": "string (required)",
  "character_ids": ["array of integers (optional)"],
  "max_participants": "integer (optional)",
  "public": "boolean (optional)",
  "voice_enabled": "boolean (optional)"
}
```

**Response:** `200 OK`
```json
{
  "room_id": "string",
  "name": "string",
  "join_url": "string",
  "created_at": "datetime"
}
```

**Authentication:** Required

---

#### GET /api/live/room/{room_id}
Get live room details.

**Path Parameters:**
- `room_id` (string, required): Room ID

**Response:** `200 OK`
```json
{
  "room_id": "string",
  "name": "string",
  "participants": ["array of user objects"],
  "characters": ["array of character objects"],
  "created_at": "datetime"
}
```

---

### Personas

CRUD operations for user personas.

#### POST /api/persona
Create a persona.

**Request Body:**
```json
{
  "name": "string (required)",
  "description": "string (optional)",
  "avatar": "string (optional, base64)",
  "attributes": "object (optional)"
}
```

**Response:** `200 OK`
```json
{
  "id": "integer",
  "name": "string",
  "created_at": "datetime"
}
```

**Authentication:** Required

---

#### GET /api/persona
List all user personas.

**Response:** `200 OK`
```json
{
  "personas": [
    {
      "id": "integer",
      "name": "string",
      "description": "string",
      "avatar_uri": "string"
    }
  ]
}
```

---

#### GET /api/persona/{persona_id}
Get a specific persona.

**Path Parameters:**
- `persona_id` (integer, required): Persona ID

**Response:** `200 OK`

---

#### PUT /api/persona/{persona_id}
Update a persona.

**Path Parameters:**
- `persona_id` (integer, required): Persona ID

**Request Body:** Same fields as create (all optional)

**Response:** `200 OK`

**Authentication:** Required

---

#### DELETE /api/persona/{persona_id}
Delete a persona.

**Path Parameters:**
- `persona_id` (integer, required): Persona ID

**Response:** `200 OK`

**Authentication:** Required

---

### Lore

Endpoints for RAG (Retrieval-Augmented Generation) and lorebooks.

#### POST /api/lorebook
Create a lorebook.

**Request Body:**
```json
{
  "name": "string (required)",
  "description": "string (optional)",
  "entries": [
    {
      "key": "array of strings (required)",
      "content": "string (required)",
      "enabled": "boolean (optional, default: true)",
      "insertion_order": "integer (optional)",
      "case_sensitive": "boolean (optional)"
    }
  ],
  "public": "boolean (optional)",
  "nsfw": "boolean (optional)",
  "tags": ["array of strings (optional)"]
}
```

**Response:** `200 OK`
```json
{
  "id": "integer",
  "name": "string",
  "entry_count": "integer",
  "created_at": "datetime"
}
```

**Authentication:** Required

---

#### GET /api/lorebook/{lorebook_id}
Get lorebook details.

**Path Parameters:**
- `lorebook_id` (integer, required): Lorebook ID

**Response:** `200 OK`
```json
{
  "id": "integer",
  "name": "string",
  "description": "string",
  "entries": ["array of entry objects"],
  "public": "boolean",
  "nsfw": "boolean",
  "tags": ["array"],
  "creator": "string",
  "created_at": "datetime"
}
```

---

#### PUT /api/lorebook/{lorebook_id}
Update a lorebook.

**Path Parameters:**
- `lorebook_id` (integer, required): Lorebook ID

**Request Body:** Same fields as create (all optional)

**Response:** `200 OK`

**Authentication:** Required

---

#### DELETE /api/lorebook/{lorebook_id}
Delete a lorebook.

**Path Parameters:**
- `lorebook_id` (integer, required): Lorebook ID

**Response:** `200 OK`

**Authentication:** Required

---

### Unstable

**Warning:** These endpoints are under active development and may change without notice. Best not to rely on these in production.

#### POST /api/infer/emotion
Infer the emotion of a string.

**Request Body:**
```json
{
  "text": "string (required)"
}
```

**Response:** `200 OK`
```json
{
  "emotions": [
    {
      "label": "string",
      "score": "number"
    }
  ]
}
```

---

## Data Models

### Character Schema
```json
{
  "id": "integer",
  "name": "string",
  "description": "string",
  "personality": "string",
  "scenario": "string",
  "first_message": "string",
  "example_dialogues": "string",
  "avatar_uri": "string",
  "nsfw": "boolean",
  "tags": ["array of strings"],
  "public": "boolean",
  "creator": "string",
  "token_count": "integer",
  "aischema": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

### Lorebook Schema
```json
{
  "id": "integer",
  "name": "string",
  "description": "string",
  "entries": [
    {
      "key": ["array of strings"],
      "content": "string",
      "enabled": "boolean",
      "insertion_order": "integer",
      "case_sensitive": "boolean"
    }
  ],
  "public": "boolean",
  "nsfw": "boolean",
  "tags": ["array of strings"],
  "creator": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

### Chat Message Schema
```json
{
  "message_id": "string",
  "session_id": "string",
  "role": "string (user|assistant|system)",
  "content": "string",
  "timestamp": "datetime",
  "metadata": "object (optional)"
}
```

### Gallery Item Schema
```json
{
  "id": "integer",
  "project_id": "integer",
  "url": "string",
  "thumbnail_url": "string",
  "nsfw": "boolean",
  "created_at": "datetime",
  "metadata": "object"
}
```

---

## Error Handling

The API uses standard HTTP status codes and returns error responses in the following format:

### User Error (4xx)
```json
{
  "error": {
    "type": "user_error",
    "message": "string",
    "code": "string (optional)",
    "param": "string (optional)"
  }
}
```

### API Error (5xx)
```json
{
  "error": {
    "type": "api_error",
    "message": "string",
    "code": "string (optional)"
  }
}
```

### Validation Error (422)
```json
{
  "detail": [
    {
      "loc": ["array"],
      "msg": "string",
      "type": "string"
    }
  ]
}
```

### Common Status Codes

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Bad Request - Invalid parameters |
| 401 | Unauthorized - Missing or invalid authentication |
| 403 | Forbidden - Insufficient permissions |
| 404 | Not Found - Resource doesn't exist |
| 422 | Validation Error - Request validation failed |
| 429 | Too Many Requests - Rate limit exceeded |
| 500 | Internal Server Error |

---

## Rate Limiting

Rate limits are enforced per API key. When you exceed the rate limit, you'll receive a `429 Too Many Requests` response with the following headers:

- `X-RateLimit-Limit`: Maximum requests per time window
- `X-RateLimit-Remaining`: Remaining requests in current window
- `X-RateLimit-Reset`: Unix timestamp when the limit resets

**Best Practices:**
- Implement exponential backoff for retries
- Cache responses when possible
- Use streaming for long-running requests
- Monitor rate limit headers

---

## OpenAI Compatibility

The Rostro API provides OpenAI-compatible endpoints at `https://api.rostro.dev/v1`. You can use existing OpenAI client libraries by simply changing the base URL.

### Python Example
```python
from openai import OpenAI

client = OpenAI(
    api_key="your-rostro-api-key",
    base_url="https://api.rostro.dev/v1"
)

response = client.chat.completions.create(
    model="model-name",
    messages=[
        {"role": "user", "content": "Hello!"}
    ]
)
```

### JavaScript Example
```javascript
import OpenAI from 'openai';

const client = new OpenAI({
  apiKey: 'your-rostro-api-key',
  baseURL: 'https://api.rostro.dev/v1',
});

const response = await client.chat.completions.create({
  model: 'model-name',
  messages: [
    { role: 'user', content: 'Hello!' }
  ],
});
```

### cURL Example
```bash
curl https://api.rostro.dev/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer your-rostro-api-key" \
  -d '{
    "model": "model-name",
    "messages": [
      {"role": "user", "content": "Hello!"}
    ]
  }'
```

---

## Advanced Features

### Web Search Integration
Some chat completion endpoints support web search:

```json
{
  "model": "model-name",
  "messages": [...],
  "web_search_options": {
    "enabled": true,
    "max_results": 5,
    "include_domains": ["example.com"],
    "exclude_domains": ["spam.com"]
  }
}
```

### Function Calling
The API supports OpenAI-style function calling:

```json
{
  "model": "model-name",
  "messages": [...],
  "functions": [
    {
      "name": "get_weather",
      "description": "Get the weather in a location",
      "parameters": {
        "type": "object",
        "properties": {
          "location": {
            "type": "string",
            "description": "The city and state"
          }
        },
        "required": ["location"]
      }
    }
  ],
  "function_call": "auto"
}
```

### Structured Output
Request JSON responses with specific schemas:

```json
{
  "model": "model-name",
  "messages": [...],
  "response_format": {
    "type": "json_schema",
    "json_schema": {
      "name": "response",
      "schema": {
        "type": "object",
        "properties": {
          "answer": {"type": "string"},
          "confidence": {"type": "number"}
        }
      }
    }
  }
}
```

---

## Pagination

Endpoints that return lists support pagination:

**Query Parameters:**
- `page`: Page number (1-indexed)
- `limit` or `first`: Items per page
- `offset`: Number of items to skip

**Response:**
```json
{
  "items": [...],
  "page": 1,
  "pages": 10,
  "count": 237,
  "limit": 24
}
```

---

## NSFW Content

Many endpoints have NSFW filtering:

- `nsfw=true`: Include NSFW content (default for authenticated users)
- `nsfw=false`: Exclude NSFW content

Projects can be marked as NSFW when created or updated.

---

## Best Practices

1. **Authentication**: Always store API keys securely and never commit them to version control
2. **Error Handling**: Implement proper error handling for all status codes
3. **Rate Limiting**: Monitor rate limit headers and implement backoff strategies
4. **Streaming**: Use streaming for long responses to improve user experience
5. **Caching**: Cache character and lorebook data when appropriate
6. **Validation**: Validate inputs before sending to reduce API calls
7. **Versioning**: Be aware of API version changes and update accordingly

---

## Support

For issues, questions, or feature requests:

- **Email**: support@rostro.dev
- **Documentation**: Check the OpenAPI specification for detailed schemas
- **Terms of Service**: https://rostro.dev/tos

---

## Changelog

### Version 0.5.9
- Current stable version
- Full OpenAI compatibility
- Enhanced character and lorebook features
- Image generation and gallery support
- Live voice and multi-user rooms
- RAG and lorebook integration

---

## License

Refer to the Terms of Service at https://rostro.dev/tos for usage terms and conditions.

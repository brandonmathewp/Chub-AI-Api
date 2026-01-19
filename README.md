# Rostro API Documentation

**Version:** 0.5.9  
**Base URL:** 
- OpenAI Mimic: `https://api.rostro.dev/v1`
- MCP Server: `https://proto.rostro.dev/mcp`

**Contact:** support@rostro.dev  
**Terms of Service:** https://rostro.dev/tos

## Table of Contents

- [Authentication](#authentication)
- [Imagine Endpoints](#imagine-endpoints)
  - [POST /imagine - Generate Multimedia Assets](#post-imagine)
  - [POST /imagine/history - Fetch Generation History](#post-imaginehistory)
- [OpenAI Compatible Endpoints](#openai-compatible-endpoints)
  - [POST /v1/chat/completions - Chat Completions](#post-v1chatcompletions)
  - [POST /v1/completions - Text Completions](#post-v1completions)
  - [POST /v1/images/generations - Image Generation](#post-v1imagesgenerations)
  - [POST /v1/images/edits - Image Editing](#post-v1imagesedits)
  - [POST /v1/audio/transcriptions - Audio Transcription](#post-v1audiotranscriptions)
  - [POST /v1/audio/translations - Audio Translation](#post-v1audiotranslations)
  - [POST /v1/audio/speech - Text-to-Speech](#post-v1audiospeech)
  - [GET /v1/models - List Models](#get-v1models)
- [Account Management Endpoints](#account-management-endpoints)
  - [GET /account - Get Account Information](#get-account)
  - [GET /account/keys - List API Keys](#get-accountkeys)
  - [POST /account/keys - Create API Key](#post-accountkeys)
- [Schemas](#schemas)

---

## Authentication

All endpoints require authentication via the `Authorization` header using an API key:

```
Authorization: Bearer YOUR_API_KEY
```

---

## Imagine Endpoints

### POST /imagine

**Summary:** Generate Multimedia Assets

**Description:** A unified endpoint for multimedia asset generation including images, videos, audio, 3D models, and other creative assets.

**Operation ID:** `imagine`

**Tags:** `Imagine`

**Security:** Requires Authorization

#### Query Parameters

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `return_immediate` | boolean | No | false | Whether to return immediately without waiting for generation to complete |

#### Request Body

**Content Type:** `application/json`

**Schema:** `GenerationRequest`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `prompt` | string or object | Yes | The prompt describing what to generate |
| `model` | string | No | The model to use for generation |
| `negative_prompt` | string | No | What to avoid in the generation |
| `width` | integer | No | Width of the generated asset |
| `height` | integer | No | Height of the generated asset |
| `num_outputs` | integer | No | Number of outputs to generate |
| `seed` | integer | No | Random seed for reproducibility |
| `guidance_scale` | number | No | How closely to follow the prompt |
| `num_inference_steps` | integer | No | Number of denoising steps |
| `scheduler` | string | No | The scheduler algorithm to use |
| `output_format` | string | No | Format of the output (e.g., "png", "jpg", "mp4") |
| `output_quality` | integer | No | Quality of the output (0-100) |

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `ImaginedItem`

| Field | Type | Description |
|-------|------|-------------|
| `generation_uuid` | string or null | Unique identifier for this generation |
| `cost` | number or null | Cost in credits for this generation |
| `primary_media_url` | string or null | URL where the generated media is located (max 1500 chars) |
| `description` | string or null | Generated description of the item |
| `prompt` | object or null | Prompt metadata used for generation |
| `is_done` | boolean | Whether generation is completed (default: true) |
| `is_failed` | boolean | Whether generation failed (default: false) |
| `uuid` | string or null | Unique identifier of the media |
| `info` | LayerInfo or null | Layer information if part of a project |
| `user_id` | integer or null | User ID associated with this generation |
| `secondary_media_urls` | object or null | Additional asset URLs (e.g., textures for 3D models) |
| `error` | Rejection or null | Error information if generation failed |
| `note` | string or null | Additional notes, typically for LLM |

#### LayerInfo Object

| Field | Type | Description |
|-------|------|-------------|
| `width` | integer or null | Canvas width |
| `height` | integer or null | Canvas height |
| `dpi` | integer or null | Canvas DPI |
| `z_index` | integer or null | Layer z-index |
| `opacity` | integer | Layer opacity (default: 100) |
| `duration` | number or null | Total duration for animations/tracks |
| `visible` | boolean | Layer visibility (default: true) |
| `locked` | boolean | Layer locked state (default: false) |
| `start_time` | number or null | Start time for animations/tracks |
| `end_time` | number or null | End time for animations/tracks |
| `in_point` | number or null | In point for animations/tracks |
| `out_point` | number or null | Out point for animations/tracks |
| `effects` | object or null | Layer effects |
| `children` | array or null | Child layers |

#### Rejection Object

| Field | Type | Description |
|-------|------|-------------|
| `reason` | RejectionReason | Reason for rejection (default: "unknown") |
| `location` | string or null | Location of the rejection |

**RejectionReason Enum:** `unknown`, `explicit_text`, `explicit_image`, `malformed_image`, `out_of_credits`

#### Error Responses

**400 Bad Request** - Invalid request parameters
**422 Unprocessable Entity** - Validation error

#### Example Request

```json
{
  "prompt": "A serene mountain landscape at sunset",
  "model": "stable-diffusion-xl",
  "width": 1024,
  "height": 768,
  "num_outputs": 1,
  "guidance_scale": 7.5
}
```

---

### POST /imagine/history

**Summary:** Fetch Generation History

**Description:** Retrieve the history of multimedia asset generations for the authenticated user.

**Operation ID:** `history`

**Tags:** `Imagine`

**Security:** Requires Authorization

**Read-Only:** true  
**Idempotent:** true  
**Destructive:** false

#### Request Body

**Content Type:** `application/json`

**Schema:** `HistoryRequest`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `limit` | integer | No | Maximum number of items to return |
| `offset` | integer | No | Number of items to skip |
| `start_date` | string | No | Start date filter (ISO 8601 format) |
| `end_date` | string | No | End date filter (ISO 8601 format) |
| `status` | string | No | Filter by status (e.g., "completed", "failed") |

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `ImaginedItems` (array of `ImaginedItem`)

Returns an array of `ImaginedItem` objects (see schema above in `/imagine` endpoint).

#### Error Responses

**422 Unprocessable Entity** - Validation error

#### Example Request

```json
{
  "limit": 50,
  "offset": 0,
  "status": "completed"
}
```

---

## OpenAI Compatible Endpoints

### POST /v1/chat/completions

**Summary:** Create Chat Completion

**Description:** Creates a model response for the given chat conversation. OpenAI-compatible endpoint.

**Operation ID:** `create_chat_completion`

**Tags:** `Mimic`

**Security:** Requires Authorization

#### Request Body

**Content Type:** `application/json`

**Schema:** `CompletionCreateParams`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `messages` | array | Yes | Array of message objects with role and content |
| `model` | string | Yes | ID of the model to use |
| `stream` | boolean | No | Whether to stream responses |
| `temperature` | number | No | Sampling temperature (0-2) |
| `top_p` | number | No | Nucleus sampling parameter |
| `max_tokens` | integer | No | Maximum tokens to generate |
| `frequency_penalty` | number | No | Penalty for token frequency (-2.0 to 2.0) |
| `presence_penalty` | number | No | Penalty for token presence (-2.0 to 2.0) |
| `n` | integer | No | Number of completions to generate |
| `stop` | string or array | No | Stop sequences |
| `tools` | array | No | List of tools the model can call |
| `tool_choice` | string or object | No | Controls tool usage ("none", "auto", "required") |
| `response_format` | object | No | Format of the response (text, JSON) |
| `seed` | integer | No | Random seed for reproducibility |
| `logprobs` | boolean | No | Whether to return log probabilities |
| `top_logprobs` | integer | No | Number of top log probs to return |
| `user` | string | No | Unique identifier for the end-user |
| `parallel_tool_calls` | boolean | No | Whether tools can be called in parallel |
| `reasoning_effort` | string | No | Effort level: "minimal", "low", "medium", "high" |
| `service_tier` | string | No | Service tier: "auto", "default", "flex", "scale", "priority" |
| `web_search_options` | object | No | Options for web search integration |

#### Message Object

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `role` | string | Yes | Role of the message author ("system", "user", "assistant", "tool") |
| `content` | string or array | Yes | Content of the message |
| `name` | string | No | Name of the author |
| `tool_calls` | array | No | Tool calls made by the assistant |
| `tool_call_id` | string | No | ID of the tool call (for tool role) |

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `ChatCompletion` or `ChatCompletionChunk` (if streaming)

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier for the completion |
| `object` | string | Object type ("chat.completion") |
| `created` | integer | Unix timestamp of creation |
| `model` | string | Model used for completion |
| `choices` | array | Array of completion choices |
| `usage` | object | Token usage information |
| `system_fingerprint` | string | System fingerprint |

#### Choice Object

| Field | Type | Description |
|-------|------|-------------|
| `index` | integer | Index of the choice |
| `message` | object | Message object with role and content |
| `finish_reason` | string | Reason for stopping ("stop", "length", "tool_calls") |
| `logprobs` | object or null | Log probabilities if requested |

#### Usage Object

| Field | Type | Description |
|-------|------|-------------|
| `prompt_tokens` | integer | Number of tokens in the prompt |
| `completion_tokens` | integer | Number of tokens in the completion |
| `total_tokens` | integer | Total tokens used |

#### Error Responses

**400 Bad Request** - Invalid request parameters  
**422 Unprocessable Entity** - Validation error

#### Example Request

```json
{
  "model": "gpt-4",
  "messages": [
    {
      "role": "system",
      "content": "You are a helpful assistant."
    },
    {
      "role": "user",
      "content": "What is the capital of France?"
    }
  ],
  "temperature": 0.7,
  "max_tokens": 150
}
```

---

### POST /v1/completions

**Summary:** Create Text Completion

**Description:** Creates a completion for the provided prompt. OpenAI-compatible legacy endpoint.

**Operation ID:** `create_completion`

**Tags:** `Mimic`

**Security:** Requires Authorization

#### Request Body

**Content Type:** `application/json`

**Schema:** `CompletionCreateParams`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `model` | string | Yes | Model to use ("gpt-3.5-turbo-instruct", "davinci-002", "babbage-002") |
| `prompt` | string or array | Yes | Prompt(s) to generate completions for |
| `stream` | boolean | No | Whether to stream responses |
| `temperature` | number | No | Sampling temperature (0-2) |
| `top_p` | number | No | Nucleus sampling parameter |
| `max_tokens` | integer | No | Maximum tokens to generate |
| `frequency_penalty` | number | No | Penalty for token frequency (-2.0 to 2.0) |
| `presence_penalty` | number | No | Penalty for token presence (-2.0 to 2.0) |
| `n` | integer | No | Number of completions to generate |
| `stop` | string or array | No | Stop sequences |
| `logprobs` | integer | No | Number of log probabilities to return |
| `echo` | boolean | No | Echo back the prompt in addition to completion |
| `best_of` | integer | No | Generate multiple completions and return best |
| `logit_bias` | object | No | Modify likelihood of specified tokens |
| `suffix` | string | No | Suffix to append after completion |
| `seed` | integer | No | Random seed for reproducibility |
| `user` | string | No | Unique identifier for the end-user |

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `Completion` or `CompletionChunk` (if streaming)

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier for the completion |
| `object` | string | Object type ("text_completion") |
| `created` | integer | Unix timestamp of creation |
| `model` | string | Model used |
| `choices` | array | Array of completion choices |
| `usage` | object | Token usage information |

#### Choice Object

| Field | Type | Description |
|-------|------|-------------|
| `index` | integer | Index of the choice |
| `text` | string | Generated text |
| `finish_reason` | string | Reason for stopping ("stop", "length") |
| `logprobs` | object or null | Log probabilities if requested |

#### Error Responses

**400 Bad Request** - Invalid request parameters  
**422 Unprocessable Entity** - Validation error

#### Example Request

```json
{
  "model": "gpt-3.5-turbo-instruct",
  "prompt": "Once upon a time",
  "max_tokens": 50,
  "temperature": 0.8
}
```

---

### POST /v1/images/generations

**Summary:** Generate Images

**Description:** Creates an image given a prompt. OpenAI-compatible endpoint.

**Operation ID:** `create_image`

**Tags:** `Mimic`

**Security:** Requires Authorization

#### Request Body

**Content Type:** `application/json`

**Schema:** `ImageGenerateParams`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `prompt` | string | Yes | Text description of the desired image(s) |
| `model` | string | No | Model to use for image generation |
| `n` | integer | No | Number of images to generate (1-10) |
| `size` | string | No | Size of images ("256x256", "512x512", "1024x1024", "1792x1024", "1024x1792") |
| `quality` | string | No | Quality of the image ("standard", "hd") |
| `response_format` | string | No | Format of response ("url", "b64_json") |
| `style` | string | No | Style of the image ("vivid", "natural") |
| `user` | string | No | Unique identifier for the end-user |

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `ImagesResponse`

| Field | Type | Description |
|-------|------|-------------|
| `created` | integer | Unix timestamp of creation |
| `data` | array | Array of image objects |

#### Image Object

| Field | Type | Description |
|-------|------|-------------|
| `url` | string | URL of the generated image (if response_format is "url") |
| `b64_json` | string | Base64 encoded image (if response_format is "b64_json") |
| `revised_prompt` | string | Revised prompt used for generation |

#### Error Responses

**400 Bad Request** - Invalid request parameters  
**422 Unprocessable Entity** - Validation error

#### Example Request

```json
{
  "prompt": "A white siamese cat",
  "n": 1,
  "size": "1024x1024",
  "quality": "hd",
  "style": "vivid"
}
```

---

### POST /v1/images/edits

**Summary:** Edit Images

**Description:** Creates an edited or extended image given an original image and a prompt. OpenAI-compatible endpoint.

**Operation ID:** `create_image_edit`

**Tags:** `Mimic`

**Security:** Requires Authorization

#### Request Body

**Content Type:** `multipart/form-data`

**Schema:** `ImageEditParams`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `image` | file | Yes | Image to edit (PNG, must be square, <4MB) |
| `prompt` | string | Yes | Text description of desired image |
| `mask` | file | No | Additional image for masking (PNG, same dimensions as image) |
| `model` | string | No | Model to use for image editing |
| `n` | integer | No | Number of images to generate (1-10) |
| `size` | string | No | Size of generated images |
| `response_format` | string | No | Format of response ("url", "b64_json") |
| `user` | string | No | Unique identifier for the end-user |

#### Response

Same as `/v1/images/generations` endpoint.

#### Error Responses

**400 Bad Request** - Invalid request parameters  
**422 Unprocessable Entity** - Validation error

---

### POST /v1/audio/transcriptions

**Summary:** Transcribe Audio

**Description:** Transcribes audio into the input language. OpenAI-compatible endpoint.

**Operation ID:** `create_transcription`

**Tags:** `Mimic`

**Security:** Requires Authorization

#### Request Body

**Content Type:** `multipart/form-data`

**Schema:** `AudioTranscriptionParams`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `file` | file | Yes | Audio file to transcribe (mp3, mp4, mpeg, mpga, m4a, wav, webm, <25MB) |
| `model` | string | Yes | Model to use (e.g., "whisper-1") |
| `language` | string | No | Language of the input audio (ISO-639-1 format) |
| `prompt` | string | No | Optional text to guide the model's style |
| `response_format` | string | No | Format of response ("json", "text", "srt", "verbose_json", "vtt") |
| `temperature` | number | No | Sampling temperature (0-1) |
| `timestamp_granularities` | array | No | Timestamp granularities ("word", "segment") |

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `Transcription`

| Field | Type | Description |
|-------|------|-------------|
| `text` | string | Transcribed text |
| `language` | string | Detected language (if not specified) |
| `duration` | number | Duration of audio in seconds |
| `words` | array | Word-level timestamps (if requested) |
| `segments` | array | Segment-level timestamps (if requested) |

#### Error Responses

**400 Bad Request** - Invalid request parameters  
**422 Unprocessable Entity** - Validation error

#### Example Usage

```bash
curl -X POST https://api.rostro.dev/v1/audio/transcriptions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -F "file=@audio.mp3" \
  -F "model=whisper-1" \
  -F "language=en"
```

---

### POST /v1/audio/translations

**Summary:** Translate Audio

**Description:** Translates audio into English. OpenAI-compatible endpoint.

**Operation ID:** `create_translation`

**Tags:** `Mimic`

**Security:** Requires Authorization

#### Request Body

**Content Type:** `multipart/form-data`

**Schema:** `AudioTranslationParams`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `file` | file | Yes | Audio file to translate (mp3, mp4, mpeg, mpga, m4a, wav, webm, <25MB) |
| `model` | string | Yes | Model to use (e.g., "whisper-1") |
| `prompt` | string | No | Optional text to guide the model's style |
| `response_format` | string | No | Format of response ("json", "text", "srt", "verbose_json", "vtt") |
| `temperature` | number | No | Sampling temperature (0-1) |

#### Response

Same as `/v1/audio/transcriptions` endpoint, but text is translated to English.

#### Error Responses

**400 Bad Request** - Invalid request parameters  
**422 Unprocessable Entity** - Validation error

---

### POST /v1/audio/speech

**Summary:** Text-to-Speech

**Description:** Generates audio from the input text. OpenAI-compatible endpoint.

**Operation ID:** `create_speech`

**Tags:** `Mimic`

**Security:** Requires Authorization

#### Request Body

**Content Type:** `application/json`

**Schema:** `SpeechCreateParams`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `model` | string | Yes | Model to use (e.g., "tts-1", "tts-1-hd") |
| `input` | string | Yes | Text to generate audio for (max 4096 chars) |
| `voice` | string | Yes | Voice to use ("alloy", "echo", "fable", "onyx", "nova", "shimmer") |
| `response_format` | string | No | Format of audio ("mp3", "opus", "aac", "flac", "wav", "pcm") |
| `speed` | number | No | Speed of audio (0.25 - 4.0) |

#### Response

**Status Code:** 200 OK

**Content Type:** `audio/*` (depends on response_format)

Returns the audio file as binary data.

#### Error Responses

**400 Bad Request** - Invalid request parameters  
**422 Unprocessable Entity** - Validation error

#### Example Request

```json
{
  "model": "tts-1",
  "input": "Hello, how are you today?",
  "voice": "alloy",
  "speed": 1.0
}
```

---

### GET /v1/models

**Summary:** List Available Models

**Description:** Lists the currently available models and provides basic information about each.

**Operation ID:** `list_models`

**Tags:** `Mimic`

**Security:** Requires Authorization

**Read-Only:** true  
**Idempotent:** true  
**Destructive:** false

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `ModelList`

| Field | Type | Description |
|-------|------|-------------|
| `object` | string | Object type ("list") |
| `data` | array | Array of model objects |

#### Model Object

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Model identifier |
| `object` | string | Object type ("model") |
| `created` | integer | Unix timestamp of model creation |
| `owned_by` | string | Organization that owns the model |

#### Error Responses

**422 Unprocessable Entity** - Validation error

#### Example Response

```json
{
  "object": "list",
  "data": [
    {
      "id": "gpt-4",
      "object": "model",
      "created": 1687882411,
      "owned_by": "openai"
    },
    {
      "id": "stable-diffusion-xl",
      "object": "model",
      "created": 1687882411,
      "owned_by": "stability-ai"
    }
  ]
}
```

---

## Account Management Endpoints

### GET /account

**Summary:** Get Account Information

**Description:** Retrieves information about the authenticated user's account.

**Operation ID:** `get_account`

**Tags:** `User Account`

**Security:** Requires Authorization

**Read-Only:** true  
**Idempotent:** true  
**Destructive:** false

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `Account`

| Field | Type | Description |
|-------|------|-------------|
| `user_id` | integer | User's unique identifier |
| `email` | string | User's email address |
| `username` | string or null | User's username |
| `credits` | number | Available credits |
| `tier` | string | Account tier/plan |
| `created_at` | string | Account creation timestamp (ISO 8601) |
| `limits` | object | Usage limits and quotas |

#### Error Responses

**401 Unauthorized** - Invalid or missing API key  
**422 Unprocessable Entity** - Validation error

#### Example Response

```json
{
  "user_id": 12345,
  "email": "user@example.com",
  "username": "johndoe",
  "credits": 1000.50,
  "tier": "pro",
  "created_at": "2024-01-15T10:30:00Z",
  "limits": {
    "max_requests_per_day": 10000,
    "max_concurrent_requests": 10
  }
}
```

---

### GET /account/keys

**Summary:** List API Keys

**Description:** Retrieves a list of API keys associated with the authenticated user's account.

**Operation ID:** `list_keys`

**Tags:** `User Account`

**Security:** Requires Authorization

**Read-Only:** true  
**Idempotent:** true  
**Destructive:** false

#### Response

**Status Code:** 200 OK

**Content Type:** `application/json`

**Schema:** `APIKeyList`

| Field | Type | Description |
|-------|------|-------------|
| `keys` | array | Array of API key objects |

#### APIKey Object

| Field | Type | Description |
|-------|------|-------------|
| `key_id` | string | Unique identifier for the key |
| `key_prefix` | string | First few characters of the key |
| `name` | string or null | Optional name for the key |
| `created_at` | string | Creation timestamp (ISO 8601) |
| `last_used_at` | string or null | Last usage timestamp (ISO 8601) |
| `is_active` | boolean | Whether the key is active |

#### Error Responses

**401 Unauthorized** - Invalid or missing API key  
**422 Unprocessable Entity** - Validation error

#### Example Response

```json
{
  "keys": [
    {
      "key_id": "key_abc123",
      "key_prefix": "sk-rst_abc",
      "name": "Production Key",
      "created_at": "2024-01-15T10:30:00Z",
      "last_used_at": "2024-01-18T14:22:00Z",
      "is_active": true
    },
    {
      "key_id": "key_xyz789",
      "key_prefix": "sk-rst_xyz",
      "name": "Development Key",
      "created_at": "2024-01-10T08:15:00Z",
      "last_used_at": null,
      "is_active": true
    }
  ]
}
```

---

### POST /account/keys

**Summary:** Create API Key

**Description:** Creates a new API key for the authenticated user's account.

**Operation ID:** `create_key`

**Tags:** `User Account`

**Security:** Requires Authorization

**Destructive:** false

#### Request Body

**Content Type:** `application/json`

**Schema:** `CreateAPIKeyRequest`

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `name` | string | No | Optional name for the key |
| `expires_at` | string | No | Optional expiration date (ISO 8601) |
| `scopes` | array | No | Optional array of permission scopes |

#### Response

**Status Code:** 201 Created

**Content Type:** `application/json`

**Schema:** `CreateAPIKeyResponse`

| Field | Type | Description |
|-------|------|-------------|
| `key_id` | string | Unique identifier for the key |
| `key` | string | Full API key (only shown once) |
| `name` | string or null | Name of the key |
| `created_at` | string | Creation timestamp (ISO 8601) |
| `expires_at` | string or null | Expiration timestamp (ISO 8601) |

⚠️ **Important:** The full API key is only returned once. Store it securely as it cannot be retrieved again.

#### Error Responses

**401 Unauthorized** - Invalid or missing API key  
**422 Unprocessable Entity** - Validation error

#### Example Request

```json
{
  "name": "New Production Key",
  "scopes": ["imagine", "chat", "images"]
}
```

#### Example Response

```json
{
  "key_id": "key_new123",
  "key": "sk-rst_abcdefghijklmnopqrstuvwxyz123456789",
  "name": "New Production Key",
  "created_at": "2024-01-18T15:30:00Z",
  "expires_at": null
}
```

---

## Schemas

### Common Data Types

#### HTTPValidationError

Validation error response structure.

| Field | Type | Description |
|-------|------|-------------|
| `detail` | array | Array of validation error details |

#### ValidationError Detail

| Field | Type | Description |
|-------|------|-------------|
| `loc` | array | Location of the error (path in request) |
| `msg` | string | Error message |
| `type` | string | Error type |

---

## Usage Examples

### Python Example - Generate Image

```python
import requests

url = "https://api.rostro.dev/imagine"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}
payload = {
    "prompt": "A futuristic cityscape at night with neon lights",
    "model": "stable-diffusion-xl",
    "width": 1024,
    "height": 768,
    "num_outputs": 1
}

response = requests.post(url, json=payload, headers=headers)
result = response.json()

if result.get("primary_media_url"):
    print(f"Image URL: {result['primary_media_url']}")
```

### Python Example - Chat Completion

```python
import requests

url = "https://api.rostro.dev/v1/chat/completions"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}
payload = {
    "model": "gpt-4",
    "messages": [
        {"role": "user", "content": "Explain quantum computing in simple terms"}
    ],
    "temperature": 0.7,
    "max_tokens": 200
}

response = requests.post(url, json=payload, headers=headers)
result = response.json()

print(result["choices"][0]["message"]["content"])
```

### cURL Example - Transcribe Audio

```bash
curl -X POST https://api.rostro.dev/v1/audio/transcriptions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -F "file=@/path/to/audio.mp3" \
  -F "model=whisper-1" \
  -F "language=en" \
  -F "response_format=json"
```

### JavaScript Example - List Models

```javascript
const url = "https://api.rostro.dev/v1/models";
const headers = {
    "Authorization": "Bearer YOUR_API_KEY"
};

fetch(url, { headers })
    .then(response => response.json())
    .then(data => {
        console.log("Available models:", data.data);
    })
    .catch(error => console.error("Error:", error));
```

---

## Rate Limits

Rate limits vary by account tier and endpoint. Check your account information for specific limits. Generally:

- **Free tier**: Lower rate limits, suitable for testing
- **Pro tier**: Higher rate limits for production use
- **Enterprise tier**: Custom rate limits

When you exceed rate limits, you'll receive a `429 Too Many Requests` response.

---

## Error Handling

All errors follow a consistent format:

```json
{
  "error": {
    "message": "Description of the error",
    "type": "invalid_request_error",
    "code": "invalid_api_key"
  }
}
```

Common error codes:
- `invalid_api_key` - The API key is invalid or missing
- `insufficient_credits` - Not enough credits for the operation
- `rate_limit_exceeded` - Too many requests
- `invalid_request_error` - Invalid parameters or request format
- `server_error` - Internal server error

---

## Support

For support, questions, or feedback:
- Email: support@rostro.dev
- Documentation: https://rostro.dev/docs
- Terms of Service: https://rostro.dev/tos

---

**Last Updated:** January 2025  
**API Version:** 0.5.9

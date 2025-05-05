# Voice Synthesis API Documentation

## Base URL
```
https://tkpm-production.up.railway.app
```

## Endpoints

### 1. Voice Synthesis
Convert text to speech using Google Cloud Text-to-Speech API.

**Endpoint:** `/api/v1/voice/synthesize`  
**Method:** `POST`  
**Content-Type:** `application/json`

#### Request Body
```json
{
    "text": "Text to convert to speech",
    "voice_id": "en-US-Neural2-A",
    "language": "en-US",
    "speed": 1.0
}
```

| Parameter | Type | Description | Required |
|-----------|------|-------------|----------|
| text | string | Text to convert to speech | Yes |
| voice_id | string | Voice ID from Google Cloud TTS | Yes |
| language | string | Language code (e.g., en-US, es-ES) | Yes |
| speed | float | Speech rate (0.25 to 4.0) | Yes |

#### Response
```json
{
    "voice_id": "63b61466-15b6-40bb-b4cb-2cd877450a8f",
    "audio_url": "/static/audio/63b61466-15b6-40bb-b4cb-2cd877450a8f.mp3",
    "duration": 0.93
}
```

| Field | Type | Description |
|-------|------|-------------|
| voice_id | string | Unique identifier for the generated audio |
| audio_url | string | URL to access the generated audio file |
| duration | float | Duration of the audio in seconds |

#### Example Usage

Using cURL:
```bash
curl -X POST https://tkpm-production.up.railway.app/api/v1/voice/synthesize \
  -H "Content-Type: application/json" \
  -d '{
    "text": "Hello! This is a test of the voice synthesis service.",
    "voice_id": "en-US-Neural2-A",
    "language": "en-US",
    "speed": 1.0
  }'
```

Using Python:
```python
import requests

url = "https://tkpm-production.up.railway.app/api/v1/voice/synthesize"
payload = {
    "text": "Hello! This is a test of the voice synthesis service.",
    "voice_id": "en-US-Neural2-A",
    "language": "en-US",
    "speed": 1.0
}
headers = {"Content-Type": "application/json"}

response = requests.post(url, json=payload, headers=headers)
print(response.json())
```

## Available Voices

### English (en-US)
- `en-US-Neural2-A` - Female voice
- `en-US-Neural2-C` - Female voice
- `en-US-Neural2-D` - Male voice
- `en-US-Neural2-E` - Female voice
- `en-US-Neural2-F` - Female voice
- `en-US-Neural2-G` - Female voice
- `en-US-Neural2-H` - Female voice
- `en-US-Neural2-I` - Male voice
- `en-US-Neural2-J` - Male voice

### Spanish (es-ES)
- `es-ES-Neural2-A` - Female voice
- `es-ES-Neural2-B` - Female voice
- `es-ES-Neural2-C` - Female voice
- `es-ES-Neural2-D` - Female voice
- `es-ES-Neural2-E` - Female voice
- `es-ES-Neural2-F` - Female voice

## Error Handling

The API returns appropriate HTTP status codes and error messages:

- `200 OK`: Request successful
- `400 Bad Request`: Invalid request parameters
- `422 Unprocessable Entity`: Validation error
- `500 Internal Server Error`: Server-side error

Example error response:
```json
{
    "detail": "Invalid voice_id: invalid-voice"
}
```

## Rate Limiting

The API has rate limiting to prevent abuse. Please contact the administrator for specific limits.

## Best Practices

1. **Text Length**: Keep text inputs reasonable in length (recommended < 5000 characters)
2. **Voice Selection**: Choose appropriate voice and language combinations
3. **Speed Parameter**: Use values between 0.25 and 4.0 for optimal results
4. **Error Handling**: Always implement proper error handling in your applications
5. **Caching**: Cache generated audio files when possible to reduce API calls

## Support

For support or to report issues, please contact the administrator or open an issue in the project repository. 
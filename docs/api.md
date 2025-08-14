# API Reference

This page contains the API reference documentation.

## Authentication

All API requests require authentication using an API key.

### Headers

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

## Endpoints

### GET /api/v1/users

Retrieve a list of users.

**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `limit` | integer | Maximum number of users to return (default: 20) |
| `offset` | integer | Number of users to skip (default: 0) |
| `search` | string | Search term to filter users |

**Response:**

```json
{
  "users": [
    {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com",
      "created_at": "2023-01-01T00:00:00Z"
    }
  ],
  "total": 1,
  "limit": 20,
  "offset": 0
}
```

### POST /api/v1/users

Create a new user.

**Request Body:**

```json
{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "password": "secure_password"
}
```

**Response:**

```json
{
  "id": 2,
  "name": "Jane Doe",
  "email": "jane@example.com",
  "created_at": "2023-01-02T00:00:00Z"
}
```

### GET /api/v1/users/{id}

Retrieve a specific user by ID.

**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `id` | integer | User ID |

**Response:**

```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com",
  "created_at": "2023-01-01T00:00:00Z",
  "updated_at": "2023-01-01T00:00:00Z"
}
```

## Error Responses

The API uses standard HTTP status codes and returns error information in JSON format.

### Error Format

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "The request data is invalid",
    "details": {
      "field": "email",
      "issue": "Email format is invalid"
    }
  }
}
```

### Status Codes

| Status Code | Description |
|-------------|-------------|
| 200 | Success |
| 201 | Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |
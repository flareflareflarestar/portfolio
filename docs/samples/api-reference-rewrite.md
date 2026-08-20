> **Source text**<br />
> Url is `/api/v2/users` and you have to POST to it. Needs authentication header `Authorization: Bearer <token>`. Don't forget `Content-Type: application/json`. In the request body, `username` is required (string, 3-20 chars). `email` is required too (must be a valid email string). `role` is optional string, defaults to "user", but can be "admin" or "editor". `age` is optional integer, must be between 18 and 120. If it succeeds, it returns `201 Created` with a JSON body that has the newly created `id` (integer), `username`, `email`, `role`, `age`, and `created_at` (ISO 8601 timestamp). If you forget required fields or pass invalid data like age under 18, it gives `400 Bad Request` with `{"error": "Validation failed", "details": "age must be at least 18"}`. If token is missing/invalid, you get `401 Unauthorized` with `{"error": "Invalid token"}`. If email or username is already taken, it throws `409 Conflict` with `{"error": "User already exists"}`.

---

# Endpoint: `POST /api/v2/users`

## Headers

| Header | Required |
|:---|:---|
| `Authorization: Bearer <token>` | mandatory |
| `Content-Type: application/json` | mandatory |

## Body Parameters

| Parameter | Type | Required | Description |
|:---|:---|:---|:---|
| `username` | String (3-20 chars) | mandatory | Used for user profile |
| `email` | String (valid email) | mandatory | Used for log in and notifications |
| `role` | String ("user", "admin", or "editor") | optional (defaults "user") | Enables specific features and privileges |
| `age` | Integer (between 18 and 120) | optional | For data collection purposes |

## Responses

### 201 Created

User profile successfully created. An example payload returned: 
```json
    { 
        "id": 1,
        "username": "flareflareflarestar",
        "email": "flare@st.ar",
        "role": "admin",
        "age": 69,
        "created_at": "2026-08-18T06:58:05-06:00"
    }
```

### 400 Bad Request

Invalid data passed. Returns:
```json
    {
        "error": "Validation failed",
        "details": "Age must be at least 18"

    }
```

### 401 Unauthorized

Missing or invalid token. Returns:
```json
    {
        "error": "Invalid token"
    }
```

### 409 Conflict

Username or email already taken. Returns:
```json
    {
        "error": "User already exists"
    }
```

---

# Retrospective

## The Challenge

The original endpoint specifications were provided as unstructured, raw developer notes. Crucial integration details such as request parameters, mandatory headers, default values, constraint boundaries, and error schemas were embedded in narrative text, making it time consuming for developers to construct valid API requests.

## Key Improvements Made

- Standardised endpoint layout: Adopted a RESTful API documentation layout with clear visual hierarchy.
- Structured parameter schema: Created concise tables for request headers and request parameters detailing data types, constraints, and default behaviours.
- Formatted JSON payloads: Provided clear examples of successful responses and error scenarios aiding developers in debugging and testing.

## Impact

By standardising the endpoint reference, developers can quickly integrate the API, construct valid requests, and correctly handle error scenarios without needing to consult backend engineers.
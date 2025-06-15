# Blog Platform API Documentation

This document provides details about the REST API endpoints available in the Blog Platform application.

## Base URL

```
http://localhost:5000/api
```

## Authentication

Most endpoints require authentication. Include the JWT token in the Authorization header:

```
Authorization: Bearer <your_jwt_token>
```

## Endpoints

### Authentication

#### Register a new user

```
POST /auth/register
```

Request body:
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```

Response:
```json
{
  "token": "jwt_token_here",
  "user": {
    "id": "user_id",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

#### Login

```
POST /auth/login
```

Request body:
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

Response:
```json
{
  "token": "jwt_token_here",
  "user": {
    "id": "user_id",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

#### Get current user

```
GET /auth/user
```

Response:
```json
{
  "id": "user_id",
  "name": "John Doe",
  "email": "john@example.com"
}
```

### Blogs

#### Get all blogs

```
GET /blogs
```

Response:
```json
[
  {
    "id": "blog_id_1",
    "title": "Blog Title 1",
    "content": "Blog content here...",
    "author": "John Doe",
    "userId": "user_id",
    "createdAt": "2023-07-15T10:30:00.000Z",
    "likes": ["user_id_1", "user_id_2"],
    "views": 42,
    "tags": ["technology", "programming"],
    "imageBase64": "base64_encoded_image_data",
    "commentCount": 5
  },
  {
    "id": "blog_id_2",
    "title": "Blog Title 2",
    "content": "Another blog content...",
    "author": "Jane Smith",
    "userId": "another_user_id",
    "createdAt": "2023-07-14T15:45:00.000Z",
    "likes": ["user_id_3"],
    "views": 27,
    "tags": ["travel", "adventure"],
    "imageBase64": "base64_encoded_image_data",
    "commentCount": 2
  }
]
```

#### Get a specific blog

```
GET /blogs/:id
```

Response:
```json
{
  "id": "blog_id_1",
  "title": "Blog Title 1",
  "content": "Blog content here...",
  "author": "John Doe",
  "userId": "user_id",
  "createdAt": "2023-07-15T10:30:00.000Z",
  "likes": ["user_id_1", "user_id_2"],
  "views": 42,
  "tags": ["technology", "programming"],
  "imageBase64": "base64_encoded_image_data",
  "commentCount": 5
}
```

#### Create a new blog

```
POST /blogs
```

Request body:
```json
{
  "title": "New Blog Title",
  "content": "New blog content...",
  "tags": ["technology", "programming"],
  "imageBase64": "base64_encoded_image_data"
}
```

Response:
```json
{
  "id": "new_blog_id",
  "title": "New Blog Title",
  "content": "New blog content...",
  "author": "John Doe",
  "userId": "user_id",
  "createdAt": "2023-07-16T09:20:00.000Z",
  "likes": [],
  "views": 0,
  "tags": ["technology", "programming"],
  "imageBase64": "base64_encoded_image_data",
  "commentCount": 0
}
```

#### Update a blog

```
PUT /blogs/:id
```

Request body:
```json
{
  "title": "Updated Blog Title",
  "content": "Updated blog content...",
  "tags": ["technology", "programming", "web"]
}
```

Response:
```json
{
  "id": "blog_id",
  "title": "Updated Blog Title",
  "content": "Updated blog content...",
  "author": "John Doe",
  "userId": "user_id",
  "createdAt": "2023-07-15T10:30:00.000Z",
  "updatedAt": "2023-07-16T11:45:00.000Z",
  "likes": ["user_id_1", "user_id_2"],
  "views": 42,
  "tags": ["technology", "programming", "web"],
  "imageBase64": "base64_encoded_image_data",
  "commentCount": 5
}
```

#### Delete a blog

```
DELETE /blogs/:id
```

Response:
```json
{
  "message": "Blog deleted successfully"
}
```

#### Like a blog

```
POST /blogs/:id/like
```

Response:
```json
{
  "message": "Blog liked successfully"
}
```

#### Unlike a blog

```
POST /blogs/:id/unlike
```

Response:
```json
{
  "message": "Blog unliked successfully"
}
```

#### Increment blog view count

```
POST /blogs/:id/view
```

Response:
```json
{
  "message": "View count incremented"
}
```

### User-specific endpoints

#### Get blogs by current user

```
GET /users/blogs
```

Response:
```json
[
  {
    "id": "blog_id_1",
    "title": "Blog Title 1",
    "content": "Blog content here...",
    "author": "John Doe",
    "userId": "user_id",
    "createdAt": "2023-07-15T10:30:00.000Z",
    "likes": ["user_id_1", "user_id_2"],
    "views": 42,
    "tags": ["technology", "programming"],
    "imageBase64": "base64_encoded_image_data",
    "commentCount": 5
  }
]
```

#### Bookmark a blog

```
POST /users/bookmark/:id
```

Response:
```json
{
  "message": "Blog bookmarked successfully"
}
```

#### Remove a bookmark

```
DELETE /users/bookmark/:id
```

Response:
```json
{
  "message": "Bookmark removed successfully"
}
```

#### Get all bookmarked blogs

```
GET /users/bookmarks
```

Response:
```json
[
  {
    "id": "blog_id_1",
    "title": "Blog Title 1",
    "content": "Blog content here...",
    "author": "John Doe",
    "userId": "user_id",
    "createdAt": "2023-07-15T10:30:00.000Z",
    "likes": ["user_id_1", "user_id_2"],
    "views": 42,
    "tags": ["technology", "programming"],
    "imageBase64": "base64_encoded_image_data",
    "commentCount": 5
  }
]
```

## Error Responses

All endpoints may return the following error responses:

### 400 Bad Request

```json
{
  "error": "Invalid request parameters"
}
```

### 401 Unauthorized

```json
{
  "error": "Authentication required"
}
```

### 403 Forbidden

```json
{
  "error": "You do not have permission to perform this action"
}
```

### 404 Not Found

```json
{
  "error": "Resource not found"
}
```

### 500 Internal Server Error

```json
{
  "error": "Internal server error"
}
```
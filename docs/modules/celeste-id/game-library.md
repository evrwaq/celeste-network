## Game Library

- **Route**: `GET /api/v1/game-library`

### Request

- **Headers**:
  ```json
  {
    "Authorization": "Bearer jwt-token"
  }
  ```

### Response

- **Response** (200. Ok):
  ```json
  {
    "library": [
      {
        "gameId": "game123",
        "title": "Amazing Game",
        "purchaseDate": "2023-11-01",
        "platform": "PS5"
      },
      {
        "gameId": "game456",
        "title": "Adventure Game",
        "purchaseDate": "2023-12-10",
        "platform": "PC"
      }
    ]
  }
  ```
- **Response** (401. Authentication Error):
  ```json
  {
    "error": "Unauthorized"
  }
  ```
- **Response** (500. Server Error):
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

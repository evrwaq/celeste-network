## Username Change

- **Route**: `POST /api/v1/username-change`

### Request

- **Request Headers**:
  ```json
  {
    "Authorization": "Bearer jwt-token"
  }
  ```
- **Request Body**:
  ```json
  {
    "newUsername": "new_username"
  }
  ```

### Validation Rules

- **Username**

  - Must be between 3 and 12 characters.
  - Must be unique.
  - Can include numbers, but cannot start with a number.
  - Can contain uppercase and lowercase letters.
  - Allowed characters: letters, numbers, \_ (underscore), and . (period).
  - Cannot start with a number, underscore, or period.

### Response

- **Response** (201. Created):
  ```json
  {
    "message": "Username successfully changed"
  }
  ```
- **Response** (400. Validation Error - Invalid Username):
  ```json
  {
    "error": "Username is invalid"
  }
  ```
- **Response** (409. Conflict Error - Username already exists):
  ```json
  {
    "error": "Username already exists"
  }
  ```
- **Response** (500. Server Error):
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

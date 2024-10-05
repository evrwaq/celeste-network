## Sign Up

- **Route**: `POST /api/v1/sign-up`

### Request

- **Request Body**:
  ```json
  {
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123"
  }
  ```

### Response

- **Response** (201. Created):
  ```json
  {
    "celesteId": "abc123",
    "accessToken": "jwt-token"
  }
  ```
- **Response** (400. Validation Error - Invalid Email):
  ```json
  {
    "error": "Invalid email format"
  }
  ```
- **Response** (400. Validation Error - Weak Password):
  ```json
  {
    "error": "Password must be at least 8 characters long"
  }
  ```
- **Response** (500. Server Error):
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

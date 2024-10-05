## Sign Up

- **Route**: `POST /api/v1/sign-up`

### Request

- **Request Body**:
  ```json
  {
    "name": "John Doe",
    "username": "john_doe",
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
- **Response** (400. Validation Error - Invalid Name):
  ```json
  {
    "error": "Name is invalid"
  }
  ```
- **Response** (400. Validation Error - Invalid Username):
  ```json
  {
    "error": "Username is invalid"
  }
  ```
- **Response** (400. Validation Error - Invalid Email):
  ```json
  {
    "error": "Email is invalid"
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

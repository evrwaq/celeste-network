## Sign In

- **Route**: `POST /api/v1/sign-in`

### Request

- **Request Body**:
  ```json
  {
    "email": "johndoe@example.com",
    "password": "Password123!"
  }
  ```

### Validation Rules

- **Email**

  - Must be a valid email format.
  - Email must be registered

### Response

- **Response** (200. Ok):
  ```json
  {
    "accessToken": "jwt-token"
  }
  ```
- **Response** (400. Validation Error - Invalid Email):
  ```json
  {
    "error": "Email is invalid"
  }
  ```
- **Response** (404. Not Found Error - Email is not registered):
  ```json
  {
    "error": "Email is not registered"
  }
  ```
- **Response** (500. Server Error):
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

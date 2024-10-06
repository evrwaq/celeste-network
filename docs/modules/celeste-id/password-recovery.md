## Password Recovery

### Step 1: Request Password Recovery

- **Route**: `POST /api/v1/password-recovery/request`

### Request

- **Request Body**:
  ```json
  {
    "email": "johndoe@example.com"
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
    "message": "Password recovery code sent to your email"
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

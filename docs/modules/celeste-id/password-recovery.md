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

### Step 2: Validate Code and Generate New Password

- **Route**: `POST /api/v1/password-recovery/validate-code`

### Request

- **Request Body**:
  ```json
  {
    "email": "johndoe@example.com",
    "code": "ABC123"
  }
  ```

### Validation Rules

- **Email**

  - Must be a valid email format.
  - Email must be registered

- **Code**
  - Must be a 6-character alphanumeric code.
  - The code must match the one sent to the user's email.

### Response

- **Response** (200. Ok):
  ```json
  {
    "message": "A new password has been generated and sent to your email"
  }
  ```
- **Response** (400. Validation Error - Invalid Email):
  ```json
  {
    "error": "Email is invalid"
  }
  ```
- **Response** (400. Validation Error - Invalid Code):
  ```json
  {
    "error": "The provided code is incorrect"
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

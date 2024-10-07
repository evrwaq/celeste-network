## Email Change

### Step 1: Request to Change Email

- **Route**: `POST /api/v1/email-change`

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
    "newEmail": "newemail@example.com"
  }
  ```

### Validation Rules

- **New Email**

  - Must be a valid email format.
  - Must not be the same as the current email.
  - Must be unique (not already in use by another account).

### Response

- **Response** (200. Ok):
  ```json
  {
    "message": "Email change request initiated, please confirm your new email"
  }
  ```
- **Response** (400. Validation Error - Invalid Email):
  ```json
  {
    "error": "New email is invalid"
  }
  ```
- **Response** (400. Validation Error - Same Email):
  ```json
  {
    "error": "New email cannot be the same as the current email"
  }
  ```
- **Response** (401. Authentication Error):
  ```json
  {
    "error": "Unauthorized"
  }
  ```
- **Response** (409. Conflict Error - Email Already Exists):
  ```json
  {
    "error": "Email is already associated with another account"
  }
  ```
- **Response** (500. Server Error):
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

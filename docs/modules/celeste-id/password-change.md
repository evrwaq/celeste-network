# Password Change

- **Route**: `POST /api/v1/password-change`

## Request

- **Request Headers**:

  ```json
  {
    "Authorization": "Bearer jwt-token"
  }
  ```

- **Request Body**:

  ```json
  {
    "currentPassword": "currentpassword123",
    "newPassword": "newpassword456"
  }
  ```

## Validation Rules

- **Current Password**

  - Must match the password stored in the database.

- **New Password**

  - Must be between 8 and 255 characters long.
  - Must contain at least one uppercase letter, one lowercase letter, one number, and one special character.
  - Cannot be the same as the current password.

## Response

- **Response** (200. Ok):

  ```json
  {
    "message": "Password changed successfully"
  }
  ```

- **Response** (400. Validation Error - Invalid New Password):

  ```json
  {
    "error": "Password must be between 8 and 255 characters long, at least 1 uppercase letter, 1 lowercase letter, 1 number and 1 special character"
  }
  ```

- **Response** (400. Validation Error - Invalid Current Password):

  ```json
  {
    "error": "Current password is incorrect"
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

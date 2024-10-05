## Sign Up

- **Route**: `POST /api/v1/sign-up`

### Request

- **Request Body**:
  ```json
  {
    "name": "John Doe",
    "username": "john_doe",
    "email": "johndoe@example.com",
    "password": "Password123!"
  }
  ```

### Validation Rules

- **Name**

  - Must be between 2 and 50 characters.
  - Can contain only letters, and only 1 space between names

- **Username**

  - Must be between 3 and 12 characters.
  - Must be unique.
  - Can include numbers, but cannot start with a number.
  - Can contain uppercase and lowercase letters.
  - Allowed characters: letters, numbers, \_ (underscore), and . (period).
  - Cannot start with a number, underscore, or period.

- **Email**

  - Must be a valid email format.
  - Must be unique.

- **Password**
  - Must be between 8 and 255 characters long.
  - Must contain at least one uppercase letter, one lowercase letter, one number, and one special character.

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
- **Response** (400. Validation Error - Invalid Password):
  ```json
  {
    "error": "Password must be between 8 and 255 characters long, at least 1 uppercase letter, 1 lowercase letter, 1 number and 1 special character"
  }
  ```
- **Response** (409. Conflict Error - Username already exists):
  ```json
  {
    "error": "Username already exists"
  }
  ```
- **Response** (409. Conflict Error - Email already exists):
  ```json
  {
    "error": "Email already exists"
  }
  ```
- **Response** (500. Server Error):
  ```json
  {
    "error": "Internal server error. Please try again later."
  }
  ```

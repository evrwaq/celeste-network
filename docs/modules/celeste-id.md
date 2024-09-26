# Celeste ID

The **Celeste ID** module is responsible for account and profile management, offering features for account creation, login, profile customization, and game history. Additionally, new functionalities have been added to enhance account, games, and trophies management for the user.

- **Celeste ID Registration**

  - Creation of a new Celeste ID with data validation.

- **Login**

  - User authentication using email and password.

- **Password Recovery**

  - Sends an email to reset the user's password.

- **Password Change**

  - Allows users to change their password. The user must provide their current password and will receive an email to confirm the password change.

- **Profile Settings**

  - Update information such as username, password, profile picture, etc.

- **Email Change**

  - Allows users to change the email associated with their account, with additional security validation to ensure the change is legitimate.

- **Game Library**

  - Displays the library of games purchased by the user, which may or may not have been played.

- **Game History**

  - Displays the history of games played by the user, including unlocked trophies and game progress.

- **Trophy Management**

  - Displays all unlocked and pending trophies from the games the user has played, and allows querying unlock conditions for each trophy.

- **Two-Factor Authentication (2FA)**

  - Enables or disables two-factor authentication to enhance account security.

- **Session Management**

  - Displays all active login sessions for the user, allowing them to terminate specific sessions if needed, such as in case of a login on unfamiliar devices.

- **Purchase History**

  - Displays the full purchase history of the user, including dates, acquired games, and other digital content purchased.

- **Subscription Management**
  - Manage active or expired subscriptions associated with the user, including the ability to renew or cancel.

---

## Celeste ID Entity (Database Structure)

```typescript
{
  "userId": "abc123",
  "name": "John Doe",
  "email": "johndoe@example.com",
  "profileImage": "url-to-image",
  "library": [
    {
      "gameId": "game123",
      "purchaseDate": "2024-01-15"
    },
    {
      "gameId": "game456",
      "purchaseDate": "2024-02-01"
    }
  ],
  "playedGames": [
    {
      "gameId": "game123",
      "playStartDate": "2024-01-20",
      "trophies": [
        {
          "trophyId": "trophy456",
          "name": "First Step",
          "unlocked": true,
          "unlockedAt": "2024-01-21",
          "score": 10,
          "tier": "bronze",
          "unlockConditions": "Complete the first level of the game"
        },
        {
          "trophyId": "trophy789",
          "name": "Master Explorer",
          "unlocked": false,
          "score": 25,
          "tier": "silver",
          "unlockConditions": "Discover all secret areas"
        },
        {
          "trophyId": "platinum123",
          "name": "Ultimate Champion",
          "unlocked": false,
          "score": 100,
          "tier": "platinum",
          "unlockConditions": "Unlock all other trophies in the game"
        }
      ],
      "trophyProgress": 25 // Based on the percentage of unlocked trophies (1 out of 4 unlocked = 25%)
    }
  ],
  "purchaseHistory": [
    {
      "purchaseId": "purchase123",
      "gameId": "game123",
      "purchaseDate": "2024-01-15",
      "price": {
        "value": 59.99,
        "currency": "$"
      }
    }
  ],
  "activeSessions": [
    {
      "sessionId": "session123",
      "device": "iPhone",
      "loginDate": "2024-01-14T12:34:56Z",
      "ipAddress": "192.168.0.1"
    }
  ],
  "subscriptions": [
    {
      "subscriptionId": "sub123",
      "status": "active",
      "startDate": "2024-01-01",
      "endDate": "2025-01-01",
      "renewalDate": "2025-01-01"
    }
  ]
}
```

---

## API Requests and Responses

### 1. **Account Creation**

- **Route**: `POST /api/celeste-id/register`
- **Request Body**:
  ```json
  {
    "name": "John Doe",
    "username": "john_doe",
    "email": "johndoe@example.com",
    "password": "password123"
  }
  ```
- **Response**:
  ```json
  {
    "accessToken": "jwt-token"
  }
  ```

### 2. **Login**

- **Route**: `POST /api/celeste-id/login`
- **Request Body**:
  ```json
  {
    "email": "johndoe@example.com",
    "password": "password123"
  }
  ```
- **Response**:
  ```json
  {
    "accessToken": "jwt-token"
  }
  ```

### 3. **Password Recovery**

- **Route**: `POST /api/celeste-id/recover-password`
- **Request Body**:
  ```json
  {
    "email": "johndoe@example.com"
  }
  ```
- **Response**:
  ```json
  {
    "message": "Password recovery email sent to johndoe@example.com"
  }
  ```

### 4. **Password Change**

- **Route**: `POST /api/celeste-id/change-password`
- **Request Body**:
  ```json
  {
    "currentPassword": "password123",
    "newPassword": "newpassword456"
  }
  ```
- **Response**:
  ```json
  {
    "message": "Password change request initiated. Please check your email to confirm the change."
  }
  ```

### 5. **Profile Update**

- **Route**: `PUT /api/celeste-id/update-profile`
- **Request Body**:
  ```json
  {
    "name": "John Doe",
    "profileImage": "url-to-new-image"
  }
  ```
- **Response**:
  ```json
  {
    "message": "Profile updated successfully",
    "name": "John Doe",
    "profileImage": "url-to-new-image"
  }
  ```

### 6. **Email Change**

- **Route**: `POST /api/celeste-id/change-email`
- **Request Body**:
  ```json
  {
    "newEmail": "newemail@example.com"
  }
  ```
- **Response**:
  ```json
  {
    "message": "Email change request initiated. Please check your new email to confirm the change."
  }
  ```

### 7. **View Game Library**

- **Route**: `GET /api/celeste-id/library`
- **Response**:
  ```json
  {
    "library": [
      {
        "gameId": "game123",
        "purchaseDate": "2024-01-15"
      },
      {
        "gameId": "game456",
        "purchaseDate": "2024-02-01"
      }
    ]
  }
  ```

### 8. **View Game History**

- **Route**: `GET /api/celeste-id/game-history`
- **Response**:
  ```json
  {
    "playedGames": [
      {
        "gameId": "game123",
        "playStartDate": "2024-01-20",
        "trophies": [
          {
            "trophyId": "trophy456",
            "name": "First Step",
            "unlocked": true,
            "unlockedAt": "2024-01-21",
            "score": 10,
            "tier": "bronze",
            "unlockConditions": "Complete the first level of the game"
          }
        ]
      }
    ]
  }
  ```

### 9. **Session Management**

- **Route**: `GET /api/celeste-id/sessions`
- **Response**:
  ```json
  {
    "activeSessions": [
      {
        "sessionId": "session123",
        "device": "iPhone",
        "loginDate": "2024-01-14T12:34:56Z",
        "ipAddress": "192.168.0.1"
      }
    ]
  }
  ```

---

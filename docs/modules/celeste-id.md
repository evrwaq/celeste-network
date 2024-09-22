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

## API Response

### 1. **All User Info**

<details>
  <summary>All user info</summary>
  <br/>

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
          "trophyId": "trophy987",
          "name": "Ultimate Explorer",
          "unlocked": false,
          "score": 50,
          "tier": "gold",
          "unlockConditions": "Complete the game without losing a life"
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
      "price": "59.99R$"
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

</details>

### 2. **User Played Games**

<details>
  <summary>Only games played by the user</summary>
  <br/>

```typescript
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
      "trophyProgress": 33.33 // Based on 1 out of 3 regular trophies unlocked (platinum included in total count)
    }
  ]
}
```

</details>

### 3. **User Game Library**

<details>
  <summary>Only games in the user's library</summary>
  <br/>

```typescript
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

</details>

### 4. **User Purchase History**

<details>
  <summary>Full purchase history of the user</summary>
  <br/>

```typescript
{
  "purchaseHistory": [
    {
      "purchaseId": "purchase123",
      "gameId": "game123",
      "purchaseDate": "2024-01-15",
      "price": "59.99R$"
    }
  ]
}
```

</details>

### 5. **Active Sessions**

<details>
  <summary>All active sessions for the user</summary>
  <br/>

```typescript
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

</details>

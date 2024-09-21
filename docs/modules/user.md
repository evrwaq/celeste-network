## User - _Celeste ID_

The User (Celeste ID) module is responsible for account and profile management, offering features for account creation, login, and profile customization.

- **Celeste ID Registration**
  - Creation of new Celeste ID with data validation.
- **Login**
  - User authentication with email and password.
- **Password Recovery**
  - Sends an email for password reset.
- **Profile Settings**
  - Update of information such as username, password, profile picture, etc.
- **Game History**
  - Displays the history of games purchased and played by the user.

## API Response

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
        ]
      }
    ]
  }
```

</details>

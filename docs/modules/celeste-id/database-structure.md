# Celeste ID Entity (Database Structure)

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

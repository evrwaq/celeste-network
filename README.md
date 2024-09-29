# Celeste Networ

## Modules

### 1. Celeste ID

The Celeste ID module is responsible for account and profile management, offering features for account creation, login, and profile customization.

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

### 2. Games

The games module manages the catalog of games available on the platform. Each game has detailed information and is associated with trophies that players can earn.

- **Game Catalog**
  - List of all games available on the platform.
- **Game Details**
  - Information such as title, description, price, genre, and available trophies.
- **Game Management**
  - Add, edit, and remove games from the catalog (admin only).

### 3. Trophies/Achievements

The trophies/achievements module manages the rewards players can earn by completing specific tasks in games.

- **Trophy Listing**
  - Displays all available trophies for a particular game.
- **Trophy Status**
  - Shows the user's progress in earning trophies for each game.
- **Trophy Unlock**
  - Records when a user unlocks a trophy in a game.

### 4. Store

The store contains all the games, subscriptions, and other items that users can purchase. Prices are shown according to the user's region.

- **Store Catalog**
  - Displays games, subscriptions, and special items available for purchase.
- **Promotions**
  - List of items that are on sale.
- **Product Details**
  - Description, price, and other information about store products.

### 5. Checkout

The checkout module is responsible for handling the purchase process for items selected by users, including games and subscriptions.

- **Payment Process**
  - Completes the purchase of selected items, supporting various payment methods.
- **Purchase History**
  - Displays the history of purchases made by the user.
- **Cart Management**
  - Adds and removes items from the cart before finalizing the payment.

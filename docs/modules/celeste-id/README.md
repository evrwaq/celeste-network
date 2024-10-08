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

## [Celeste ID Entity (Database Structure)](./database-structure.md)

---

## API Requests and Responses

### 1. [**Sign Up**](./sign-up.md)

### 2. [**Sign In**](./sign-in.md)

### 3. [**Password Recovery**](./password-recovery.md)

### 4. [**Password Change**](./password-change.md)

### 5. [**Email Change**](./email-change.md)

### 6. [**Game Library**](./game-library.md)

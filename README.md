## Final Project

**TuwaiqPay** : Application allows you to create account and send/receive money to/from any user in application using NFC or QRCode

## User Stories

- **Signup:** As an anon I can sign up in the app so that I start send, receive moneys
- **Login:** As a user I can login to the aapp so that I can log my exit points
- **Logout:** As a user I can logout from the app so no one else can use it
- **Send Moeny:** As a user I can send money to any user in the app using NFC or QRCode
- **Receive Money:** As a user I can receive money from another users in the app
- **Show QRCode:** As a user I can show my QRCode so anyone can scan it and send money to my account

## Client / Frontend

### React Navigation Routes (Reac-Native App)

| Path | Component | Permissions | Behavior |
| --- | --- | --- | --- |
| `/` | SplashPage | public `<Route>` | First screen when start the app |
| `/register` | RegisterComponent | anon only `<AnonRoute>` | Signup form, link to login, navigate to homepage after signup |
| `/login` | LoginComponent | anon only `<AnonRoute>` | Login form navigate to home page |
| `/home` | Home | users only`<PrivateRoute>` | Home page with navigator to all another pages and components |

### Components

- Card
  
- lastTransactions
  
- transferMethod
  
- Drawer
  

### Screens

- Home
  
- About App
  
- Login
  
- Register
  
- Transactions
  
- TransferMoney
  
- QRCode Generator
  

## Server / Backend

### Models

User model

```
{
  user: {type: String, required: true, unique: true},
  email: {type: String, required: true, unique: true},
  password: {type: String, required: true},
}
```

User accounts

```
 {
    userId: {type: Schema.Types.ObjectId,ref:'User'},
    accountType: {type: String, required: true},
    accountNumber: {type: Number, required: true}
    balance: {type: Number, required: true}
 }
```

Account Transactions

```
{
    accountNumber: {type: Schema.Types.Number,ref:'Account'},
    transaction: { type: Object, required: true },
}
```

### Backend routes

| HTTP Method | URL | Request Body | Success status | Error Status | Description |
| --- | --- | --- | --- | --- | --- |
| GET | `/auth/me` |     | 200 | 404 | Check if user is logged in and return profile page |
| POST | `/auth/signup` | {name, email, password} | 201 | 404 | Checks if fields not empty (422) and user not exists (409), then create user with encrypted password, and store user in session |
| POST | `/auth/login` | {username, password} | 200 | 401 | Checks if fields not empty (422), if user exists (404), and if password matches (404), then stores user in session |
| POST | `/auth/logout` | (empty) | 204 | 400 | Logs out the user |

### Links

- [Trello/Kanban](https://trello.com/b/mPehp6Ve/final-project)

- Git
  

[Client repository Link](https://github.com/TheRealBasel/TuwaiqPay-Frontend)

[Server repository Link](https://github.com/TheRealBasel/TuwaiqPay-Backend)

- Slides

- [Figma](https://www.figma.com/file/xJxNRuBDUaEPtNYiPzg8zA/Untitled?node-id=0%3A1)

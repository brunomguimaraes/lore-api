# Lore Explorer

Embark on a server-side journey through the Warcraft universe. This platform is an API designed to store, retrieve, and interact with the expansive lore of the world of Azeroth.

## Project Overview

This API serves as the backbone of a platform where users can dive into characters, locations, and major events from the Warcraft universe. It's equipped to handle CRUD operations for each entity.

## Technologies

- **Backend**: Node.js
- **Web Framework**: Express.js
- **Database**: MongoDB
- **User Authentication**: Passport.js
- **API Testing**: Postman

## Database Schemas

### 1. Characters

```javascript
{
    name: String,
    race: String,
    class: String,
    faction: String,
    history: String,
    notableEvents: [String],
    image: String,  // URL to an image
    contributors: [ObjectId]  // User IDs who contributed to this entry
}
```

### 2. Locations

```javascript
{
    name: String,
    region: String,
    history: String,
    notableEvents: [String],
    image: String,  // URL to an image
    contributors: [ObjectId]
}
```

### 3. Events

```javascript
{
    title: String,
    date: String,  // In-universe date
    participants: [ObjectId],  // Character IDs
    location: ObjectId,  // Location ID
    description: String,
    contributors: [ObjectId]
}
```

### 4. Users

```javascript
{
    username: String,
    password: String,  // Stored as a hash
    contributions: [ObjectId]  // IDs of characters, locations, or events they've added/edited
}
```

## Possible API Routes

- **Character Routes**:
    - GET `/characters`: Fetch all characters
    - GET `/characters/:id`: Fetch a single character by ID
    - POST `/characters`: Add a new character
    - PUT `/characters/:id`: Update an existing character
    - DELETE `/characters/:id`: Delete a character

- **Location Routes**:
    - GET `/locations`: Fetch all locations
    - GET `/locations/:id`: Fetch a single location by ID
    - POST `/locations`: Add a new location
    - PUT `/locations/:id`: Update an existing location
    - DELETE `/locations/:id`: Delete a location

- **Event Routes**:
    - GET `/events`: Fetch all events
    - GET `/events/:id`: Fetch a single event by ID
    - POST `/events`: Add a new event
    - PUT `/events/:id`: Update an existing event
    - DELETE `/events/:id`: Delete an event

- **User Authentication Routes**:
    - POST `/users/register`: Register a new user
    - POST `/users/login`: Log in a user
    - GET `/users/logout`: Log out a user
    - GET `/users/profile`: Get profile of the logged-in user

## Development Steps

1. **Setting Up Environment**:
    - Initialize a new Node.js project with `npm init`.
    - Install necessary packages (`express`, `mongoose`, `passport`, etc.).
    - Set up a basic server with Express in `app.js`.
  
2. **Building Models**:
    - Design the database models in the `/models` directory using Mongoose.
    - Connect the database using `mongoose.connect()`.
  
3. **Routing**:
    - Implement routes in the `/routes` directory.
    - Ensure that routes handle appropriate error scenarios and edge cases.
  
4. **User Authentication**:
    - Implement user registration and login using `passport.js`.
    - Ensure passwords are hashed before storing.

5. **Testing**:
    - Test routes using Postman to ensure they handle CRUD operations correctly.
    - Document any special scenarios or test cases.

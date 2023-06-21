# myContact-Backend

- project-root/
  - config/
    - dbConnetion/
  - controllers/
    - contactControllars/
    - userControllars/
  - middleware/
    - errorHandler/
    - validateTokenHandler/
  - models/
    - contactModels/
    - userModels/
  - routes/
    - contactRoutes/
    - userRoutes/
- .env/
- contants/
- server/



## Technologies

List the technologies and frameworks used in your project. Here are the main components of your stack:

- Node.js: Runtime environment for executing JavaScript code on the server-side.
- Express: Fast and minimalistic web application framework for Node.js.
- MongoDB: NoSQL database used to store contact information.
- JWT: JSON Web Tokens for authentication and authorization.

## Installation

npm i express -- for express installation
npm i mongoos -- for mongoose installation
npm i bcrypt  -- for bcrypt installation (Hash)
npm i jsonwebtoken -- for webtoken installation
npm i dotenv -- for dotenv installation
npm i express-async-handler -- for installation

## API Endpoints

server.js--api/users/userRoutes/userControllars

server.js--api/contacts/contactRoutes/contactControllars


### Create a new user

- **URL:** `/api/users/register`
- **Method:** `POST`
- **Request Body:** 
  - `name` (string): The name of the user.
  - `email` (string): The email address of the user.
  - `password` (string): The password for the user account.
- **Response:** 
  - `token` (string): JWT token for user authentication.

### Log in a user

- **URL:** `/api/users/login`
- **Method:** `POST`
- **Request Body:** 
  - `email` (string): The email address of the user.
  - `password` (string): The password for the user account.
- **Response:** 
  - `token` (string): JWT token for user authentication.

### Current user

- **URL:** `/api/users/current`
- **Method:** `POST`


### Create a new contact

- **URL:** `/api/contacts`
- **Method:** `POST`
- **Request Body:** 
  - `name` (string): The name of the contact.
  - `phone` (string): The phone number of the contact.
  - `email` (string): The email address of the contact.
- **Response:** 
  - `id` (string): The unique identifier of the created contact.
  - `name` (string): The name of the contact.
  - `phone` (string): The phone number of the contact.
  - `email` (string): The email address of the contact.

### Update a contact

- **URL:** `/api/contacts/:id`
- **Method:** `PUT`
- **Request Parameters:**
  - `id` (string): The unique identifier of the contact.
- **Request Body:** 
  - `name` (string): The updated name of the contact.
  - `phone` (string): The updated phone number of the contact.
  - `email` (string): The updated email address of the contact.
- **Response:** 
  - `id` (string): The unique identifier of the updated contact.
  - `name` (string): The updated name of the contact.
  - `phone` (string): The updated phone number of the contact.
  - `email` (string): The updated email address of the contact.

### Delete a contact

- **URL:** `/api/contacts/:id`
- **Method:** `DELETE`
- **Request Parameters:**
  - `id` (string): The unique identifier of the contact.
- **Response:** 
  - `message` (string): A success message indicating the contact was deleted.

### Get all contacts

- **URL:** `/api/contacts`
- **Method:** `GET`
- **Response:** 
  - Array of contacts with the following properties:
    - `id` (string): The unique identifier of the contact.
    - `name` (string): The name of the contact.
    - `phone` (string): The phone number of the contact.
    - `email` (string): The email address of the contact.

### Get contacts

- **URL:** `/api/contacts/:id`
- **Method:** `GET`
- **Response:** 
  - Array of contacts with the following properties:
    - `id` (string): The unique identifier of the contact.
    - `name` (string): The name of the contact.
    - `phone` (string): The phone number of the contact.
    - `email` (string): The email address of the contact.

## Authentication

JWT (JSON Web Token) authentication works by generating a token that contains user information, which is securely transmitted between parties. Here's a simplified explanation of the process:

User registers or logs in with their credentials.
Upon successful authentication, the server generates a JWT token.
The JWT token is issued to the client and stored locally (e.g., local storage or a cookie).
For subsequent requests, the client includes the JWT token in the request.
The server verifies the token's integrity and authenticity using a secret key.
If the token is valid and not expired, the server considers the user authenticated.
The server can extract user information from the token to authorize access to specific resources.
If the token expires, the client may need to obtain a new one through the authentication process.
JWT authentication eliminates the need for server-side sessions and allows for stateless authentication, providing a secure and scalable authentication mechanism for web applications.

## Configuration

### .env File

To run the project, you need to create a `.env` file in the root directory and include the following configuration variables:

```plaintext
PORT=50001
MONGODB_URI=mongodb://localhost:27017/your-database-name
SECRET_KEY=your-secret-key

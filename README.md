# Joke API

This is a simple Joke API built using Express.js. The API allows you to perform CRUD (Create, Read, Update, Delete) operations on jokes.

## Requirements

- Node.js
- npm (Node Package Manager)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/MercySpectures/JokesAPI.git
   ```
2. Navigate to the project directory:
   ```bash
   cd JokesAPI
   ```
3. Install the dependencies:
   ```bash
   npm install
   ```

## Usage

1. Start the server:
   ```bash
   node index.js
   ```
2. The server will be running on `http://localhost:3000`.

## API Endpoints

### 1. GET a random joke

- **URL:** `/random`
- **Method:** `GET`
- **Description:** Returns a random joke from the list.
- **Response:**
  ```json
  {
    "id": 1,
    "jokeText": "Why don't scientists trust atoms? Because they make up everything.",
    "jokeType": "Science"
  }
  ```

### 2. GET a specific joke

- **URL:** `/jokes/:id`
- **Method:** `GET`
- **Description:** Returns a specific joke by its ID.
- **Response:**
  ```json
  {
    "id": 1,
    "jokeText": "Why don't scientists trust atoms? Because they make up everything.",
    "jokeType": "Science"
  }
  ```

### 3. GET jokes by filtering on the joke type

- **URL:** `/filter?type=:type`
- **Method:** `GET`
- **Description:** Returns jokes that match the specified type.
- **Response:**
  ```json
  [
    {
      "id": 1,
      "jokeText": "Why don't scientists trust atoms? Because they make up everything.",
      "jokeType": "Science"
    },
    {
      "id": 6,
      "jokeText": "How do you organize a space party? You planet!",
      "jokeType": "Science"
    }
  ]
  ```

### 4. POST a new joke

- **URL:** `/jokes`
- **Method:** `POST`
- **Description:** Adds a new joke to the list.
- **Request Body:**
  ```json
  {
    "text": "Your new joke text here.",
    "type": "Joke type here."
  }
  ```
- **Response:**
  ```json
  {
    "id": 101,
    "jokeText": "Your new joke text here.",
    "jokeType": "Joke type here."
  }
  ```

### 5. PUT a joke

- **URL:** `/jokes/:id`
- **Method:** `PUT`
- **Description:** Updates an existing joke by its ID.
- **Request Body:**
  ```json
  {
    "text": "Updated joke text.",
    "type": "Updated joke type."
  }
  ```
- **Response:**
  ```json
  {
    "id": 1,
    "jokeText": "Updated joke text.",
    "jokeType": "Updated joke type."
  }
  ```

### 6. PATCH a joke

- **URL:** `/jokes/:id`
- **Method:** `PATCH`
- **Description:** Partially updates an existing joke by its ID.
- **Request Body:**
  ```json
  {
    "text": "Partially updated joke text.",
    "type": "Partially updated joke type."
  }
  ```
- **Response:**
  ```json
  {
    "id": 1,
    "jokeText": "Partially updated joke text.",
    "jokeType": "Partially updated joke type."
  }
  ```

### 7. DELETE a specific joke

- **URL:** `/jokes/:id`
- **Method:** `DELETE`
- **Description:** Deletes a specific joke by its ID.
- **Response:**
  - **Success:** `200 OK`
  - **Error:** `404 Not Found`

### 8. DELETE all jokes

- **URL:** `/all`
- **Method:** `DELETE`
- **Description:** Deletes all jokes if the correct master key is provided.
- **Request Query Parameter:**
  ```json
  {
    "key": "4VGP2DN-6EWM4SJ-N6FGRHV-Z3PR3TT"
  }
  ```
- **Response:**
  - **Success:** `200 OK`
  - **Error:** `404 Not Found`
  ```json
  {
    "error": "You are not authorized to perform this action."
  }
  ```

## Example Jokes

```json
[
  {
    "id": 1,
    "jokeText": "Why don't scientists trust atoms? Because they make up everything.",
    "jokeType": "Science"
  },
  {
    "id": 2,
    "jokeText": "Why did the scarecrow win an award? Because he was outstanding in his field.",
    "jokeType": "Puns"
  },
  {
    "id": 3,
    "jokeText": "I told my wife she was drawing her eyebrows too high. She looked surprised.",
    "jokeType": "Puns"
  },
  // ...more jokes
]
```

## License

This project is licensed under the MIT License.

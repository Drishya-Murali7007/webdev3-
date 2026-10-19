# Student Management REST API

Lab Assignment 2 — Web Dev III (Node.js & Express Backend), Unit 2.

This project implements the required student CRUD APIs using Express, an in-memory JavaScript array, modular routing, custom logger middleware, and status-code-based error handling. No database or Mongoose is used.

## Requirements
- Node.js and npm
- Postman (for testing)

## Setup
Open a terminal in this folder and run:

```bash
npm install
npm start
```

The API runs at `http://localhost:3000`.

## Project structure

```text
student-management-rest-api/
├── app.js
├── package.json
├── README.md
├── .gitignore
├── routes/
│   └── studentRoutes.js
├── middleware/
│   └── logger.js
└── data/
    └── students.js
```

## Student record format

```json
{
  "id": 1,
  "name": "Rahul",
  "course": "BCA"
}
```

Student records are stored in an in-memory array. Changes are lost when the server restarts, as required by the no-database restriction.

## Required API endpoints

Base URL: `http://localhost:3000`

| Method | Endpoint | Purpose | Success status |
|---|---|---|---|
| GET | `/students` | Get all students | 200 |
| GET | `/students/:id` | Get one student by ID | 200 |
| POST | `/students` | Create a student | 201 |
| PUT | `/students/:id` | Update a student's name and/or course | 200 |
| DELETE | `/students/:id` | Delete a student | 200 |

Invalid IDs return `400 Bad Request`; unknown student IDs return `404 Not Found`; invalid JSON returns `400 Bad Request`.

## Postman testing

Start the server before sending requests.

### 1. Get all students
- Method: `GET`
- URL: `http://localhost:3000/students`

### 2. Get one student
- Method: `GET`
- URL: `http://localhost:3000/students/1`

### 3. Create a student
- Method: `POST`
- URL: `http://localhost:3000/students`
- Body → raw → JSON:

```json
{
  "name": "Neha",
  "course": "BTech"
}
```

Expected status: `201 Created`.

### 4. Update a student
- Method: `PUT`
- URL: `http://localhost:3000/students/1`
- Body → raw → JSON:

```json
{
  "name": "Rahul Sharma",
  "course": "MCA"
}
```

Expected status: `200 OK`.

### 5. Delete a student
- Method: `DELETE`
- URL: `http://localhost:3000/students/1`

Expected status: `200 OK`.

## Example error tests
- `GET http://localhost:3000/students/999` → `404 Not Found`
- `POST http://localhost:3000/students` with `{ "name": "", "course": "BCA" }` → `400 Bad Request`
- `GET http://localhost:3000/students/abc` → `400 Bad Request`

## Notes
- `express.json()` parses JSON request bodies.
- `logger.js` logs the timestamp, HTTP method, and URL for each request.
- `studentRoutes.js` contains the CRUD routes and is mounted at `/students` by `app.js`.
- No database, Mongoose, or third-party middleware is used.

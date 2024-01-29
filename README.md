# Events Rest-API

## Quick Start

Install Dependencies using `go get`:

```sh
$ go get
```

Then run the API on Port:8080 :

```sh
$ go run .
```


## API Routes

### GET Requests

- **/api/events**
  - Description: Get a list of available events
  - Example Request:
    ```http
    GET http://localhost:8080/events
    ```
  - Example Response:
    ```json
    [
      {
        "id": 1,
        "name": "John Doe"
      },
      {
        "id": 2,
        "name": "Jane Smith"
      }
    ]
    ```

- **/api/events/&lt;id&gt;**
  - Description: Get an event by specific ID
  - Example Request:
    ```http
    GET http://localhost:8080/events/21
    ```
  - Example Response:
    ```json
    [
      {
        "id": 1,
        "name": "John Doe"
      },
      {
        "id": 2,
        "name": "Jane Smith"
      }
    ]
    ```

### POST Requests

- **/api/events**
  - Description: Create bookable event **(Auth Required)**
  - Example Request:
    ```http
    POST http://localhost:8080/events
    content-type: application/json
    authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InRlc3RAZXhhbXBsZS5jb20iLCJleHAiOjE2OTkyODQzNDMsInVzZXJJZCI6MX0.GtpnS_WUOoJQ7wtcBQ4nL1w9q1XKuloePjvEr4aZom8

    {
    "name": "Test event",
    "description": "Test event!!!",
    "location": "A test location",
    "dateTime": "2025-01-01T15:30:00.000Z"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```

- **/api/signup**
  - Description: Create a new user
  - Example Request:
    ```http
    POST http://localhost:8080/signup
    content-type: application/json

    {
    "email": "test2@example.com",
    "password": "test"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```

- **/api/login**
  - Description: Sign in and Authenticate user **(Returns Auth Token)**
  - Example Request:
    ```http
    POST http://localhost:8080/login
    content-type: application/json

    {
    "email": "test2@example.com",
    "password": "test"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```

- **/api/events/&lt;id&gt;/register**
  - Description: Register the user for an Event **(Auth Required)**
  - Example Request:
    ```http
    POST http://localhost:8080/events/1/register
    authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InRlc3QyQGV4YW1wbGUuY29tIiwiZXhwIjoxNjk5Mjg0NDUxLCJ1c2VySWQiOjJ9.zCjaAoFNnIBMbg8N8Hx4MS_KafwV5qkR4tc6YPlYQRg
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```


### PUT Requests

- **/api/events/&lt;id&gt;**
  - Description: Update an existing Event **(Auth Required) (Only by Creator)**
  - Example Request:
    ```http
    PUT http://localhost:8080/events/5
    content-type: application/json
    authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InRlc3QyQGV4YW1wbGUuY29tIiwiZXhwIjoxNjk5MjgyODAzLCJ1c2VySWQiOjJ9.0v3T0JovPLtzaDnQ6VwSaR2wyyaWnM-0jY5KjhbLgUs

    {
    "name": "Updated test event",
    "description": "A test event",
    "location": "Test location (Updated!)",
    "dateTime": "2025-01-01T15:30:00Z"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "Updated User"
    }
    ```

### DELETE Requests

- **/api/events/&lt;id&gt;**
  - Description: Delete an Event by ID **(Auth Required) (Only by Creator)**
  - Example Request:
    ```http
    DELETE http://localhost:8080/events/5
    authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InRlc3QyQGV4YW1wbGUuY29tIiwiZXhwIjoxNjk5MjgyOTI5LCJ1c2VySWQiOjJ9.7XsczbLX9dN2HocDsumtpQU6Rhvy_jbPTxL2YzbqCqA
    ```
  - Example Response:
    ```json
    {
      "message": "User deleted successfully"
    }
    ```
- **/api/events/&lt;id&gt;/register**
  - Description: Delete a registration for an Event **(Auth Required)**
  - Example Request:
    ```http
    DELETE http://localhost:8080/events/1/register
    authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InRlc3QyQGV4YW1wbGUuY29tIiwiZXhwIjoxNjk5Mjg0NDUxLCJ1c2VySWQiOjJ9.zCjaAoFNnIBMbg8N8Hx4MS_KafwV5qkR4tc6YPlYQRg
    ```
  - Example Response:
    ```json
    {
      "message": "User deleted successfully"
    }
    ```





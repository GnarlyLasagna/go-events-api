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

- **/events**
  - Description: 
  - Example Request:
    ```http
    GET /events
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

- **/events/<id>**
  - Description: 
  - Example Request:
    ```http
    GET /events
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

- **/events**
  - Description: 
  - Example Request:
    ```http
    POST /events
    Content-Type: application/json

    {
      "name": "New User"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```

- **/signup**
  - Description: 
  - Example Request:
    ```http
    POST /events
    Content-Type: application/json

    {
      "name": "New User"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```

- **/login**
  - Description: 
  - Example Request:
    ```http
    POST /events
    Content-Type: application/json

    {
      "name": "New User"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```

- **/events/<id>/register**
  - Description: 
  - Example Request:
    ```http
    POST /events
    Content-Type: application/json

    {
      "name": "New User"
    }
    ```
  - Example Response:
    ```json
    {
      "id": 3,
      "name": "New User"
    }
    ```


### PUT Requests

- **/events/<id>**
  - Description: Update an existing user.
  - Example Request:
    ```http
    PUT /events
    Content-Type: application/json

    {
      "name": "Updated User"
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

- **/events/<id>**
  - Description: 
  - Example Request:
    ```http
    DELETE /events
    ```
  - Example Response:
    ```json
    {
      "message": "User deleted successfully"
    }
    ```
- **/events/<id>/register**
  - Description: 
  - Example Request:
    ```http
    DELETE /events
    ```
  - Example Response:
    ```json
    {
      "message": "User deleted successfully"
    }
    ```





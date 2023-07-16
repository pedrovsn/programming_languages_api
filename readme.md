# Example REST API using Python and Flask

This is a simple example of a REST API built with Python and Flask. The API provides endpoints to perform CRUD (Create, Read, Update, Delete) operations on programming languages.

## Requirements

- Python 3.x
- Flask (Install using `pip install Flask`)

## Getting Started

1. Clone the repository:

```
git clone <repository_url>
cd <repository_name>
```

2. Install Flask:

```
pip install Flask
```

3. Run the Flask app:

```
python app.py
```

The server should start running on `http://127.0.0.1:5000/`.

## Endpoints

### List all programming languages

- **URL**: `/programming_languages`
- **Method**: GET
- **Description**: Retrieve a list of all programming languages.

### Create a programming language

- **URL**: `/programming_languages`
- **Method**: POST
- **Description**: Create a new programming language.

### Get a programming language

- **URL**: `/programming_languages/<lang_name>`
- **Method**: GET
- **Description**: Retrieve information about a specific programming language.

### Update a programming language

- **URL**: `/programming_languages/<lang_name>`
- **Method**: PUT
- **Description**: Update information for a specific programming language.

### Delete a programming language

- **URL**: `/programming_languages/<lang_name>`
- **Method**: DELETE
- **Description**: Delete a specific programming language.

## Request and Response Format

The API accepts JSON data for POST and PUT requests. The response will also be in JSON format.

### Sample Request (POST/PUT)

```json
{
  "name": "Python",
  "year_invented": 1991,
  "creator": "Guido van Rossum"
}
```

### Sample Response (GET)

```json
{
  "name": "Python",
  "year_invented": 1991,
  "creator": "Guido van Rossum"
}
```

### Sample Response (GET all)

```json
[
  {
    "name": "Python",
    "year_invented": 1991,
    "creator": "Guido van Rossum"
  },
  {
    "name": "JavaScript",
    "year_invented": 1995,
    "creator": "Brendan Eich"
  },
  ...
]
```

### Sample Response (DELETE)

```json
{
  "message": "Programming language deleted successfully."
}
```

## Error Handling

In case of errors, the API will return appropriate HTTP status codes and error messages in the response.

## Sample Usage

Here are some sample cURL commands to interact with the API:

### Create a programming language

```
curl -X POST -H "Content-Type: application/json" -d '{"name":"Java", "year_invented": 1995, "creator": "James Gosling"}' http://127.0.0.1:5000/programming_languages
```

### Get a programming language

```
curl http://127.0.0.1:5000/programming_languages/Java
```

### Update a programming language

```
curl -X PUT -H "Content-Type: application/json" -d '{"year_invented": 1996}' http://127.0.0.1:5000/programming_languages/Java
```

### Delete a programming language

```
curl -X DELETE http://127.0.0.1:5000/programming_languages/Java
```

## License

This project is licensed under the [MIT License](LICENSE). Feel free to modify and use it for your own projects.

---

Please note that this is a basic example for learning purposes and not intended for production use. In a real-world scenario, you would need to add proper error handling, input validation, authentication, and database integration to ensure security and reliability.
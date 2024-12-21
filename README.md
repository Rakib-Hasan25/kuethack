# Ingredients Management API

This API allows users to manage a collection of ingredients with their quantities. The API is built using Flask and MongoDB and includes the following features:

- Add a new ingredient
- Retrieve all ingredients
- Update an existing ingredient's quantity
- Delete an ingredient

## Prerequisites

- Python 3.7+
- MongoDB server
- Install dependencies:
  bash
  pip install flask pymongo pydantic
  

## Running the Application

1. Start your MongoDB server.
2. Run the Flask application:
   bash
   python app.py
   
3. The API will be available at http://localhost:5000.

## API Documentation

### 1. Add a New Ingredient
- *Route*: /ingredients
- *Method*: POST
- *Sample Payload*:
  json
  {
    "name": "Sugar",
    "quantity": 5
  }
  
- *Sample Response*:
  json
  {
    "message": "Ingredient added successfully"
  }
  
- *Error Responses*:
  json
  {
    "error": "Name and quantity are required"
  }
  
  json
  {
    "error": "Ingredient already exists"
  }
  

### 2. Retrieve All Ingredients
- *Route*: /ingredients
- *Method*: GET
- *Sample Response*:
  json
  [
    {
      "name": "Sugar",
      "quantity": 5
    },
    {
      "name": "Salt",
      "quantity": 2
    }
  ]
  

### 3. Update an Ingredient's Quantity
- *Route*: /ingredients/<name>
- *Method*: PUT
- *Sample Payload*:
  json
  {
    "quantity": 10
  }
  
- *Sample Response*:
  json
  {
    "message": "Ingredient updated successfully"
  }
  
- *Error Responses*:
  json
  {
    "error": "Quantity is required"
  }
  
  json
  {
    "error": "Ingredient not found"
  }
  

### 4. Delete an Ingredient
- *Route*: /ingredients/<name>
- *Method*: DELETE
- *Sample Response*:
  json
  {
    "message": "Ingredient deleted successfully"
  }
  
- *Error Response*:
  json
  {
    "error": "Ingredient not found"
  }
  

## Notes

- Make sure MongoDB is running before starting the application.
- The API validates payloads using Pydantic to ensure correct data structure.
- Replace localhost with your server IP or domain when deploying to production.

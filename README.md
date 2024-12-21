#Challange2

## Prerequisites
- Python 3.13.0 version
- MongoDB server

  
## Running the Application

1. Start your MongoDB server.
2. Run the Flask application:
   python app.py
   
3. The API will be available at http://localhost:5000.

# Ingredients Management API

This API allows users to manage a collection of ingredients with their quantities. The API is built using Flask and MongoDB and includes the following features:

- Add a new ingredient
- Retrieve all ingredients
- Update an existing ingredient's quantity
- Delete an ingredient


## API Documentation

### 1. Add a New Ingredient
- *Route*: /ingredients
- *Method*: POST
- *Sample Payload*:
  ```
  json
  {
    "name": "Sugar",
    "quantity": 5
  }
  ```
- *Sample Response*:
  ```
  json
  {
    "message": "Ingredient added successfully"
  }
  ```
- *Error Responses*:
  ```
  json
  {
    "error": "Name and quantity are required"
  }

  json
  {
    "error": "Ingredient already exists"
  }
  ```

### 2. Retrieve All Ingredients
- *Route*: /ingredients
- *Method*: GET
- *Sample Response*:
  json
   ```
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

#  Chatwithbot

This system manages recipes by parsing and storing recipe details, and integrates an LLM-based chatbot to recommend recipes based on user preferences and available ingredients.

- Install dependencies:
  flask, langchain,
  and also used openai api
  
## Features

### 1. Recipe Storage
- Parse and store recipe details from text not get time for image.
- Combine all recipes into a single my_fav_recipes.txt file.

### 2. Recipe Retrieval API
- Add new favorite recipes via image or text input.

### 3. Chatbot Integration
- Interact with users to understand preferences (e.g., "I want something sweet today").
- Recommend recipes based on user preferences and available ingredients.

## API Documentation

### 1. Add a New Recipe
- *Route*: /store-recipies-text
- *Method*: POST
- *Sample Payload* (Text):
  json
  
 {
 "recipe_title":"",
    "cuisine_type":"",
    "taste_profile":"",
    "review":"",
    "preparation_time":"",
   "ingredients":""
}
  
- *Sample Response*:
  json
 {"data":"successfully write this data"}
  

### 2. Chatbot Interaction
- *Route*: /chat-with-bot
- *Method*: POST
- *Sample Payload*:
  json
  {
    "query_text": "i want to eat some sweet suggest one"
  }
  
- *Sample Response*:
  json
{
  "data": "Here are some sweet dish suggestions along with their essential ingredients:\n\n1. **Creme Brulee (French, Sweet, 4.7/5, 35 minutes)**\n   - Cream\n   - Sugar\n   - Vanilla\n   - Egg yolks\n\n2. **Churros (Spanish, Sweet, 4.9/5, 20 minutes)**\n   - Flour\n   - Sugar\n   - Eggs\n   - Cinnamon\n   - Oil\n\n3. **Baklava (Turkish, Sweet, 4.7/5, 60 minutes)**\n   - Phyllo dough\n   - Nuts\n   - Honey\n   - Sugar\n   - Butter\n\n4. **Tiramisu (Italian, Sweet, 4.9/5, 45 minutes)**\n   - Mascarpone\n   - Coffee\n   - Ladyfingers\n   - Cocoa\n   - Sugar\n\n5. **Apple Pie (American, Sweet, 4.8/5, 70 minutes)**\n   - Apples\n   - Sugar\n   - Cinnamon\n   - Flour\n   - Butter\n\n6. **Panna Cotta (Italian, Sweet, 4.7/5, 20 minutes)**\n   - Cream\n   - Sugar\n   - Gelatin\n   - Vanilla\n   - Berries\n\nThese dishes are sure to satisfy your sweet cravings!"
}
  




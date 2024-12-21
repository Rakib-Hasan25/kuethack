# Recipe Management and Chatbot API

This system manages recipes by parsing and storing recipe details, and integrates an LLM-based chatbot to recommend recipes based on user preferences and available ingredients.

## Prerequisites

- Python 3.7+
- MongoDB server
- Install dependencies:
  bash
  pip install flask pymongo openai pytesseract
  
- For OCR functionality, ensure Tesseract is installed on your system.
- Set up an OpenAI API key or another LLM provider.

## Features

### 1. Recipe Storage
- Parse and store recipe details from images or text.
- Combine all recipes into a single my_fav_recipes.txt file.

### 2. Recipe Retrieval API
- Add new favorite recipes via image or text input.

### 3. Chatbot Integration
- Interact with users to understand preferences (e.g., "I want something sweet today").
- Recommend recipes based on user preferences and available ingredients.

## API Documentation

### 1. Add a New Recipe
- *Route*: /recipes
- *Method*: POST
- *Sample Payload* (Text):
  json
  {
    "recipe_type": "text",
    "content": "Chocolate Cake Recipe: Ingredients - flour, sugar, cocoa powder, butter. Instructions - Mix, bake at 350F for 30 mins."
  }
  
- *Sample Payload* (Image):
  json
  {
    "recipe_type": "image",
    "image_path": "path/to/recipe_image.jpg"
  }
  
- *Sample Response*:
  json
  {
    "message": "Recipe added successfully"
  }
  
- *Error Response*:
  json
  {
    "error": "Invalid recipe type or content"
  }
  

### 2. Chatbot Interaction
- *Route*: /chatbot
- *Method*: POST
- *Sample Payload*:
  json
  {
    "user_input": "I want something sweet today"
  }
  
- *Sample Response*:
  json
  {
    "recommendation": "Based on your preferences and available ingredients, try the Chocolate Cake recipe."
  }
  
- *Error Response*:
  json
  {
    "error": "Unable to process the request. Please try again."
  }
  

## Notes

- For OCR, ensure that Tesseract is installed and accessible.
- The chatbot processes my_fav_recipes.txt to recommend recipes.
- Update the my_fav_recipes.txt file automatically when new recipes are added.
- Replace localhost with your server IP or domain when deploying to production.
- Set your OpenAI API key as an environment variable or update the LLM configuration in the code.

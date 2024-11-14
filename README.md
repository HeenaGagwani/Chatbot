# Movie Chatbot with Neo4j and Langchain

## Overview

This project is a **Movie Chatbot** powered by **Neo4j**, **Langchain**, and **OpenAI's GPT-3**. It allows users to interact with a dynamic, conversational chatbot capable of providing detailed information about movies, including their plots, actors, directors, and more. The chatbot leverages vector-based search for semantic understanding of movie plots, as well as Cypher queries for exact match retrievals from the Neo4j graph database.

The chatbot provides an intuitive interface built with **Streamlit** and utilizes Langchain to manage LLM (Large Language Models) and interactions with the Neo4j database.

## Features

- **Conversational Interface**: Interact with a chatbot that can answer questions about movies, actors, and directors.
- **Semantic Search**: Powered by vector embeddings of movie plots for context-based search.
- **Exact Match Queries**: Use Cypher queries for precise results on movie titles, actors, and directors.
- **Multi-tool Support**: The chatbot can handle different types of queries using tools like the movie plot search and general chat functionalities.
- **Session History**: Maintains a conversation history, allowing users to ask follow-up questions.

## Project Setup

### Prerequisites

- **Neo4j**: Ensure you have a Neo4j instance running and access to your database credentials.
- **OpenAI API Key**: Required to use GPT-3 for the conversational agent.
- **Python 3.8+**: Required for running the project.

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/movie-chatbot.git
   cd movie-chatbot
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up your **Neo4j** instance with the necessary credentials (URI, username, password) and **OpenAI API** key. Add these values to the `.streamlit/secrets.toml` file:
   ```toml
   [neo4j]
   NEO4J_URI = "your_neo4j_uri"
   NEO4J_USERNAME = "your_neo4j_username"
   NEO4J_PASSWORD = "your_neo4j_password"

   [openai]
   OPENAI_API_KEY = "your_openai_api_key"
   OPENAI_MODEL = "gpt-3.5-turbo"
   ```

4. Start your **Neo4j** database and make sure it contains the movie data with embeddings of the movie plots and related properties.

### Running the Application

To launch the application, simply run the following command:

```bash
streamlit run bot.py
```

This will start the Streamlit interface in your browser, where you can interact with the chatbot.

## How It Works

1. **Streamlit Frontend**: The frontend is built using Streamlit, which provides a simple and interactive UI for users to input their queries.
2. **LLM Integration**: The **ChatOpenAI** class from Langchain is used to interact with OpenAI's GPT-3 model, generating responses to user queries.
3. **Neo4j Integration**: The **Neo4jGraph** class is used to interface with the Neo4j database, and **Neo4jVector** is used for vector search, allowing the chatbot to perform semantic search based on movie plot embeddings.
4. **Cypher Queries**: Exact match Cypher queries are used to search for movies, actors, or directors based on user input.

### Available Tools

1. **General Chat**: For answering general movie-related questions.
2. **Movie Plot Search**: For searching movies by plot or finding related movies based on a given plot description.

### Example Usage

1. **User**: "Tell me about the movie Inception."
2. **Chatbot**: "Inception is a science fiction action movie directed by Christopher Nolan. It stars Leonardo DiCaprio as Dom Cobb, a thief who specializes in entering people's dreams and stealing their secrets..."

3. **User**: "Who directed Inception?"
4. **Chatbot**: "Inception was directed by Christopher Nolan."

This README provides a comprehensive overview of the Movie Chatbot project, explaining its setup, usage, and future improvements.

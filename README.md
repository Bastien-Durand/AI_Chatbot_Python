# AI-Powered Assistant

An interactive chat application that leverages Streamlit for the UI and OpenAI's GPT-3.5 for generating conversational AI responses. It features a persistent chat history using shelve, allowing users to pick up where they left off or start fresh by clearing the history.

## Overview

This application offers a simple and intuitive interface for users to engage in conversation with an AI. Utilizing OpenAI's powerful GPT-3.5 model, it can understand and respond to a wide range of queries and topics. Chat history is saved locally, ensuring that users can return to their previous conversations at any time.

## Setup

### Dependencies

- `openai`: For accessing OpenAI's API.
- `streamlit`: To create the web app interface.
- `python-dotenv`: For loading environment variables.
- `shelve`: For persistent storage of chat history.

### Environment Variables

Create a `.env` file in the root directory and add your OpenAI API key:

```
OPENAI_API_KEY=your_api_key_here
```

### Installation

Ensure Python is installed on your system, then run the following command to install the required packages:

```sh
pip install openai streamlit python-dotenv
```

## Application Structure

### Initializing the Application

The application is initialized with Streamlit, setting up the title and loading the OpenAI API key from the environment variables. It also ensures the session state includes the selected OpenAI model and initializes or loads the chat history.

```python
from openai import OpenAI
import streamlit as st
from dotenv import load_dotenv
import os
import shelve

load_dotenv()

st.title("AI-Powered Assistant")
```

### Managing Chat History

Functions `load_chat_history` and `save_chat_history` manage the retrieval and updating of chat history stored in a local shelve file. This allows for persistence across sessions.

### User Interface

The UI includes a main chat interface where users can enter their queries and view the conversation. Users can also delete the chat history through an option in the sidebar, providing a fresh start whenever needed.

### Processing and Responding to User Input

Upon receiving a user query, the application appends it to the session's message list and sends it to the OpenAI API. The response is then displayed in the chat interface, simulating a real-time conversation with an AI.

## Running the Application

To run the app, navigate to the project directory in your terminal and execute:

```sh
streamlit run your_script_name.py
```

Replace `your_script_name.py` with the actual name of your Python script.

## Contributing

Contributions to this project are welcome. Please fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

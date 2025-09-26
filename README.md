# Three End-to-End Agentic AI Chatbots

This project showcases three distinct agentic AI chatbots, each built with `langgraph` to demonstrate different levels of complexity and capabilities, all powered by Groq's fast language models and presented with a Streamlit user interface.

## What is this Project?

This application serves as a demonstration of how to create versatile AI chatbots using an "agentic" approach. This means the AI doesn't just respond directly, but can think, decide, and use external tools to achieve its goals.

## Chatbot Types / Features

The project includes three main chatbot functionalities, selectable from the Streamlit UI:

1.  **Basic Chatbot**: A fundamental conversational AI that provides direct responses based on its language model capabilities.
2.  **Chatbot With Web**: An enhanced chatbot that can perform web searches using the Tavily API to find and incorporate up-to-date information into its responses, making it more informative.
3.  **AI News**: A specialized agent that fetches the latest Artificial Intelligence (AI) news from the web and summarizes it for you, categorized by timeframes like daily, weekly, or monthly.

## Key Technologies Used

  * **LangChain**: A framework for developing applications powered by language models.
  * **LangGraph**: Used for building stateful, multi-step agentic workflows and managing the conversation flow.
  * **Groq**: Provides fast and scalable inference for the Large Language Models (LLMs) used in the chatbots.
  * **Streamlit**: For creating an interactive and user-friendly web interface for the chatbots.
  * **Tavily**: A search API used by the "Chatbot With Web" and "AI News" agents to fetch real-time information from the internet.
  * **uv**: A modern and fast Python package installer and dependency manager.

## Project Structure

  * `app.py`: The main entry point to launch the Streamlit application.
  * `src/langgraphagenticai/`: Contains the core logic for the chatbots.
      * `LLMS/groqllm.py`: Manages the initialization and configuration of the Groq LLM.
      * `graph/graph_builder.py`: Defines the `langgraph` workflows (graphs) for each of the three chatbot types, outlining their steps and decision-making logic.
      * `nodes/`: Contains the individual processing units (nodes) for each chatbot's workflow:
          * `basic_chatbot_node.py`: Implements the core logic for the basic chatbot.
          * `chatbot_with_Tool_node.py`: Adds logic for integrating external tools (like web search) into the chatbot.
          * `ai_news_node.py`: Contains the logic for fetching, summarizing, and saving AI news.
      * `state/state.py`: Defines the shared data structure (`State`) that passes information between different steps in the `langgraph` workflows.
      * `tools/search_tool.py`: Provides the implementation for the web search tool using Tavily.
      * `ui/`: Contains files related to the Streamlit user interface.
          * `uiconfigfile.ini`: Configuration file for UI options (LLM, use cases, models).
          * `streamlitui/loadui.py`: Handles loading and displaying the Streamlit UI components.
          * `streamlitui/display_result.py`: Manages how the results and chatbot messages are displayed on the Streamlit UI.
  * `requirements.txt`: Lists all necessary Python dependencies for the project.
  * `uv.lock`: Specifies exact versions of dependencies for reproducible installations.
  * `README.md`: This file, providing an overview of the project.

## Setup and Installation

1.  **Clone the Repository:**

    ```bash
    # Assuming you are in the directory containing "Dhiraj1312" folder
    # If not, adjust path accordingly.
    git clone <repository_url> # Replace with actual repository URL if available
    ```

2.  **Set up Python Environment:**
    Ensure you have Python 3.13 installed. `uv` is used for efficient dependency management.

    ```bash
    # Install uv if you don't have it
    pip install uv

    # Create a new virtual environment
    uv venv

    # Activate the virtual environment
    # On macOS/Linux:
    source .venv/bin/activate
    # On Windows:
    .venv\Scripts\activate
    ```

3.  **Install Dependencies:**

    ```bash
    uv pip install -r requirements.txt
    ```

4.  **Configure API Keys:**
    Create a `.env` file in the root directory of this specific project and add your API keys:

    ```
    GROQ_API_KEY="YOUR_GROQ_API_KEY"
    TAVILY_API_KEY="YOUR_TAVILY_API_KEY"
    ```

    *Replace `"YOUR_GROQ_API_KEY"` and `"YOUR_TAVILY_API_KEY"` with your actual API keys. You can get a Groq API key from [Groq Console](https://console.groq.com/keys) and a Tavily API key from [Tavily Dashboard](https://app.tavily.com/home).*

## How to Run

1.  **Launch the Streamlit Application:**
    From the root directory of the project, run:

    ```bash
    streamlit run app.py
    ```

    This will open the Streamlit application in your web browser.

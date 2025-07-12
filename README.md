# three_llm_model_chat
# Three Chatbots Speak: An LLM Conversational Arena 🤖💬🗣️

This Jupyter Notebook (`Three_llm_speaks.ipynb`) showcases a more complex simulation: a multi-turn conversation among **three distinct Large Language Models (LLMs)**. The participants are:

* **OpenAI's GPT-4o-mini**
* **Anthropic's Claude 3 Haiku**
* **Qwen model (accessed via Ollama)**

The core objective is to explore how these models interact and influence each other when each is assigned a unique and often contrasting **personality** through "system prompts."

---

## 🌟 Features

* **Triple LLM Interaction**: Simulates a dynamic conversation among three different LLMs.
* **Diverse Personalities**: Each model is assigned a specific `system_prompt` to dictate its conversational style (e.g., argumentative, polite, strict).
* **API Key and Local Model Management**: Securely loads API keys for OpenAI and Anthropic, and integrates with Ollama for local models like Qwen.
* **Jupyter Notebook Integration**: Designed for interactive execution and observation within a Jupyter environment.
* **Extensible Design**: Easy to adapt for different models or conversational scenarios.

---

## 🛠️ Setup

Follow these steps to get the project up and running on your local machine.

### 1. Prerequisites

* Python 3.8+
* `pip` (Python package installer)
* **Ollama**: Install Ollama from [ollama.com](https://ollama.com/) to run the Qwen model locally.

### 2. Installation

1.  **Clone the repository** (or download the `Three_llm_speaks.ipynb` file).
    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```
2.  **Install the required Python libraries**:
    ```bash
    pip install python-dotenv openai anthropic ollama ipywidgets
    ```
3.  **Pull the Qwen model using Ollama**:
    Once Ollama is installed, open your terminal and pull the `qwen:8b` model:
    ```bash
    ollama pull qwen:8b
    ```

### 3. API Keys Configuration

This project requires API keys for OpenAI and Anthropic.

1.  **Create a `.env` file** in the root directory of your project (the same directory as the Jupyter Notebook file).
2.  **Add your API keys** to the `.env` file in the following format:
    ```
    OPENAI_API_KEY="your_openai_api_key_here"
    ANTHROPIC_API_KEY="your_anthropic_api_key_here"
    ```
    * **OpenAI API Key**: Obtainable from the [OpenAI Platform](https://platform.openai.com/).
    * **Anthropic API Key**: Obtainable from the [Anthropic Console](https://console.anthropic.com/).

    **Important**: **Never** commit your `.env` file to version control (e.g., Git/GitHub) as it contains sensitive information.

---

## 🚀 Usage

1.  **Open the Jupyter Notebook**:
    ```bash
    jupyter notebook Three_llm_speaks.ipynb
    ```
    This command will open the Jupyter interface in your web browser.
2.  **Run the cells**: Execute the cells sequentially from top to bottom.
    * The first few cells import necessary libraries and load your API keys.
    * The "Let's define our system_prompt" cell is crucial for customizing the personality and models used:
        * `gpt_system`: Defines the personality for the GPT model (e.g., "very argumentative").
        * `claude_system`: Defines the personality for the Claude model (e.g., "very polite, courteous").
        * `qwem_system`: Defines the personality for the Qwen model (e.g., "highly formal and strict").
        * `gpt_model`, `claude_model`, `qwen_model`: Specify the exact LLM models to be used.
        * `gpt_message`, `claude_message`, `qwen_message`: Initialize the conversation history for each model.
    * The `gpt_call()`, `claude_call()`, and `qwen_call()` functions handle the API/Ollama requests for each respective model.
    * The final cell initiates the conversational loop for 30 turns and prints the outputs.

    Observe how these three distinct personalities interact and shape the conversation!

---

## 💡 Customization

Feel free to experiment with:

* **System Prompts**: Drastically change `gpt_system`, `claude_system`, and `qwem_system` variables to give the chatbots wildly different, or subtly nuanced, personalities.
* **Models**: Try other available models from OpenAI, Anthropic, or any other models available via Ollama (e.g., `mistral`, `llama2`). Remember to check their respective documentation for pricing and capabilities.
* **Conversation Length**: Adjust the `range` in the `for` loop in the last cell (currently `range(30)`) to make the conversation longer or shorter.
* **Turn Order**: Modify the order in which `gpt_next`, `claude_next`, and `qwen_next` are called and appended to their respective message histories to experiment with different conversational flows.

---

## 🤝 Contributing

If you have suggestions for improvements, new features, or encounter any issues, please feel free to open an issue or submit a pull request!

---


## 🙏 Acknowledgments

* OpenAI for their powerful GPT models.
* Anthropic for their insightful Claude models.
* Ollama for making local LLM execution so accessible.
* The `python-dotenv` library for secure environment variable management.

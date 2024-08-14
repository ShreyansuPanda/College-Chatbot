# College Information ChatBot

A chatbot application built with Python, Flask for the web interface, and PyTorch for the AI model. This chatbot is designed to provide information about a college, including courses, contact details, and admission procedures. It utilizes a neural network model to understand and respond to user queries.

## Features

- Answer questions about the college, including available courses, contact details, and admission procedures.
- Provide responses to greetings, farewells, and other common conversational phrases.
- Simple, web-based user interface using Flask.
- Customizable intents and responses to suit different use cases.

## Requirements

- Python
- Flask
- PyTorch
- NLTK

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/college-chatbot.git
    cd college-chatbot
    ```

2. Install required packages:
    ```sh
    pip install -r requirements.txt
    ```

3. Download NLTK dependencies:
    ```python
    import nltk
    nltk.download('punkt')
    ```

## Usage

1. Train the model:
    ```sh
    python train.py
    ```

    This will generate a `data.pth` file containing the trained model parameters.

2. Run the web application:
    ```sh
    python app.py
    ```

    The application will be accessible at `http://127.0.0.1:5000/`.

## Code Structure

- `app.py`: Main Flask application that serves the chatbot interface and handles API requests.
- `chat.py`: Contains the logic for generating responses using the trained neural network model.
- `intents.json`: Defines the intents, patterns, and responses used for training the chatbot.
- `model.py`: Defines the neural network architecture used for the chatbot.
- `nltk_utils.py`: Utility functions for natural language processing, including tokenization and bag-of-words implementation.
- `train.py`: Script to train the neural network model using the intents defined in `intents.json`.
- `templates/base.html`: HTML template for the web interface.

## Database Schema

The chatbot does not use a traditional database but rather a JSON-based schema defined in `intents.json`. The JSON file contains the following structure:

- `intents`: List of intent objects, where each intent has:
    - `tag`: A label for the intent.
    - `patterns`: A list of possible user inputs for this intent.
    - `responses`: A list of potential responses the bot can give for this intent.

## Functions

### `app.py`

- `index_get()`: Renders the main HTML page for the chatbot.
- `predict()`: Handles incoming chat messages, passes them to the model, and returns a response.

### `chat.py`

- `get_response(msg)`: Takes a user message as input, processes it with the neural network model, and returns an appropriate response.

### `train.py`

- `ChatDataset()`: A custom PyTorch dataset class for loading and processing the training data.
- `__init__()`: Initializes and loads the training data.
- `train_loader()`: Loads the data in batches for training the model.
- `NeuralNet()`: Defines the architecture of the neural network used for classification.
- `train()`: Trains the neural network model using the processed data and saves the trained model to `data.pth`.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

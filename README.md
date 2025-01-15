# Seq2Seq-Chatbot

This repository contains a Python script for an interactive chatbot using the FLAN-T5 model from Google. The chatbot maintains a conversation history, allowing it to generate context-aware responses based on previous interactions.

## Features

- Uses the `transformers` library by Hugging Face.
- Implements Google’s FLAN-T5 large model for sequence-to-sequence language generation.
- Maintains a dynamic conversation history for more natural and context-aware conversations.

## Requirements

To run this script, install the following dependencies:

- `transformers`

Install the library via pip:

```bash
pip install transformers
```

## Usage

1. Clone the repository:

```bash
git clone https://github.com/your-username/seq2seq-chatbot.git
cd seq2seq-chatbot
```

2. Run the script:

```bash
python chatbot.py
```

3. Start interacting with the chatbot by typing your messages after the `>` prompt.

## How It Works

1. **Model and Tokenizer Initialization**: The script loads the pre-trained FLAN-T5 large model and its corresponding tokenizer.

2. **Conversation Management**: A `conversation_history` list is used to keep track of previous messages and responses.

3. **Dynamic Input Construction**:
   - The conversation history is concatenated into a single string.
   - User input is tokenized along with the conversation history for context-aware generation.

4. **Response Generation**:
   - The model generates a response based on the provided input and history.
   - The response is decoded and printed to the console.

5. **Iterative Interaction**:
   - Each user input and model response is appended to the `conversation_history` list to ensure context continuity.

## Example Interaction

```
> Hello!
Hi! How can I assist you today?
> Tell me a joke.
Why don't scientists trust atoms? Because they make up everything!
```

## Customization

- **Model Selection**: Change `model_name` to load a different model from the Hugging Face Model Hub:

```python
model_name = "facebook/blenderbot-400M-distill"
```

- **Response Length**: Adjust the maximum response length by passing the `max_length` parameter to the `generate` method:

```python
outputs = model.generate(**inputs, max_length=100)
```

## Limitations

- The chatbot may produce irrelevant or repetitive responses in some cases.
- Context length is limited by the model's maximum token capacity.

## Acknowledgments

- [Hugging Face](https://huggingface.co/) for providing the `transformers` library and pre-trained models.
- Google for the FLAN-T5 model.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.


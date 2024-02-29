# Transcript Summarization App

This flask app provides an interface for summarizing meeting transcripts using pretrained language models.

## Instructions
To run the app locally:

1. Ensure you have Python 3.7+ and Flask installed
2. Clone this repo
3. Run pip install requirements.txt
4. Update index.html to include your Azure OpenAI deployment names in the model list
```
    <option value="gpt-4-turbo-deployment">gpt-4-turbo</option>
    <option value="gpt-4-deployment">gpt-4</option>
    <option value="gpt-35-turbo-deployment">gpt-3.5-turbo</option>
```
5. Include the api info in your environment variables or create a .env file that includes them. See .env.example for an example.
6. Run `python MSA.py`
7. Visit http://127.0.0.1:5000 in your browser

The app accepts .vtt video transcripts for summarization, but can also take raw text input or .txt files. 

## Usage

Create a config.py and supply your OpenAI and Anthropic API keys.

On the home page, you can either upload a .vtt transcript file, enter raw text, or paste the contents of a .txt file. 

In the "Model Selection" dropdown, choose between you Azure OpenAI deployments.

Click "Summarize" to generate a bulleted summary of the meeting discussion points using the selected model.

You can then download the summary as a .txt file or edit it on the page and re-summarize.

## Overview
This app provides a wrapper around a meeting transcript summarizer. It uses a token splitter to chunk long input texts and employs batch inference to efficiently summarize each chunk with the selected language model.

The summarizer aims to capture the essence of meeting discussions in a concise yet comprehensive bulleted list format.

## Installation

### Create an environment
Whatever you prefer (e.g. `conda` or `venv`)
```console
mkdir myproject
$ cd myproject
$ python3 -m venv venv
```

### Activate it
Windows:
```console
venv\Scripts\activate
```
### Install PyTorch and dependencies

For Installation of PyTorch see [official website](https://pytorch.org/).

You also need `nltk`,`numpy`,`torch`:
 ```console
pip install nltk
pip install numpy
pip install torch
 ```

If you get an error during the first run, you also need to install `nltk.tokenize.punkt`:
Run this once in your terminal:
 ```console
$ python
>>> import nltk
>>> nltk.download('punkt')
```

## Usage
Run
```console
python train.py
```
This will dump `data.pth` file. And then run
```console
python chat.py
```
## Customize
Have a look at [intents.json](intents.json). You can customize it according to your own use case. Just define a new `tag`, possible `patterns`, and possible `responses` for the chat bot. You have to re-run the training whenever this file is modified.
```console
{
  "intents": [
    {
      "tag": "greeting",
      "patterns": [
        "Hi",
        "Hello",
        "Good morning",
        "Good evening"
      ],
      "responses": [
        "Hello! Welcome to our restaurant. How can I assist you today?",
        "Hi there! Looking to make a reservation or do you have questions?"
      ]
    },
    {
      "tag": "make_reservation",
      "patterns": [
        "I want to book a table",
        "Can I make a reservation for dinner?",
        "I'd like to reserve a table",
        "Book a table"
      ],
      "responses": [
        "Sure! For how many people and when would you like to reserve?",
        "Absolutely, I can help with that. What date and time are you looking at?"
      ]
    },
    ...
  ]
}
```

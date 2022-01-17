# AsNER

This repository contains pre-trained model for Assamese NER based on BiLSTM-CRF architecture
## How to run

Download the pre-trained model from the link- https://drive.google.com/file/d/1sqBxuujk9yOPcXkQTvONgQlP93qt0EJD/view?usp=sharing

```
from flair.models import SequenceTagger
from flair.data import  Sentence, Token

# Load the tagger

model = SequenceTagger.load('AsFlair.pt')

#  create example sentence
sen='দিল্লী ভাৰতৰ ৰাজধানী ।'
sentence = Sentence(sen)

# predict tags and print
model.predict(sentence)
print(sentence.to_tagged_string())

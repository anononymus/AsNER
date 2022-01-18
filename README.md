# AsNER

## Annotated Assamese NER dataset 

Dataset has been splitted into three parts- train, dev and test which is available in the name of train.txt, dev.txt and test.txt.

This repository contains pre-trained model for Assamese NER based on BiLSTM-CRF architecture using MuRIL embeddings. The F1-score acuracy of this model is 79.3%
## How to run

Download the pre-trained model from the link- https://drive.google.com/file/d/1sqBxuujk9yOPcXkQTvONgQlP93qt0EJD/view?usp=sharing

```
from flair.models import SequenceTagger
from flair.data import  Sentence, Token

# Load the tagger

model = SequenceTagger.load('AsNER.pt')

#  create example sentence
sen='দিল্লী ভাৰতৰ ৰাজধানী ।'
sentence = Sentence(sen)

# predict tags and print
model.predict(sentence)
print(sentence.to_tagged_string())




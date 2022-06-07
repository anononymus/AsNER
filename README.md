# AsNER

This repository contains pre-trained model as well as dataset for Assamese NER. The model is trained using BiLSTM-CRF architecture with MuRIL embeddings. The F1-score acuracy of this model is 80.69%

## Annotated Assamese NER dataset 

Dataset has been splitted into three parts- train, dev and test which is available in the name of train.txt, dev.txt and test.txt.

## Requirements

* It requires python 3.6+
* Install [Flair](https://github.com/flairNLP/flair) preferably  in in favorite virtual environment, 


## How to run

Download the pre-trained model from the link- [AsNER](https://drive.google.com/file/d/1sqBxuujk9yOPcXkQTvONgQlP93qt0EJD/view?usp=sharing)

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
দিল্লী <LOC> ভাৰতৰ <LOC> ৰাজধানী ।
```



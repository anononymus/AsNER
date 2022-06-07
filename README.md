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
sen1='দিল্লী ভাৰতৰ ৰাজধানী ।'
sentence1 = Sentence(sen1)

# predict tags and print
model.predict(sentence1)
print(sentence1.to_tagged_string())
দিল্লী <LOC> ভাৰতৰ <LOC> ৰাজধানী ।

sen2='বিশ্ববিদ্যালয়খন গুৱাহাটী মহানগৰীৰ জালুকবাৰী অঞ্চলত অৱস্থিত ।'
sentence2 = Sentence(sen2)

# predict tags and print
model.predict(sentence2)  
print(sentence2.to_tagged_string())
বিশ্ববিদ্যালয়খন <MISC> গুৱাহাটী <LOC> মহানগৰীৰ <LOC> জালুকবাৰী <LOC> অঞ্চলত <LOC> অৱস্থিত ।


sen3='গুৱাহাটী বিশ্ববিদ্যালয় গুৱাহাটী মহানগৰীৰ জালুকবাৰীত অৱস্থিত ।'
sentence3 = Sentence(sen3)
# predict tags and print

model.predict(sentence3)
print(sentence3.to_tagged_string())
গুৱাহাটী <ORG> বিশ্ববিদ্যালয় <ORG> গুৱাহাটী <LOC> মহানগৰীৰ <LOC> জালুকবাৰীত <LOC> অৱস্থিত ।

```



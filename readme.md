# Building-for-Tomorrow


**RQ1 PLMs **

_static representaions_

- Google W2V
!wget -c "https://s3.amazonaws.com/dl4j-distribution/GoogleNews-vectors-negative300.bin.gz"
!gzip -d GoogleNews-vectors-negative300.bin.gz

- FastText
!wget https://dl.fbaipublicfiles.com/fasttext/vectors-wiki/wiki.en.zip
!unzip wiki.en.zip

- Glove
!wget https://zenodo.org/record/3237458/files/glove.twitter.27B.200d.txt.gz
!gzip -d glove.twitter.27B.200d.txt.gz

_contextual representaions_

Implemented using huggingface + Tensorflow

from transformers import TFAutoModel as CWRModel
from transformers import AutoTokenizer as CWRTokenizer

model_choices = ['bert-base-uncased', 'gpt2' ,'roberta-base']
model_inx = 0 or 1 or 2

CWR = CWRModel.from_pretrained(model_choices[model_inx], output_hidden_states=True)
tokenizer = CWRTokenizer.from_pretrained(model_choices[model_inx])

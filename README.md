# Building-for-Tomorrow


## datasets clearning 

Cleaning
- GESD

import string
import re
printable = set(string.printable)
def collect_hashtags(string):
    return re.findall(r'\B#\w*[a-zA-Z]+\w*', string)
def clean_text(x):
    x = str(x)
    for hash in collect_hashtags(x):
        x = x.replace(hash, ' ')
    x = ''.join(filter(lambda s: s in printable, x))
    x = ' '.join(x.split())
    return x.lower()

for more check: https://github.com/OpinionChange2021/opinion_are_made_to_be_changed

- TESA

evidance removed, check this: https://github.com/AkaneNyan/distant-supervision-tweets

- ABRR

def review_clean_text(text):
    text = str(text)
    return text.lower()
    
    
# static-embedding based models clearning 

- Google W2V

def _get_mispell(mispell_dict):
    mispell_re = re.compile('(%s)' % '|'.join(mispell_dict.keys()))
    return mispell_dict, mispell_re

mispell_dict = {'colour':'color',
                'centre':'center',
                'didnt':'did not',
                'doesnt':'does not',
                'isnt':'is not',
                'shouldnt':'should not',
                'favourite':'favorite',
                'travelling':'traveling',
                'counselling':'counseling',
                'theatre':'theater',
                'cancelled':'canceled',
                'labour':'labor',
                'organisation':'organization',
                'wwii':'world war 2',
                'citicise':'criticize',
                'instagram': 'social medium',
                'whatsapp': 'social medium',
                'snapchat': 'social medium'

                }
mispellings, mispellings_re = _get_mispell(mispell_dict)

def replace_typical_misspell(text):
    def replace(match):
        return mispellings[match.group(0)]
    return mispellings_re.sub(replace, text)
    
def w2v_clean_text(x):
    x = str(x)
    for punct in "/-'":
        x = x.replace(punct, ' ')
    for punct in '&':
        x = x.replace(punct, f' {punct} ')
    for punct in '?!.,"#$%\'()*+-/:;<=>@[\\]^_`{|}~' + '“”’':
        x = x.replace(punct, '')

    x = re.sub('[0-9]{5,}', '#####', x)
    x = re.sub('[0-9]{4}', '####', x)
    x = re.sub('[0-9]{3}', '###', x)
    x = re.sub('[0-9]{2}', '##', x)

    x = replace_typical_misspell(x)

    to_remove = ['a', 'to', 'of', 'and']
    sentences = ' '.join(word for word in x.split() if not word in to_remove)

    return sentences
    
 - Glove
 
 def glove_tokenize(text):
    # Different regex parts for smiley faces
    eyes = r"[8:=;]"
    nose = r"['`\-]?"

    # function so code less repetitive
    def re_sub(pattern, repl):
        return re.sub(pattern, repl, text, flags=FLAGS)

    text = re_sub(r"https?:\/\/\S+\b|www\.(\w+\.)+\S*", "")
    text = re_sub(r"@\w+", "")
    text = re_sub(r"{}{}[)dD]+|[)dD]+{}{}".format(eyes, nose, nose, eyes), "")
    text = re_sub(r"{}{}p+".format(eyes, nose), "")
    text = re_sub(r"{}{}\(+|\)+{}{}".format(eyes, nose, nose, eyes), "")
    text = re_sub(r"{}{}[\/|l*]".format(eyes, nose), "")
    text = re_sub(r"/", " / ")
    text = re_sub(r"<3", "<heart>")
    text = re_sub(r"[-+]?[.\d]*[\d]+[:,.\d]*", "")
    text = re_sub(r"#\w+", '')  # amackcrane edit
    text = re_sub(r"([!?.]){2,}", r"")
    text = re_sub(r"\b(\S*?)(.)\2{2,}\b", r"")
    text = re_sub(r"([a-zA-Z<>()])([?!.:;,])", r"")
    text = re_sub(r"\(([a-zA-Z<>]+)\)", r"")
    text = re_sub(r"  ", r" ")
    text = re_sub(r" ([A-Z]){2,} ", allcaps)

    return text.lower()
  
- Fasttext

from nltk.tokenize import TweetTokenizer
tknzr = TweetTokenizer()

def fasttext_clean(text):
    text = ' '.join(tknzr.tokenize(text))
    return text.lower()

# No clearning applied for contextual-embedding based models 

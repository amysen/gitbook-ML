# Intro to NLP

**Stemming**

Stemming is a somewhat crude method for cataloging related words; it essentially chops off letters from the end until the stem is reached. This works fairly well in most cases, but unfortunately English has many exceptions where a more sophisticated process is required. SpaCy doesn't include a stemmer, opting instead to rely entirely on lemmatization

&#x20; &#x20;

**Lemmatization**

In contrast to stemming, lemmatization looks beyond word reduction and considers a language's full vocabulary to apply a morphological analysis to words. The lemma of 'was' is 'be' and the lemma of 'mice' is 'mouse'. Further, the lemma of 'meeting' might be 'meet' or 'meeting' depending on its use in a sentence.

Lemmatization is typically seen as more informative than simple stemming. It looks at surrounding text to determine a given word's part of speech, it does not categorise phrases.



**Tokenization**


# NER on Legal case

[![Build Status](https://travis-ci.com/ELS-RD/anonymisation.svg?token=9BHyni1rDpKLxVsHDRNp&branch=master)](https://travis-ci.com/ELS-RD/anonymisation)

Purpose of this projet is to apply Named Entity Recognition to extract specific information from legal cases like 
names, RG number, etc.

The input are XML files from **Jurica** database.
The learning is based on extraction from Themis.

Main NER algorithm is from [Spacy ](https://spacy.io/) library and is best described in this [video](https://www.youtube.com/watch?v=sqDHBH9IjRU).
  
Basically it is a **CNN + HashingTrick / Bloom filter + L2S** approach over it.

Advantages:
- no feature extraction (but suffix and prefix, 3 letters each, and the word shape)
- quite rapid on CPU (for Lambda deployment)
- works end to end without many dependencies

Project is done in Python and can't be rewrite in something else because Spacy only exists in Python.

Other approaches (LSTM, etc.) may have shown slightly better performance but are much slower to learn and for inference.

# Technology Rewiew

## Tensorflow tools for text retrieval problems

### Abstract

Tensorflow is one of the advanced and most-used Machine Learning tool. Tensorflow is mostly focused on Deep Learning, but its functions and even pre-trained models can be quite helpful for traditional NLP. In this article I will describe Tensorflow features for NLP and text retrieval along with brief code examples on Python. I will cover text processing tools; ML tools for Natural language processing; existing datasets and pre-trained models; and, finally, sulitions for text retrieval problems.

### Text processing

Text processing is the first step in solving machine learning problems. In many cases programmers and researchers deal with raw data, which needs to be cleaned, processed and transformed in order to provide further NLP steps the best data possible.
While it can be done with traditional algorithms like Porter or Lancaster Stemmer, Tensorflow provides its own implementation. Here is the list of some available tokenizers: WhitespaceTokenizer, the most basic string tokenizer which splits string into individual words. WordpieceTokenizer is more complex and works as stemmer. The tokenizer uses dictionary, built with top-down WordPiece generation algorithm. There are four steps: 1. Count word frequency (w, c) for the provided document. 2. For each given word generate a set of all possible substrings: *word -> ["w", "wo", "wor", "word", "#ord", "##rd", "###d"]*. 3. Build a hashmap *(S, TC)* for substring, where *TCk = sum(C0, C1, ..., Cn)*, where *Ci* is a cound of word *Wi*, which generated substring *k*. 4. Remove substrings *Si* which have *TCk* less than given threshold *T*. 5. For each of the substring left, subtract off its count from all of its prefixes. Tensorflow provides ready-to-use vocabularies, but allows you to build your own.

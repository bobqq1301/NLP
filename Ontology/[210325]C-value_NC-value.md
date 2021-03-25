# The *C-value/NC-value* Method of Automatic Recognition for Multi-word Terms

<small>Katerina T. Frantzi, Sophia Ananiadou, and Jun-ichi Tsujii. 1998. [The C-value/NC-value Method of Automatic Recognition for Multi-Word Terms](https://dl.acm.org/doi/10.5555/646631.696825). In Proceedings of the Second European Conference on Research and Advanced Technology for Digital Libraries (ECDL '98). Springer-Verlag, Berlin, Heidelberg, 585–604.</small>

# The C-value Approach

## The Linguistic Part

consists of the following:

* Part-of-speech information from tagging the corpus;
* The linguistic filter applied to the tagged corpus to exclude those strings not required for extraction;
* The stop-list.

### Tagging

Part-of-speech tagging is the assignment of a grammatical tag to each word in the corpus.

### The linguistic filter

It's important for a method to be able to extract all types of terms. Without any linguistic information, undesirable strings would also be extracted.

3 filters:
* *NounNoun<sup>+</sup>*,
* *Adj<sup>\*</sup>Noun<sup>+</sup>*,
* *((Adj|Noun)<sup>+</sup>|((Adj|Noun)<sup>\*</sup>(NounPrep)<sup>?</sup>)(Adj|Noun)<sup>\*</sup>)Noun*

### The stop-list

A stop-list for an SL in ATR is a list of words which are not expected to occur as term words in that domain. It is used to avoid the extraction of strings that are unlikely to be terms, improving the precision of the output list.

The choice of using a stop-list is again a matter of balance between precision and recall.

## The Statistical Part


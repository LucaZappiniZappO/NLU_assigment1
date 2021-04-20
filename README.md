# NLU_assigment1
The objective of the assignment is to learn how to work with dependency graphs by defining functions.

## Requirements
- spaCy
## Instructions
Open the Jupyter Notebook with Colab or another notebook reader


## Report
Define functions to:
1. extract a path of dependency relations from the ROOT to a token
    * input is a sentence, you parse it and get a Doc object of spaCy
    * for each token the path will be a list of dependency relations, where first element is ROOT
 
This point is implemented in the function `depPath()` that iterate over all the tokens and uses the property `token.ancestors` to retrive the path from the `ROOT` to the current token The list of the ancestors has to be reversed. The output is a dictonary with Keys are the tokens of the sentence and as values a the list of dependecy relations.

---
2. extract subtree of a dependents given a token:
    * input is a sentence, you parse it and get a Doc object of spaCy
    * for each token in Doc objects you extract a subtree of its dependents as a list (ordered w.r.t. sentence order)
    
The function that implement this point is `subTreeFromToken()` for all the tokens in the sentence extract the subtree using the property `token.subtree`.The output of this is a dictionart with keys the tokens and values the correspondant subtree.

---
3. check if a given list of tokens (segment of a sentence) forms a subtree
    * you parse a sentence and get a Doc object of spaCy
    * providing as an input ordered list of words from a sentence, you output True/False based on the sequence forming a subtree or not

This is implemented in the function `checkListIsSubtree()` that return `True` if a list of tokens is a sub tree for a token in the sentence using the property `token.subtree` otherwise `False`.

---
4. identify head of a span, given its tokens
    * input is a sequence of words (not necessarily a sentence)
    * output is the head of the span (single word)
    
The function `getSpanHead()` as the requirments returns the head of the span (from spaCy's documentation,Span is a slice from the document. In other words, a Span is an ordered sequence of Tokens)

---
5. extract sentence subject, direct object and indirect object spans
    * input is a sentence, you parse it and get a Doc object of spaCy
    * output is dict of lists of words that form a span (not a single word) for subject, direct object, and indirect object
    
The function `sentenceObjSpans()` takes as input a sentence and returns a dictionary containing as keys the relation (**'nsubj', 'dobj', 'iobj'**) and as values a list containing the words related to the key. In order to do that the sentence is parsed and for every token, if the dependency relation is one of the key above, a list containing the subtree of the token is populated.
**Indirect object** relations are represented by the **dative** keyword, since the **iobj** keyword is deprecated since in the latest versions of spaCy.

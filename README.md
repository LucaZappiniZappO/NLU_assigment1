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
2. extract subtree of a dependents given a token
    * input is a sentence, you parse it and get a Doc object of spaCy
    * for each token in Doc objects you extract a subtree of its dependents as a list (ordered w.r.t. sentence order)
3. check if a given list of tokens (segment of a sentence) forms a subtree
    * you parse a sentence and get a Doc object of spaCy
    * providing as an input ordered list of words from a sentence, you output True/False based on the sequence forming a subtree or not
4. identify head of a span, given its tokens
    * input is a sequence of words (not necessarily a sentence)
    * output is the head of the span (single word)
5. extract sentence subject, direct object and indirect object spans
    * input is a sentence, you parse it and get a Doc object of spaCy
    * output is dict of lists of words that form a span (not a single word) for subject, direct object, and indirect object (if present of course, otherwise empty)

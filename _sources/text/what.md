# what is text analysis?
Text analysis involves asking questions about text and using different computational methods, like Natural Language Processing (NLP) or visualization methods, to answer them. It can be as simple as generating a list of the most frequent terms in a text, or as complicated as a machine learning model that extracts words related to a particular topic. What distinguishes text analysis from other kinds analysis, even those that use similar visualization methods (such as word clouds or network graphs), is the focus on *text* as the object of study. 

Text analysis involves asking questions like:
  - What ideas are in the text? What are the central concepts?
  - What are some perspectives contained within the text?
  - What do certain words mean in their context, how are they being used?
  - What are the similarities and differences across certain words? What about contextual nuances across their usages?

## tasks and questions for NLP
Text analysis can, but does not necessarily have to, involve NLP tasks. Due to their focus on linguistic elements in text, NLP tasks like "Text Summarization," "Named Entity Recognition," and "Sentiment Analysis" are very useful for finding and analyzing patterns in text. While these tasks, which use "[rules-based](https://www.geeksforgeeks.org/rule-based-approach-in-nlp/)" or pattern matching approaches, have been around for decades, some of them have more recently adoped "probablistic" methods. These more advanced methods use Machine Learning algorithms to "train" programs to automate NLP tasks. 

For example, let's look at a Sentiment Analysis task, a popular NLP task that scores text based on whether it is positive or negative. A rules-based approach would hard-code the criteria for scoring, including specific and explicit examples of negative and positive words, directly into the algorithm's instructions. By contrast, a program trained to do Sentiment Analysis will process a pre-existing dataset made of texts and their sentiment scores, which is called "training data," so that it can learn (so to speak) which kinds of texts tend to have certain scores. 

Today we will be exploring a library, or a collection of code, for doing NLP in Python. This library, called `spaCy`, enables researchers to extract text based on its linguistic features, like word forms or parts of speech. This extraction can be part of a larger process of extracting data that will later be visualized in a graph or chart, such as with [Voyant-Tools](https://voyant-tools.org/), (my personal favorite graphical tool). Or, the process can be part of a preparing a dataset for Machine Learning tasks. Here, we would use the results from our extraction to help train a new statistical model, to process even more text! 

Before jumping into analysis, however, it is important to discuss briefly how we gather and prepare data in the first place. 
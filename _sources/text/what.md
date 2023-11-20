# what is `spaCy`?

## tasks and questions for NLP
`spaCy` is a library in Python for Natural Language Processing, or
NLP. A library is just a word for a collection of code for doing a
specific task, like NLP. Before going into the specifics of the
`spaCy` library, let's talk about NLP, which refers to computational
methods used to study human language, or "natural langauge." It is a
subfield of computer science and linguistics, which started in the
1950s and 1960s with what are called "rules-based" methods, and has
grown with technological advances with Machine Learning with
"probablistic" methods (I will explain these terms in a
moment). First, it's important to understand that NLP is divided into
many different kinds of tasks, some of which you may have heard of,
like "Text Summarization," "Topic Modeling," "Named Entity
Recognition," and "Sentiment Analysis." To do these tasks, researchers
can choose between "rules-based" or "probablistic" methods. Most
recently, NLP harnesses "probablistic," or Machine Learning methods
(like the ones that power Large Languages Models underlying *ChatGPT*,
for instance) to do thinks like make predictions and generate text.
Probablistic means that the researchers has trained a computer program
to recognize a certain pattern a sample text, and then to make
predictions about where that pattern appears in new text.
Rules-based, by contrast, means that a researcher will write out a
specific rule for searching the text, kind of like a very
sophisticated control-f. In this workshop, we will be using `spaCy` to
work with both kinds of methods across NLP, so it's a good idea to
know a little bit about how and why they are different.

The `spaCy` library enables researchers to work with large amounts of
text in a programmatic way, writing rules or deriving patterns to
extract, visualize, and analyze important parts of the text. By
processing elements of language, NLP is part of a larger process
called text analysis. Text analysis involves asking questions like: 
  - What ideas are in the text? What are the central concepts?
  - What are some perspectives contained within the text?
  - What do certain words mean in their context, how are they being
    used?
  - What are the similarities and differences across certain words?
    Contextual nuances?

## adding "annotations" to text
How does `spaCy` make this possible? It does all of it by adding tags,
or what the library's creators call "annotations," to text. These are
descriptive information which is appended to text when it is passed
through the `spaCy` processing "pipelines," so to speak. The
annotations contain mostly linguistic information, like parts of
speech, punctuation, where sentences begin and end, and more. The
program decides which annotations to apply based on what the
information it contains within its own dictionaries and based on
predictions that it makes from its underlying language model. For
example, when it sees the word "sheep," it will check the dictionary
to see if the word is a noun or verb, and so on. If the desired
information isn't there, it will then make a guess based on other
aspects of the sentence (grammatical dependancy, for example)
generalizations from past data. This might not be so useful for a word
like "sheep," but it can be very useful for a word like "trans," which
is used as both a noun and adjective, and sometimes even a verb. You
can see that the annotation process combines both rule-based and
probablistic methods. 

The kind of text analysis differs from the kind that appears as word
clouds or network diagrams. Those are more about visualizing patterns
in text, whereas this is more about writing code to find the patterns
in the first place. Rather than visualizations, this workshop is about
writing code that will enable you to extract text. You can think of
this as a preparation for more visual kinds of text analysis. You have
to find the patterns before you can visualize them. This code will use
the power of `spaCy` to seek and define these patterns. When we are
done, we can then use a graphical tool to visualize or display the
results. Or we could even use the new patterns to help train a new
statistical model (to process even more text). Stay tuned for my
Wintersession on "Playing with AI" for more information about that.

# what is text analysis?

## tasks and questions for NLP
Today we will be exploring a library in Python for Natural Language Processing, or NLP. A "library" in Python means a collection of code for doing a specific task, like NLP. 

Before going into the specifics of this library, let's talk about NLP, which refer to computational methods used to study human language, or "natural langauge." Starting in the 1950s and 1960s, the field has quickly grown with technological advances with Machine Learning in the past two decades, and especially in the last five years. 

NLP is divided into many different kinds of tasks, like "Text Summarization," "Topic Modeling," "Named Entity Recognition," and "Sentiment Analysis." To do these tasks, researchers can choose between "rules-based" or "probablistic" methods. Thanks to Machine Learning advances, NLP harnesses "probablistic," or methods that can make predictions and generate text. Probablistic means that  a computer program that has been "trained" to recognize a certain pattern a sample text, and then to make predictions about where that pattern appears in new text. Rules-based, by contrast, is a much older method where the patterns are hand-coded into the program, like a very sophisticated control-find. In this workshop, we will be using `spaCy` to work with both kinds of methods across NLP, so it's a good idea to know a little bit about how and why they are different.

## what is text analysis?
NLP is part of text analysis, but  it differs from the kind of text that appears as word clouds or network diagrams. Those are more about visualizing patterns already discovered in text. As distinct from NLP, text analysis refers to a broader process of asking questions about text and using different methods, like visualization methods, to answer them. By processing elements of text, particularly linguistic elements, NLP can certainly be part of the larger process of text analysis, but it is not strictly necessary. 

Text analysis involves asking questions like:
  - What ideas are in the text? What are the central concepts?
  - What are some perspectives contained within the text?
  - What do certain words mean in their context, how are they being used?
  - What are the similarities and differences across certain words? What about contextual nuances across their usages?

## adding "annotations" to text
The `spaCy` library enables researchers to extract text based on its linguistic features. You can think of this extraction process as a preparation for more visual kinds of text analysis, where you can write code to find the patterns that you will later visualize. 

The `spaCy` library has powerful processing for linguistic features to seek out patterns in text. How does `spaCy` make this possible? It does all of it by adding tags, or what the library's creators call "annotations," to text. These annotations are filled with linguistic information, which is appended to text when it is passed through processing "pipelines," discussed in the next couple of sections. The linguistic information includes parts of speech, grammatical dependency, punctuation, sentence and clause spans, and a lot more. 

The pipeline adds annotations to text based off what it knows about language usage in its own dictionaries and language models.  For example, when it sees the word "sheep," it will check the dictionary to see if the word is a noun or verb. However, if it comes across the word "trans," which can be an adjective, a prefix, or a shortened form of a longer word like "transgender," it will then make a guess based on other aspects of the sentence, the context surrounding the word. You can see that the annotation process combines both rule-based and probablistic methods. 

When we are done with extracting text, we can then use a graphical tool (like [Voyant-Tools](https://voyant-tools.org/), my personal favorite) to visualize or display the results. Or we could even use the new patterns to help train a new statistical model, to process even more text! Stay tuned for my Wintersession on "Playing with AI" for more information about that. 

## generating research questions
It's a good idea to have a sense of what you're looking for before you jump into analysis. Though all text analysis (and any kind of data analysis more generally) can be a recursive process of formulating questions, doing some kind of manipulation, shifting your focus, and then running the analysis again.

Text analysis is a speculative and creative endeavor, because it requires the human running the program to imagine what kinds of patterns they might find in the data. The process of analysis itself will bring you to re-frame your perspective and re-write your questions. Though it feels like a step backward, this recursive process means that you're making progress toward the goal. 

Before you begin analysis, ask yourself what are some of the *most important* things you want to know about the data? For my dataset, I want to know how each bill is defining gender, sex and sexuality. By getting a list of definitions for these terms, I can start to explore the relationship between them. I can also begin to understand any possible conflation of gender as a cultural and expressive phenomenon and sex as a biological one, something I am anticipating from the results. 

*Note: Informing these questions is an understanding of gender drawn from a linked vocabulary of LGBTQ+ terms, the "[Homosaurus Vocabulary](https://homosaurus.org/)." This vocabulary is designed to improve the description and discoverabiliy of LGBTQ+ information by offering definitions of various LGBTQ+ related terms. It defines gender as a cultural phenomenon, "A socially constructed system that gives meaning to masculinity and femininity," which is "developed through the interaction of social roles and expectations, one’s response to those expectations, one’s physiology, and one’s internal sense of self" ("Gender," Homosaurus). Sex, by contrast, is "The category assigned to an individual to describe their body and its role in sexual reproduction, usually based on external anatomy, but also including chromosomes, gene expression, hormones, and internal and external reproductive/sexual organs" ("Sex," Homosaurus).*

# Introduction to Python for Working with Text

Introducing the Python programming language as a tool that takes data,
organizes it into collections/groupings, with the goal of doing
something to that data.

The first workshop will set up the core concepts: data types, variables,
functions, loops, and logic. The following workshops will build on these
concepts in web scraping and text analysis tasks.

## Upcoming Digital Scholarship Workshops

Register at library website: /calendar CS consults link

## Pedagocial models using Jupyter-Book

[Introduction to Python for
Humanists](https://python-textbook.pythonhumanities.com/intro.html), by
Dr. WJB Mattingly, Smithsonian Data Science Lab

[Introduction to Cultural Analytics &
Python](https://melaniewalsh.github.io/Intro-Cultural-Analytics/welcome.html)
by Prof Melanie Walsh, U of Washington

[Data 8 Course](https://inferentialthinking.com/chapters/intro.html) at
Stanford

## Learning Objectives

Goals:

-   Introduce ways of saving and categorizing data in Python.
-   Introduce ways of working with data through functions and methods.
-   Introduce the order of operations in code, such as in logical
    structures and iterative processes.
-   Familiarity with basic Python syntax.

# Google Colab environment

There are many ways to use Python. For this workshopwe will be using
[Google Colab](https://colab.research.google.com), a browser-based tool
for running Python code. Like Google Docs, Google Colab creates a
collaborate environment hosted on the cloud for authoring content.

Signficantly for programmers, Google Colab offers Python software
pre-installed on the cloud environment. Whereas most Python environments
require installations (some of which can be really complicated), Google
Colab enables users to jump right into coding.

Google Colab creates an interactive coding environment where you can
enter a Python expression into the black text box, called a \"cell\",
and execute, or \"run,\" the expression by pressing enter. Please see
[this tutorial](https://colab.research.google.com/?utm_source=scs-index)
for specifics on how to run Python within the Google Colab environment.

# Opening Script

We begin with a script as a kind of landmark for where the workshop will
go. By the end, participants should be able to read the script and
understand how it works.

(There is also a bug hidden in the code for the students to find.)

The text from this script is taken from the \"[Feminist Data
Manifest-NO](https://www.manifestno.com/home)\" by Marika Cifor,
Patricia Garcia et al. In the words of the creators, \"The Manifest-No
is a declaration of refusal and commitment. It refuses harmful data
regimes and commits to new data futures.\" The following are the first
five declarations from the \"Manifest-NO.\"

``` python

# a loop that goes through a list of sentences and checks if they
# contain the word "Refuse". If it does contain the word, appends the
# sentence to a new list.

text = ''' 1. We refuse to operate under the assumption that risk and harm associated with data practices can be bounded to  mean the same thing for everyone, everywhere, at every time. We commit to acknowledging how historical and systemic patterns of violence and exploitation produce differential vulnerabilities for communities.
  2. We refuse to be disciplined by data, devices, and practices that seek to shape and normalize racialized, gendered, and differently-abled bodies in ways that make us available to be tracked, monitored, and surveilled. We commit to taking back control over the ways we behave, live, and engage with data and its technologies.
  3. We refuse the use of data about people in perpetuity. We commit to embracing agency and working with intentionality, preparing bodies or corpuses of data to be laid to rest when they are not being used in service to the people about whom they were created.
  4. We refuse to understand data as disembodied and thereby dehumanized and departicularized. We commit to understanding data as always and variously attached to bodies; we vow to interrogate the biopolitical implications of data with a keen eye to gender, race, sexuality, class, disability, nationality, and other forms of embodied difference.
  5. We refuse any code of phony “ethics” and false proclamations of transparency that are wielded as cover, as tools of power, as forms for escape that let the people who create systems off the hook from accountability or responsibility. We commit to a feminist data ethics that explicitly seeks equity and demands justice by helping us understand and shift how power works.'''

sentence = text.split()

results = []
for sentence in text:
    if 'Refuse' in sentence:
    results.append(sentence)

print(results)


```

# Data types

All real world objects and ideas are transformed into computational
format, into *types of data*. There are many data types in Python, but a
few of them will be important for us in this workshop.

We use the `type()` function to check data types. These include:

-   `integer` - whole number
-   `string` - characters within quotes (sequences)
-   `boolean` - true or false values (for logic)
-   `list` - collection of all of the above.

Two things to keep in mind about data types:

-   First, all information that you want to work with must fit into one
    of these data types. The transformation of real world objects and/or
    ideas into computer-readable data inevitably reduces or simplifies
    the original. For example, words with semantic meaning to a human
    become a `string`, a sequence of characters wrapped by quotation
    marks, or someone\'s age expressed as an `integer`, a whole number
    in years. The significance of this reduction will be more apparent
    when you start to work with data in the text analysis workshop.
-   Second, that each data type has associated \"methods\" that go with
    it. You can do things with integers that you cannot do with strings,
    for example. You can add numbers together, but not strings. This
    will be the source of many, many errors as you get started.

Other types you might hear about: floats, tuples, dicts, etc. You can
read more about these [on
W3Schools](https://www.w3schools.com/python/python_datatypes.asp).

# Variables

So we have data in a digital format, as a specific type of data, but how
do we work with that data?

Before we can use that data in any kind of programming, we need to save
it. To give it a name, or a label. This is where *variables* become
important.

A variable assigns data, a value, to a label, say `x`. We could save the
integer 34 to `x` like so,

``` python
x = 34
```

With some exceptions, we can assign variables to almost any label we
want, like `x` or `y`. But, we want to make sure that anybody reading
our code will have as best a sense as possible about what the variable
refers to. It is therefore encouraged to use precise but meaningful
variables, like `age`, something that reflects the value most accurately
and succinctly.

Variables can be used to store any data type, like strings, lists, and
even booleans.

``` python
age = 34
name = 'filipa'
breakfast = ['granola', 'cashew yogurt', 'muffin', 'coffee']
truth = True
```

As a label for data, variables represent what is officially called an an
*object* in Python. Objects are ways of thinking about data in its
digitized form and what can be done to data in that form. Depending on
the type of object (like a string, for example) we can run different
kinds of computations. When applied to objects, the computations we can
do are called *methods*.

For example, with a string type of object, we can use the `upper()`
method to make all of the characters in the string uppercase.

``` python
greeting = 'hello'
greeting.upper() 
```

Here, we are using *dot syntax*, that is, a period `.` in between the
variable (the object) and the method (the action). What comes before the
dot is the data, saved to a variable. What follows the dot in dot syntax
is the action being applied to the variable.

## a note on Methods and Functions

You may have already noticed that a *method* is very similar to a
*function*, which we have seen previously with the `type()` function
that evaluates data types. Both methods and functions do something to
data. The difference between them has to do with syntax. A function
takes data in between the parentheses, like when we pass a string into
the `type()` function with `type('hello')`. A method, by contrast,
appends an action to the end of an object using dot syntax, like with
`greeting.upper()` example above.

The differences in syntax indicate a deeper difference between functions
and methods, which has to do with *object-oriented programming*, which
is an advanced concept that we will discuss futher in the Web Scraping
workshop. For now, though, it\'s enough to know that functions and
methods are recognizable by their syntax, where one takes data within
parentheses and the other appends to data using dot syntax.

Another way of thinking about the differences between methods and
functions is that methods only work with specific types of data. There
are string methods, like with `upper()` above, and with `split()`, which
*splits* a long string, say a paragraph of text, into individual
strings. Like the example below, the `split()` method will separate the
data into individual items based on whitespace.

``` python
text = '''
1. We refuse to operate under the assumption that risk and harm associated with data practices can be bounded to  mean the same thing for everyone, everywhere, at every time. We commit to acknowledging how historical and systemic patterns of violence and exploitation produce differential vulnerabilities for communities.
  2. We refuse to be disciplined by data, devices, and practices that seek to shape and normalize racialized, gendered, and differently-abled bodies in ways that make us available to be tracked, monitored, and surveilled. We commit to taking back control over the ways we behave, live, and engage with data and its technologies.
  3. We refuse the use of data about people in perpetuity. We commit to embracing agency and working with intentionality, preparing bodies or corpuses of data to be laid to rest when they are not being used in service to the people about whom they were created.
  4. We refuse to understand data as disembodied and thereby dehumanized and departicularized. We commit to understanding data as always and variously attached to bodies; we vow to interrogate the biopolitical implications of data with a keen eye to gender, race, sexuality, class, disability, nationality, and other forms of embodied difference.
  5. We refuse any code of phony “ethics” and false proclamations of transparency that are wielded as cover, as tools of power, as forms for escape that let the people who create systems off the hook from accountability or responsibility. We commit to a feminist data ethics that explicitly seeks equity and demands justice by helping us understand and shift how power works.
'''

text.split()
```

The output shows the long string split into several smaller strings.
Note that what was previously a `string` data type is now a `list` data
type. We can easily check the data type using the `type()` function.

First, thought, we need to save the output of `split()` to a new
variable, which will be called \"words.\" Saving the output of the
method to a new variable then allows us to do more things with that
data.

``` python
words = text.split()

type(words)
```

This code also introduces a bit of abstraction, where new variables are
created by saving the output of computations, like `split()`. This kind
of abstraction is common in programming, as data is transformed into new
formats, which enable further types of computations. Later in workshop,
creating new variables will be very useful for the kind of work we want
to do with text.

# Lists

The `list` data type is perhaps the most common data type for working
with text. Textual data tends to be saved as a `list`, or a collection
of separate `strings`, each string consisting of a sequence of
characters that represents a single word. It is important to remember
that while humans might read each `string` as a word, the computer does
not ascribe any semantic value, but only reads it as a sequence of
characters.

## `list` methods

Like strings, lists also have specific *methods* that only work with
list type data. List methods, as they are called, enables one to do
various things to data contained in lists.

Some of the more popular methods have to do with creating and modifying
items in a list. One list method, `append()`, adds items to a list. For
example, to a list of breakfast items, one can add additional items
using `append()`:

``` python
breakfast = ['bagel', 'cream cheese', 'coffee']
breakfast.append('orange juice') 
breakfast 
```

Other methods, `remove()` and `pop()` take items out from a list. While
`remove()` takes out a specific item (declared within the parentheses),
`pop()` will only take out the last item in a list, \"popping\" it off,
so to speak.

``` python
breakfast.remove('bagel') 
breakfast

breakfast.pop()
breakfast
```

Besides adding and deleting items, we can also sort items in a list. For
these, we use the `sort()` and `reverse()` methods.

To show the power of these methods, we\'ll work with a larger list, like
a list of words from this workshop\'s description. First, we will copy
and paste the workshop description as a single string. Then, we will
split the string, saving the output to a new variable. Once the data is
in list format, we will run the `sort()` and `reverse()` methods.

Notice a new syntax here, the triple quotation marks (instead of
single), for saving the string. The triple quotes enables our strings to
break lines and include other punctuation without messing with the
string format.

``` python
text = ''' 1. We refuse to operate under the assumption that risk and harm associated with data practices can be bounded to  mean the same thing for everyone, everywhere, at every time. We commit to acknowledging how historical and systemic patterns of violence and exploitation produce differential vulnerabilities for communities.
  2. We refuse to be disciplined by data, devices, and practices that seek to shape and normalize racialized, gendered, and differently-abled bodies in ways that make us available to be tracked, monitored, and surveilled. We commit to taking back control over the ways we behave, live, and engage with data and its technologies.
  3. We refuse the use of data about people in perpetuity. We commit to embracing agency and working with intentionality, preparing bodies or corpuses of data to be laid to rest when they are not being used in service to the people about whom they were created.
  4. We refuse to understand data as disembodied and thereby dehumanized and departicularized. We commit to understanding data as always and variously attached to bodies; we vow to interrogate the biopolitical implications of data with a keen eye to gender, race, sexuality, class, disability, nationality, and other forms of embodied difference.
  5. We refuse any code of phony “ethics” and false proclamations of transparency that are wielded as cover, as tools of power, as forms for escape that let the people who create systems off the hook from accountability or responsibility. We commit to a feminist data ethics that explicitly seeks equity and demands justice by helping us understand and shift how power works.'''

# when splitting a list, remember that we have to save the
# results to a new variable
text_split = text.split() 

# with the sort method, we don't have to save the results to
# a new variable. It will automatically just print them.
text_split.sort()

```

Notice a couple of things:

1.  I cheated. I used a `string` method when I said I was only going to
    show you `list` methods. Can you spot the rouge `string` method?
    Hint: you\'ve seen it before, and it is attached to a string type of
    object.
2.  Some methods return new objects, while other methods simply change
    existing ones. The `sort()` method is one that changes the existing
    object. Unlike the `split()` method, we don\'t have to save the
    results of `sort()` to a new variable. `sort()`, and other methods
    like `reverse()`, change the item in place, meaning that the
    existing list is modified. `split()`, by contrast, creates a new
    object, which needs to be saved. This is a bit of an advanced
    concept in Python, so there is no rush to fully grasp it now.
3.  The resulting list is organized alphabetically, which means that any
    punctuation and/or numbers will appear before any letters. This will
    explain why the results may not seem alphabetically sorted at first.

Remember that these `list` methods will not work on `string` type data.
Try running a few of them on a string, just to see what happens.

## `list` indexing

While list methods enable one to do things like create and modify lists,
list indexing enables one to access specific items in a list.

List indexing is super useful for working with large lists, such as a
full text, or even a collection of texts. It works by accessing items
according to their position (their location) within a list. The moment a
list is created in Python, it comes with an implicit index, where each
item is assigned a numerical position. The first item is assigned to the
position 0, the second item is assigned 1, the third item is assigned 2,
the fourth item assigned 3, and so on.

Why does list indexing begin with 0? The answer is a bit complicated,
and gets into technical details of how computer memory works in
programming. Put simply, it has to do with the memory location being
defined or based by offsets. Because the first item of a list is also
the origin location of the list, its offset is 0. In other words, to go
to the first item in the list, there is no movement (or offset) from the
current, or origin, location. The second item of the list requires 1
movement from current location, and is therefore assigned to the
location 1.

The syntax for list indexing is to declare the list name followed by
brackets that contain the index. The first item in a list would be
accessed with the index 0.

``` python
breakfast = ['granola', 'cashew yogurt', 'strawberries', 'mango',
'coffee']

breakfast[0]
```

The third item in a list would be accessed with the index 2.

``` python
breakfast[2]
```

Python offers a specific way of accessing the last item of a list, which
can really useful for taking a peek at the end of a list. The last item
in a list is accessed with the index -1. This might seem a little
strange, but if you imagine the list items forming a circle which goes
clockwise, then going backward (counterclockwise) one step would take
you to the last item. That backward step is represented with -1.

``` python
breakfast[-1]
```

## `list` slicing

Like list indexing, list slicing uses a list\'s implicit index to access
items. Unlike list indexing, however, slicing enables someone to access
a range, or a \"slice,\" of items from a list. This capability becomes
convenient when working with large lists. For example, we might take a
look into a section of a list without loading the entire list, or we
might grab a portion of that list to create a new list.

The syntax for list slicing is a bit wonky, but like list indexing, it
is just a matter of getting used to the particulars of Python\'s
internal indexing.

To get a slice, you need to enter the *starting* and *ending* point of
the section which you want to grab. In between these values, insert a
*colon*, which represents every item that occurs in between the start
and end points. A list slice therefore looks like the following:

``` python
breakfast [2:5]
```

Here's the tricky part: the starting point is always inclusive, and the
ending point is always exclusive. Which means that the slice will take
everything starting at position 2, up until, but exclusing, the item in
position 5. This rule for list slicing can cause some confusion, and
it\'s best just to memorize it.

One more important thing to know is the colon. In its position between
the start and end point, it signifies everything in between. But if
there is nothing before or after the colon, then the colon represents
everything until the beginning or end of the list. For example, the
syntax \[1:\] will take everything starting at index 1 (or the second
item) until the end of the list. Similarly, \[:4\] will take everything
from the start until the fourth index position of the list.

This trick with the colon can be really nifty for grabbing the first 10
or first 100 items from a list, allowing you to take peeks into the list
items without printing the entire list.

``` python
breakfast [3:]
```

List methods, indexing, and slicing are crucial tools for working with
lists. The next sections will introduce skills for working more
programmatically with lists.

# Loops

Loops are probably one of the more conceptually difficult concepts for
new programmers, but once they are used a bit in practice, it becomes
easier to grasp. Loops are ways of working with collections of data
(like lists) by isolating each item from the list, one at a time. A loop
will go through each item in a list, for example, a list of breakfast
items, to do a specific action, like print each item from the list.

``` python
for item in breakfast:
  print(item)
```

Here, we\'ve also introduced a new function, `print()`. This function
will \"print,\" or display, whatever data you pass into the parentheses.
Some historical context for the name of the `print()` function: it comes
from a time before screens, when computers literally *printed* the
output of their computations. The name of this function is a holdover
from that time, but now it means *display* on the screen rather than
print.

Loops work with strings as well. We might print each character (or
letter) from a string like \"hello\":

``` python
for letter in 'hello':
  print(letter)
```

The syntax for writing a loop contains two lines. The first line
identifies one item from a collection of items, such as a list. You can
think of the first line saying something like \"for (each) item (inside
this) breakfast (list).\" Then, the second line specifies the action
done to that item, in this case, the instruction to print that item.

``` python
for item (in) breakfast:
  print(item)
```

## a note on variable names

The variable which indicates each individual item (`item`) can be
assigned to any name. That\'s because the variable is assigned on the
fly, *as the loop is being executed*. This goes against usual practices
with variable assignments, which always need to be assigned beforehand,
or there will be a `NameError` because the variable hasn\'t been
defined.

``` python
for x in y:
    print(x)
```

For example, we could very well name the individual item x, or any other
letter, and the loop would run just fine. However, it\'s helpful to give
as semantically meaningful names as possible, to avoid code that gives
no indication about the data contained in the variables. This will be
really useful for other people reading your code as well. The trick is
to be semantically meaningful while keeping your code as concise as
possible.

For future reference, the convention is to use the letter `i` as
shorthand for indicating an item from a list.

``` python
for i in breakfast:
    print(i)
```

## `string` methods

Loops are great ways to do things en masse to data, such as to
individual words within a text, in other words, to `string` type data
that is contained within a `list`.

Looping over strings in a list is a great way of programmatically
applying a rule or task to all the strings in a list. For example, you
might want to lowercase all of the letters from our dataset for
regularization purposes. To do that, use the `lower()` method.

Can you guess what it does?

``` python
'HELLO'.lower()
```

Now, let\'s combine this `string` method with what we know about loops.
Let\'s try it on a list of items with varying levels of capitalization.

``` python
cities = ['Lisbon', 'Setubal', 'Alcacer do Sal', 'Lagos']
for city in cities:
   print(city.lower())
```

Here, the loop goes through each item in the list of \"cities,\" and
lowercases that item while also printing it (remember the `print()`
function?). Here, the `lower()` method is attached to the \"city\"
variable, which is assigned to each item, or city name, in the list.

Let\'s try to do the same with a longer list, like the text from the
\"Feminist Data Manifest-NO\". First, though, we need to split our
`text`, which is currently one long string, into individual strings
within a list. For that, we use the string method, `split()`, which we
saw briefly above when we talked about list methods.

``` python
words = text.split()
words 
```

We can see our text as a list of strings, saved to the variable
\"words.\" Now, we can do things programmatically to each `string` in
the `list`, like lowercase the items.

``` python
words_lower = []
for i in words:
  words_lower.append(i.lower())

words_lower
```

This loop goes through each item in the list of words, lowercases it,
then adds that word to a new list, called `words_lower`.

Notice here that I\'ve introduced a few new things:

1.  Above the loop, I\'ve created an empty list, called
    \"words~lower~,\" where we will eventually drop our lowercased
    words.
2.  The first line of the loop uses the `i` variable to stand in for
    each time in the list. I\'m going to start using the `i` variable in
    this way, to get used to the widely popular convention of using it
    in loops.
3.  The last line of the loop uses a `list` method to add data to our
    empty list. Notice that the list method `append()` is attached to a
    list object, while the string method `lower()` is attached to a
    string object.

# Logic

Logic allows programmers to write code that can \"make decisions\" based
on certain conditions. It enables what is called \"control flow,\" which
is to direct the order of code execution throughout a program.

Logic works by inserting conditions into the code. If the condition
evaluates to be true, then a specific expression can execute. If the
condition evaluates to be false, then another expression (or no
expression at all) can execute.

Logic structures are very useful when working with text, because we can
specify what kinds of text we want to work on, specific things that we
want to change or do with that text.

## `boolean`

First, let\'s take a closer look at a very important (and thus far
ignored) data type, `booleans`. If you remember, a boolean is a `True`
or `False` value.

``` python
type(True)
```

``` python
type(False)
```

But why do these values need a separate data type? The answer is because
computer programs *make decisions* based on whether expressions are true
or false.

``` python
10 > 5
```

To evaluate whether expressions are true or false, we can use certain
operators, like `==` to check equivalence.

``` python
10 == 5
```

Note that the equivalence operator `==` is different from the assignment
operator `=` which would be used to assign a variable say in `x = 3`.

## `if statement`

Using `boolean` logic, we can write a conditional statement that checks
whether certain conditions are true. This type of statment is called the
`if statement`

``` python
if 10 > 5:
    print("This expression is true!")
```

This conditional statement will print a string if the condition
evaluates to `True`. Python will first check if the integer 10 is
greater than 5, and if it is, it will print the string contained within
the `print()` function\'s parentheses.

Notice that like the `for loop` the code here indents automatically on
the second line. This creates what is called a \"code block,\" which is
Python\'s way of grouping code into one logical unit, whose expressions
should be executed together, in the order that they are written.

The `if statement` can also be expanded to specify more conditions, with
the `elif` expression, or to include a catchall for cases that do not
meet the conditions, with `else`

``` python
if 10 == 5:
    print("10 is equal to 5")
elif 10 == 9:
    print("10 is equal to 9")
else:
    print("10 is not equal to 5")
```

We can add as many `elif` expressions as we like, to account for many
conditions in our code.

## loop with conditions

In this next and final section, we will add logic to our loop fro the
previous section. Remember that a loop goes through a collection of
items, like strings in a list, and does something to each item.

``` python
words_lower = []
for i in words:
  words_lower.append(i.lower())

words_lower[:20]
```

Notice that we are using list slicing to print only the first twenty
words from the output, so we can avoid printing out a large list, which
takes a lot of space on the screen.

Next, we will write a new loop that includes a condition. This condition
will check whether a sentence from the text contains the word
\"refuse.\" If it does contain the word, it will add it to the new list,
which we will call \"results.\"

``` python
sentences = text.split('.')

results = []
for i in sentences:
  if 'Refuse' in i:
      results.append(i)

 print(results)

```

Notice something new: we\'ve split the text by *sentence* rather than
*word*. How did we do that? The `split()` method enables us to specify
(if we choose to) a delimiter to split the string. If we do not specify
a delimiter, then it defaults to whitespace. For this case, we will
split the string by period, which we will put between quotes `" "`. The
output will then be a list of sentences.

If you typed in the code exactly as I have written it, the output should
show an empty list (with empty brackets).

Why do think it did that? *Hint: remember that computers are **very**
literal and will take the condition exactly as it is written*.

# sources

Cifor, M., Garcia, P., Cowan, T.L., Rault, J., Sutherland, T., Chan, A.,
Rode, J., Hoffmann, A.L., Salehi, N., Nakamura, L. (2019). Feminist Data
Manifest-No. Retrieved from: <https://www.manifestno.com/>.

# future workshops

## overview for Web Scraping

### Functions

### Importing libraries

### Objects

## overview for Text Analysis

### file types, importing files.

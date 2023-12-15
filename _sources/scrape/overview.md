# workshop overview
## learning objectives
This workshop explores approaches for programmatically extracting
information from websites using recent anti-trans legislation in the
US as an example. It applies the BeautifulSoup4 library and principles
from object-oriented programming to scrape and parse text data from
anti-trans bills in the US.

This workshop introduces:
- the differences between web scraping and other data gathering methods like web crawling and APIs
- ethical and legal considerations for web scraping
- tools for working with HTML and web browsers generally 
- code libraries for web scraping and data analysis
- methods for extracing text from web browsers
- object-oriented programming syntax for parsing text based data

This workshop will not to make you an expert at web scraping, but it will create a solid foundation for you begin web scraping projects on your own, even if you are a total beginner. 

## anti-trans legislation

The past couple of years has seen an explosion in anti-trans legislation that restricts basic rights and recognition for trans people. In 2023, more than 500 bills have already been proposed that prevent trans people from using bathrooms, playing in sports, accessing healthcare, and more in ways that accord with their gender identity. Of those 500 proposals across state legislatures, 83 have passed. Compare that number with last year, 2022, 174 bills were proposed, and 26 passed. See the [Trans Legislation Tracker](https://translegislation.com/) for more information.

This workshsop uses Python to scrape basic metadata about the 83 bills that have passed in 2023. This dataset, which is relatively small in size, will be a starting point for a larger dataset to be used in our next workshop on Text Analysis. For that workshop, participants will use Python to gather, clean, and analyze the full text of the bills themselves from `congress.gov`. They will explore how the terms "gender" and "sex" are being defined across the legislation, among other questions about the language contained within them. 

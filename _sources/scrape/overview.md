# workshop overview
## learning objectives
This workshop explores ethical approaches for programmatically extracting information from websites using recent anti-trans legislation in the US as an example. It applies the BeautifulSoup4 library and principles from object-oriented programming to scrape and parse text data from online trackers about current anti-trans bills in the US. 

This workshop introduces:
- the differences between web scraping and other data gathering methods like web crawling and APIs
- ethical and legal considerations for web scraping
- tools for working with web browsers, like HTML, the Inspector, and Web Developer Tools 
- code libraries for web scraping and data analysis, like BeautifulSoup4 and pandas
- methods and functions for extracing text from web browsers
- object-oriented programming syntax for parsing text based data

This workshop will not to make you an expert at web scraping, but it will create a solid foundation for you begin web scraping projects on your own, even if you are a total beginner. 

## anti-trans legislation

The past couple of years has seen an explosion in anti-trans legislation that restricts basic rights and recognition for trans people. In the first ten months of 2023, over 500 bills have already been proposed that prevent trans people from using bathrooms, playing in sports, accessing healthcare, and more in ways that accord with their gender identity. Of those 500 proposals across state legislatures, 83 have passed so far. (Compare that with last year, 2022, where 26 out of 174 bills were passed.) See the [Trans Legislation Tracker](https://translegislation.com/) for more information. 

This workshsop uses Python to scrape basic metadata about the 83 bills that have passed in 2023. This dataset, which is relatively small in size, will be a starting point for a larger dataset that includes the full text of the bill. Then, for the next workshop, Text Analysis, participants will use Python to clean and analyze the bills' text, for example, to explore how the terms "gender" and "sex" are being defined across the bills. 
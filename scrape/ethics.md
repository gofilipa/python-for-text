3# ethics

## what is legal? what is ethical?
The question is crucial needs to be asked *prior* to scraping. There's
a lot of information about the ethics and legality of web scraping,
written in much more detail that I can here. For example, check out
University of Michigan's excellent
[guidebook](https://docs.google.com/document/d/11LZweIYD9MmjiZgY-VW1IXUPOP1k-SwXNiOdJDVC7Vw/edit#heading=h.ut4ttuudwb6i)
on the subject. 

### ethical: 
Before you even start thinking about legality, you want to spend some
time thinking carefully about *who* your data pertains to (who is the
data about?) and how gathering, doing analysis, and/or publishing that
dataset will affect the groups involved. You especially want to do
this work if your project involved already marginalized communities. 

Here are some basic questions you want to ask as you get into a web
scraping project:
- Whose data am I scraping? Who owns the data? (often times, the
  answers are different)
- Is the data public or private data? Does it contain any identifying
  characteristics?
- What will I do with the data? (gather it, analyze it, publish it
  online, all of the above, etc.)
- What will be the effect of my actions on the group who the data is
  about?

The most important thing is to assess any vulnerabilities about the
people that the data pertains to. And this can only be answered on a
case by case basis. There is no hard and fast rule that applies to all
groups. 

For example, if you are scraping data about an indigenous populations
across the United States, you might want to keep in mind that these
groups are understandably protective and may not want some information
to be made public. In that case, you'd want to reach out to the groups
directly and ask permission, or you'd want to keep the data private
(doing analysis on your own) and only discuss or publish the results
of the analysis.

Another example, the *Trans Legislation Tracker*, is a different
case. Collecting and publishing that data would benefit the ones whom
the data is about by bringing awareness and attention to the
issue. The goal of the project--to do a text analysis of terms like
"gender" and "sex" in the bills--also benefits trans people, because
it creates an opportunity to examine the ways that language is being
used to oppress and limit them. 

### legal:
If after assessing the communities involved, you've determined that
you want to move forward with the proejct, then you want to think
about legality.

What is legal? Basically, there are two questions.
- First, is the data publically accessible (this is distinct from
  "open" or "free" data which are closely related concerns and contain
  their own complexities)
- Second, does the data publisher permit scraping or mining their
  data? For this, you'd need to check the `robots.txt` file (more on
  this below), and in the absence of that, the "Privacy" or "Terms of
  Service" pages on the website.
  
If the answer is yes to both of these questions, then scraping (and
perhaps even publishing) that data is entirely legal. If the answer is
no to any of them, then your project run the risk of violating the
law.

All of this being said, it is important to point out that copyright
law protects making copies of information for the purpose of academic
research. This means that, provided you do not distribute or publish
the data in any public way, you can scrape information for your own
private study. See more under the "[Fair
Use](https://www.copyright.gov/fair-use/)" description at the US
Copyright Office. 

## not everything legal is ethical
It's worth re-iterating the importance of ethics. Just because
something legally can be scraped doesn't mean it should be
scraped. The most important consideration, more important that
legality (in my view) is how copying, analyzing, and/or publishing
that data affects the groups to whom that data pertains. Be thoughtful
about the potential effects of collecting that data and making it
available. If it makes an already marginalized group more vulnerable,
don't scrape it.

## anti-trans legislation
I'm going to demonstrate this process using my project on the *Trans
Legislation Tracker* as an example.

After making the assessment that the project wouldn't harm any
marginalized grous, I sought out some websites that were legally
scrapable. By checking the `robots.txt` file for each site, I was able
to see which ones prohibited scraping. To check this file, just append
`robots.txt` to the root of the URL (following the `.com` or `.org`). 

For example, the [Bill Track 50](https://www.billtrack50.com/) website
prohibited scraping with the following declaration:

```
User-agent: *
Disallow: /
```

Here, the asterisk is a "wild card," which means that it applies to
*all* user-agents, which means all users. Similarly, the `/` in
"disallow" indicates all possible paths. Together, this definitively
shuts the door to all scrapers: it means that all users, no matter who
they are, cannot access any possible page created from the root URL,
including the root itself. 

START HERE

EVEN IF SCRAPING IS LEGAL, THERE ARE STILL OBSTACLES. LIKE BOT
BLOCKERS

ANOTHER OBSTACLE, DYNAMIC WEB INTERFACES. 

I was interested in websites that provided tracking data
for the trans legislation. These included the following web pages:
- ACLU's "[Mapping Attacking on LGBTQ Rights in US State
  Legislatures](https://www.aclu.org/legislative-attacks-on-lgbtq-rights)"
- Equality Federation's "[Anti-Transgender
  Legislation](https://www.equalityfederation.org/tracker/cumulative-anti-transgender)"
- Track Trans Legislation's "[2023 Anti-Trans
  Legislation](https://www.tracktranslegislation.com/)"
- National Center for Transgender Equality's "[State Action
  Center](https://transequality.org/state-action-center)" 
- Trans Leglislation Tracker's "[2023 anti-trans bills
  tracker](https://translegislation.com/)"
  
Of the above websites, all were legally scrapable. 

As it turns out, most websites prohibit scraping in some form. The
conventional way of finding out if a website

3# ethics

## what is legal? what is ethical?
The question is crucial needs to be asked *prior* to scraping. There's
a lot to know about the ethics and legality of web scraping, which I
will not reproduce here. For an excellent explanation, check out
University of Michigan's
[guidebook](https://docs.google.com/document/d/11LZweIYD9MmjiZgY-VW1IXUPOP1k-SwXNiOdJDVC7Vw/edit#heading=h.ut4ttuudwb6i)
on the ethics and legality of web scraping.

What follows is a brief overview of the most important questions you
should ask yourself as you begin a new web scraping project.

### ethical: 
Before you even start thinking about legality, you want to spend some
time thinking carefully about *who* your data pertains to (who is the
data about?) and how gathering, doing analysis, and/or publishing that
dataset will affect the groups involved. You especially want to do
this work if your project involves marginalized communities. 

Here are some basic questions you want to ask at the start of a web
scraping project:
- Whose data am I scraping? Who owns the data? (often times, the
  data's owner is not the same as the person/group it describes)
- Is the data public or private data? Does it contain any personally
  identifying characteristics?
- What will I do with the data? (gather it, analyze it, publish it
  online, all of the above, etc.)
- What will be the effect of my actions on the group that the data
  describes?

The most important thing is to **assess any vulnerabilities about the
people directly associated with the data**. And this can only be
answered on a case by case basis. There is no hard and fast rule that
applies to all groups.

For example, if you are scraping data about indigenous populations
across the United States, remember that these groups are
understandably protective of their information and may not want it to
be made public. In that case, you could reach out to the groups
directly and ask permission, or you can commit to keeping the data
private (doing analysis on your own) and only publish the results of
the analysis.

Another example, the *Trans Legislation Tracker*, is a different
case. Collecting and publishing this data brings awareness and
attention to the issue of trans discrimination, which benefits the
group that the data describes. And additionally, the end goal of this
project---which is to do a text analysis of terms like "gender" and
"sex" in the bills---creates an opportunity to examine the ways that
language is being used to oppress and limit them.

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
scraped. The most important consideration, more important than
legality (in my view) is how copying, analyzing, and/or publishing
that data affects the groups to whom that data pertains. Be thoughtful
about the potential effects of collecting that data and making it
available. In what ways could that data be used for exploitation or
further extraction? If it makes an already marginalized group more
vulnerable, don't scrape it.

## anti-trans legislation
Once you've assessed the ethics of your project, negotiating legality
is also its own process. I'm going to demonstrate this process by
example, using trans legislation as a test case.

After making the assessment that this project (scraping anti-trans
legislation) wouldn't harm any marginalized grous, I sought out some
websites that were legally scrapable. By checking the `robots.txt`
file for each site, I was able to see which ones prohibited
scraping. To check this file, just append `robots.txt` to the root of
the URL (the "root" is the part of the URL that ends with `.com` or
`.org`, etc.).

For example, the [Bill Track 50](https://www.billtrack50.com/) website
has its `robots.txt` at
`https://www.billtrack50.com/robots.txt`. Checking the file shows that
the website totally prohibits scraping with the following declaration:

```
User-agent: *
Disallow: /
```

Here, the "user-agent" refers to the entity looking at the website,
whether that be a person or a bot. The asterisk is a "wild card,"
which means that it applies to *all* user-agents. 

The "disallow" line indicates which parts of the websites are off
limits. The `/` in "disallow" means that all possible paths--that
means, all possible sites contained under the root `billtrack50.com`,
are off limits. Together, the user-agent and disallow declarations
definitively shut the door to all scrapers: it means that all users,
no matter who they are, cannot access any possible page created from
the root URL, including the root itself.

Even if scraping is legal, there can still be a few obstacles. One of
them is the use of "bot blockers," which will prevent web scraping by
feeding the wrong information (usually a blank webpage) to the
scraper. For example, [Congress.gov(https://www.congress.gov/) does
this, even though the federal legislation contained on this site is
technically in the public domain. It does offer a [Congress.gov
API](https://blogs.loc.gov/law/2022/09/introducing-the-congress-gov-api/),
which is a good option for those who want legislative data.

Here's a brief look at *Track Trans Legislation*'s `robots.txt` file,
which mostly allow scraping. It does have some limits, but only
on the `admin` and `bill-logs` paths. Everything else on the site is
fair game:

```
User-agent: *
Disallow: /admin/
Disallow: /bill-logs
```

However, even if sites are legally scrapable, they are not technically
scrapable due to a dynamic web interface. Because many scrapers work
with static HTML (that is, HTML that has been rendered on the page),
it cannot capture dynamic elements like those contained in JavaScript
code. Those elements include their own processes, like their own APIs,
which is not present in the static version of the website code. A good
way of telling whether a webpage is dynamic or static is to notice any
interactive or moving elements. For example, if a webpage has a
scrollable box, popup windows, or a search bar, then very likely the
information contained there is dynamically produced and cannot be
captured with typical web scrapers. (There's an exception to this, see
[Selenium](https://www.selenium.dev/).

Here are some sites which legally allow some scraping, but technically
make it difficult due to a dynamic interface:
- ACLU's "[Mapping Attacking on LGBTQ Rights in US State
  Legislatures](https://www.aclu.org/legislative-attacks-on-lgbtq-rights)"
- Equality Federation's "[Anti-Transgender
  Legislation](https://www.equalityfederation.org/tracker/cumulative-anti-transgender)"
- Track Trans Legislation's "[2023 Anti-Trans
  Legislation](https://www.tracktranslegislation.com/)"

By contrast, here are sites whose relevant elements are in static
format, so they are scrapable. 
- National Center for Transgender Equality's "[State Action
  Center](https://transequality.org/state-action-center)" 
- Trans Leglislation Tracker's "[2023 anti-trans bills
  tracker](https://translegislation.com/)"
  
The second site, *Trans Legislation Tracker* will be our target for
scraping due to its static nature and to the wonderfully open
declaration its its `robots.txt`:

```
User-agent: *
Allow: /
```

No other declaration could be more permissive than that.

# what is ethical? what is legal?
These questions are crucial needs to be asked *prior* to scraping. There's a lot intricacies about the ethics and legality (especailly legality) of web scraping, which I will not reproduce here. For an excellent explanation, check out University of Michigan's [guidebook](https://docs.google.com/document/d/11LZweIYD9MmjiZgY-VW1IXUPOP1k-SwXNiOdJDVC7Vw/edit#heading=h.ut4ttuudwb6i) on the subject.

What follows is a brief overview of the process for determining an ethical and legal approach to scraping. The process begins with a list of questions you should ask yourself at the outset of any project.

## ethical: 
Before you even start thinking about legality, you want to spend some time thinking carefully about *who* your data pertains to (who is the data about?) and how gathering, doing analysis, and/or publishing that dataset will affect the groups involved. You especially want to do this work if your project involves communinities that are marginalized in any way. 

Here are some basic questions you want to ask yourself at the start of a web scraping project:
- Whose data am I scraping? Who owns the data? (often times, the data's owner is not the same as the person/group it describes)
- Is the data public or private data? Does it contain any personally identifying characteristics?
- What will I do with the data? (gather it, analyze it, publish it online, all of the above, etc.)
- What will be the effect of my actions on the group that the data describes?

The most important thing is to **assess any vulnerabilities about the people directly associated with the data**. And this can only be answered on a case by case basis. There is no standard that applies to all groups.

Regardless of your goals, you want to consider whether any information that you extract can be repurposed for monetary value or surveillance purposes. In other words, you want to consider how the data which you scrape could be a dataset that someone (or a company) would want to buy for data analysis and/or monitoring purposes. If the answer is yes, that doesn't mean you have to scrap the project. It does mean that you should think about how you use that data, and particularly not to publish or share the dataset. 

This is more difficult to guage, but you want to also think about the group of people your data is about, and how they might want someone to use their data. For example, if you are scraping data about indigenous populations across the United States, remember that these groups are understandably protective of their information and may not want it to be made public. In that case, you could reach out to the groups directly and ask permission, or you can commit to keeping the data private (doing analysis on your own) and only publish the results of the analysis.

Another example, the *Trans Legislation Tracker*, is a different case. Collecting and publishing this data brings awareness and attention to the issue of trans discrimination, which benefits the group that the data describes. And additionally, the end goal of this project---which is to do a text analysis of terms like "gender" and "sex" in the bills---creates an opportunity to examine the ways that language is being used to oppress and limit them.

The most important consideration, more important than legality (in my view) is how copying, analyzing, and/or publishing that data affects the groups to whom that data pertains. Be thoughtful about the potential effects of collecting that data and making it
available. In what ways could that data be used for exploitation or further extraction? If it makes an already marginalized group more vulnerable, be careful about what you decide to do with that data.

## legal:
If after assessing the communities involved, you've determined how you want to move forward with the project in an ethical way, then you want to think about legality.

What is legal? Basically, there are two questions.
- First, is the data publically accessible (this is distinct from "open" or "free" data, each which contain their own complexities)
- Second, does the data publisher permit scraping or mining their data? For this, you'd need to check the `robots.txt` file (more on this below), and in the absence of that, the "Privacy" or "Terms of Service" pages on the website, and make sure to check the website thoroughly. For the Princeton University Library, for example, scraping is clearly prohibited in a "Copyright and Access" section on the sidebar. 
  
If the answer is yes to both of these questions, then scraping (and perhaps even publishing, but you'd want to check that too) the data is entirely legal. If the answer is no to any of them, then your project *may* run the risk of violating the law.

Of course, it is important to remember that copyright law protects making copies of information for the purpose of academic research. This means that, provided you do not distribute or publish the data in any public way, you can scrape information for your own private study. See more under the "[Fair Use](https://www.copyright.gov/fair-use/)" description at the US
Copyright Office.

## not everything legal is ethical: exhibit A(I)
It's worth re-iterating the importance of ethics. Just because something legally can be scraped, analyzed and/or published doesn't mean it should be scraped, analyzed, and/or published.

For example, the web scraping processes being used to train the very popular generative AI tools like *Chat GPT*. These companies take data from every corner of the web, use it to train their language and vision models, and then sell that technology back to the user. They do this without any compensation to their data sources, not even when the sources include [works of literature](https://authorsguild.org/news/ag-and-authors-file-class-action-suit-against-openai/) or [openly licensed software](https://githubcopilotlitigation.com/), which is often stipulated for non-commercial use.

Perhaps the worst offenders of scraping are those who use that data for surveillance and policing purposes, like for creating facial recognition software. For example, Clearview AI infamously [scraped images from social media to sell to law enforcement](https://www.technologyreview.com/2021/04/09/1022240/clearview-ai-nypd-emails/), who has been using the images in ways that violate privacy and exacerbate racial profiling. 

## anti-trans legislation
Once you've assessed the ethics of your project, legality and logistics is the next step. This can be a complicated process, with some potential roadblocks. I'm going to demonstrate how to negotiate the process by the example of trans legislation.

After making the assessment that this project (scraping anti-trans legislation) wouldn't harm any marginalized grous, I sought out some websites that were legally scrapable. By checking the `robots.txt` file for each site, I was able to see which ones prohibited scraping. To check this file, just append `robots.txt` to the root of the URL (the "root" is the part of the URL that ends with `.com` or `.org`, etc.).

Below is an example that totally prohibits web scraping. Here, the [Bill Track 50](https://www.billtrack50.com/) website has its `robots.txt` at `https://www.billtrack50.com/robots.txt` contains the following declaration:

```
User-agent: *
Disallow: /
```

The "user-agent" refers to the entity looking at the website, whether that be a person or a bot. The asterisk is a "wild card," which means that it applies to *all* user-agents. 

The "disallow" line indicates which parts of the websites are off limits. The `/` in "disallow" means that all possible paths--that means, all possible sites contained under the root `billtrack50.com`, are off limits. Together, the user-agent and disallow declarations definitively shut the door to all scrapers: it means that all users,no matter who they are, cannot access any possible page created from the root URL, including the root itself.

Here's an example from another contender for scraping, *Track Trans Legislation*, which mostly allows scraping. It does have some limits, but only on the `admin` and `bill-logs` paths. Everything else on the site is fair game:

```
User-agent: *
Disallow: /admin/
Disallow: /bill-logs
```

However, even if the website is legally scrapable, it may not be *technically* scrapable, which I quickly discovered when I tried to scrape the *Track Trans Legislation* site. The reason has to do with its "dynamic" web interface. Because many scrapers work with static HTML (that is, HTML that is rendered just once on the page), it cannot capture dynamic elements like those contained in JavaScript code. You can quickly tell if a site has dynamic elements if it has scrollable boxes, buttons, search bars, or something else that changes or updates in place without reloading the whoel page. Those elements include their own processes, like their own APIs, which is not present in the static version of the website code. The information contained in dynamic websites cannot be captured with typical web scrapers. The exception to this is [Selenium](https://www.selenium.dev/), which works by simulating a browser where elements can then be "clicked" and interacted with.

Dynamic websites are popular, and unfortunately for me, there were quite a few of them about my topic which, while legally permissible, I couldn't scrape:
- ACLU's "[Mapping Attacking on LGBTQ Rights in US State Legislatures](https://www.aclu.org/legislative-attacks-on-lgbtq-rights)"
- Equality Federation's "[Anti-Transgender Legislation](https://www.equalityfederation.org/tracker/cumulative-anti-transgender)"
- Track Trans Legislation's "[2023 Anti-Trans Legislation](https://www.tracktranslegislation.com/)"

Besides dynamic websites, another obstacle is the use of "bot blockers," which guards against web scraping by feeding the wrong information (usually a blank webpage) to the scraper. For example, the [Congress.gov](https://www.congress.gov/) website does this, even though the federal legislation contained on this site is technically in the public domain. It does offer a [Congress.gov API](https://blogs.loc.gov/law/2022/09/introducing-the-congress-gov-api/), which is a good option for those who want legislative data.

At the end of my search, I was left with the following two sites that contained the data I want in a logistically scrapable (that is, static) format: 
- National Center for Transgender Equality's "[State Action Center](https://transequality.org/state-action-center)" 
- Trans Leglislation Tracker's "[2023 anti-trans bills tracker](https://translegislation.com/)"
  
I selected the second site, *Trans Legislation Tracker*, due to its wonderfully open declaration in its `robots.txt` file:

```
User-agent: *
Allow: /
```

Nothing could be more permissive than that.

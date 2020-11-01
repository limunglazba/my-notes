
Python Packages
============


### Scrapy

#### Terminal commands
| Command | Description | Type |
| ------- | ----------- | ----------- |
| `scrapy startproject <project name> [project dir] ` | Create a new Scrapy project | Global command |
| `scrapy shell [url]` | Scrape [url] within interactive terminal for interactive testing and debugging | Global command |
| `scrapy crawl [spider name]` | Run your [spider] | Project-only command |

#### Creating a Project - Steps
**1. Start a new project in the terminal**
```cmd
scrapy startproject <project name> [project dir]
```

#### Settings.py
| Command | Description |
| ------- | ----------- |
| `USER_AGENT` | Identity of the person sending requests |
| `ROBOTSTXT_OBEY` | True = obeys website's scraping rules as set in their robots.txt |

#### Items.py
| Command | Description |
| ------- | ----------- |
| `Class Item` | Class should contain fields for the item we're scraping |

#### Pipeline.py
- Defines how scraped items are saved

#### Middlewares.py
- For adding extra stuff to the request (e.g. proxies) or for manipulating the received data before sending it to pipeline.py

#### Spiders folder
- Put your spiders in this folder

#### Selectors & scraping
- css and xpath selectors can be used in combination in Scrapy

| Command | Description |
| ------- | ----------- |
| `response.css('tag.class').get()` | Selects class named *class* from html *tag* |
| `response.css('tag.class::text').get()` | Selects text within the 'class' |
| `response.css('tag.class::text').re(r'<regex>')` | Selects all <regex> expressions from the text within the 'class'. *re_first()* selects first regex expression. |
| `response.css('*::text').get()` | Selects all descendant text from the current selector |
| `response.css('tag.class::attr(href)').get()` | Selects attribute (href) from the class |
| `.get()` | Returns the first result. For no mathces, *None* is returned |
| `.getall()` | Returns a list with all results |

  
 ### Discord

- [Setting up automated messages with Discord's webhooks](https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks)

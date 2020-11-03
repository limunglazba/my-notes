Python Packages
============


### Scrapy [1](https://www.youtube.com/playlist?list=PLhTjy8cBISEqkN-5Ku_kXG4QW33sxQo0t)

#### Terminal commands
| Command | Description | Type |
| ------- | ----------- | ----------- |
| `scrapy startproject <project name> [project dir] ` | Create a new Scrapy project | Global command |
| `scrapy genspider <spider name> <domain> ` | Create a template spider used to crawl `<domain>`  | Global command |
| `scrapy shell [url]` | Scrape [url] within interactive terminal for interactive testing and debugging | Global command |
| `scrapy crawl [spider name]` | Run your [spider] | Project-only command |

#### Creating a Project: Main Steps
**1. Start a new project in the terminal**
  ```cmd
  scrapy startproject <project name> [project dir]
  ```
**2. Create your spider in the *spider* subfolder with a new class inhereting from scrapy.Spider, with**:
- *name* variable: name of your spider 
- *start_urls* variable: list of urls to scrape
- *parse* method: defines what Scrapy does with the response (Scrapy uses *yield* keyword instead of *return*) - see *Selectors & scraping*
- *allowed_domains* variable (optional): list of domains allowed to get scraped

```cmd
import scrapy

class TestSpider(scrapy.Spider):
    name = 'test'
    start_urls = [<url_for_scraping>]

    def parse(self, response):
        title = response.css('.test-css').extract()
        yield {'titletext': title}

```
**3. For storing scrapped data: in *items.py*, create item containers corresponding to the parsed fields from your spider (*title* in this example)**:

```cmd
class TestItem(scrapy.Item):
    title = scrapy.Field()
```
**4. For storing scrapped data: Import item class from *items.py* to your spider**:
```cmd
from ..items import TestItem

class TestSpider(scrapy.Spider):
    name = 'test'
    start_urls = [<url_for_scraping>]
    
    def parse(self, response):
        items = RepsItem()
        title = response.css('title::text').extract()
        items['title'] = title
        yield items
```

**5. For storing scrapped data: Enable ITEM_PIPELINES in *settings.py***

**6. For storing scrapped data: In *pipeline.py*, setup your database**

**7. For multiple pages: In your spider file, add instructions in the *parse* method**
```cmd
    next_page = response.css(<CSS_SELECTOR>::attr(href)).get()

    if next_page is not None:
        yield response.follow(next_page, callback=self.parse)
```
**8. OPTIONAL: Setup User Agents using scrapy-user-agents package in settings.py (requires pip install)** [1](https://pypi.org/project/scrapy-user-agents/)
  ```cmd
DOWNLOADER_MIDDLEWARES = {
    'scrapy.downloadermiddlewares.useragent.UserAgentMiddleware': None,
    'scrapy_user_agents.middlewares.RandomUserAgentMiddleware': 400,
}
  ```
- Alternatively, setup your own *USER_AGENT* variable in settings.py, like: [Google Bots](https://developers.whatismybrowser.com/useragents/explore/software_name/googlebot/)

**9. OPTIONAL: Setup Proxies using scrapy-proxy-pool package in settings.py (requires pip install)** [1](https://github.com/rejoiceinhope/scrapy-proxy-pool)
  ```cmd
DOWNLOADER_MIDDLEWARES = {
    'scrapy.downloadermiddlewares.useragent.UserAgentMiddleware': None,
    'scrapy_user_agents.middlewares.RandomUserAgentMiddleware': 400,
}
  ```
**10. OPTIONAL: Authenticate with Scrapy's forms >> TBD**

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

#### Various
- Inspect response within your spider (in the parse method) (1)[https://docs.scrapy.org/en/latest/topics/shell.html#invoking-the-shell-from-spiders-to-inspect-responses]
  ```cmd
  from scrapy.shell import inspect_response
  inspect_response(response, self)
  ```
  
### Scraping Resources
| Command | Description |
| ------- | ----------- |
| [Requestbin](https://requestbin.com/) | Collect HTTP or webhook requests (code testing) |

  
 ### Discord

- [Setting up automated messages with Discord's webhooks](https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks)


Python Packages
============


### Scrapy

#### Terminal commands
| Command | Description |
| ------- | ----------- |
| `scrapy startproject [project name]` | Create new Scrapy project |

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
| Command | Description |
| ------- | ----------- |
| `tag.class` | Selects class named 'class' from html <tag> |
| `ROBOTSTXT_OBEY` | True = obeys website's scraping rules as set in their robots.txt |

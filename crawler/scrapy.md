---
marp: true
theme: uncover
class:
  - lead
  - invert
---

<!-- <style type="text/css">
  .reveal p {
    text-align: left;
  }
  .reveal ul {
    display: block;
  }
  .reveal ol {
    display: block;
  }
</style> -->

### Effective Ways to Scale-Up and Maintain Your Web Crawling Project
Hao-Yun Chuang
Nov 4, 2022

---

## What you can bring home today
1. Tree structure displaying the directory path<br>
2. Maintain web crawling project using Scrapy<br>
3. Useful libraries and modules when parsing<br>

---

# Tree directory

----

![](https://i.imgur.com/jlv69an.png)

----

# How?

----

* For Mac user:
```bash=
brew install tree
```

----

* For Windows user:
<!-- ![](https://i.imgur.com/6nG7Eh8.gif) -->

Please refer to this [website](https://dev.to/flyingduck92/add-tree-to-git-bash-on-windows-10-1eb1)<br>
<img src="https://i.imgur.com/PglrmTJ.jpg" style="background:none; border:none; box-shadow:none; max-width:50%;">

----

# Now give it a try!
### Under any directory...
```bash=
(base) milanochuang@zhuanghaoyundeMacBook-Pro Documents % tree
```

---

## Use Scrapy in crawling project

----

# Scrapy
* **Fast & powerful**
Rules to extract the data and let Scrapy do the rest
* **Easily extensible**
extensible by design, plug new functionality easily without having to touch the core
* **Portable, Python**
written in Python and runs on Linux, Windows, Mac

----

# Start virtual Environment

----

## Find a directory you like and run
```bash=
python3 -m venv scrapy-tutorial
```

----

## Mac User
```bash=
source scrapy-tutorial/bin/activate
```

----

## Windows User
```bash=
scrapy-tutorial\Scripts\activate.bat
```

----

```bash=
git clone https://github.com/milanochuang/spider_tutorial.git
cd spider_tutorial
pip install -r requirements.txt
```

----

# Definition of Terms

----

* **Seed URL**: First page the spider starts with. 

----

* **Crawling**: visiting websites page to page <br>
:bulb: choose your **Christmas tree** 
<br>
* **Extraction**: parsing the data from a page <br>
:bulb: choose the **decorations** <br>

---

## Start crawling project

----

<center>
Find a directory and input in the cmd
</center>

```bash=
scrapy startproject books_to_scrape
```

<center>
You should see something like this...
</center>

```
New Scrapy project 'books_to_scrape', using template directory '/Users/milanochuang/opt/anaconda3/lib/python3.8/site-packages/scrapy/templates/project', created in:
    /Users/milanochuang/Documents/code/spider_tutorial/books_to_scrape

You can start your first spider with:
    cd books_to_scrape
    scrapy genspider example example.com
```
```bash=
cd books_to_scrape
```

----

![](https://i.imgur.com/jlv69an.png)

----

```bash=
scrapy genspider books books.toscrape.com
```
```
Created spider 'books' using template 'basic' 
```

----

```bash=
tree
```
![](https://i.imgur.com/3JVwR2d.png)

----

* You can now open the editor you like.
* Open the `books_to_scrape` directory (Outer)
* With your terminal at the same directory aside

---

## Scrapy flow (1)
* Begin at the seed url (books.toscrape.com)
* Extract all the books from this page
* Store the extracted data locally
    * run `scrapy crawl books -o data.json`
<!-- * Go through each category at the sidebar
    * Extract all the books in the categories
    * Structurize the data -->

----

### Let's open `books.py`

----

You should see something like this
```python=
# -*- coding: utf-8 -*-
import scrapy


class BooksSpider(scrapy.Spider):
    name = "books"
    allowed_domains = ["books.toscrape.com"]
    start_urls = ['http://books.toscrape.com/']

    def parse(self, response):
        pass
```

----

## Remember CSS path?
~~不可能忘記吧~~

----

CSS path of each book is `.product_pod a ::attr(href)`
```python=
import scrapy
class BooksSpider(scrapy.Spider):
    name = "books"
    allowed_domains = ["books.toscrape.com"]
    start_urls = ['http://books.toscrape.com/']

    def parse(self, response):
        for url in response.css(".product_pod a ::attr(href)").getall():
            yield response.follow(url, callback=self.parse_book)
```

----

## Have you noticed any new friend?

----

* `yield`: try this
```python=
power = (i**2 for i in range(100000))
print(power)
print(type(power))
```
```
<generator object <genexpr> at 0x7f8ddb35ec10>
generator
```

----

* `follow`
* `callback`

----

## Extract the book information

----

```python=
import scrapy
class BooksSpider(scrapy.Spider):
    name = "books"
    allowed_domains = ["books.toscrape.com"]
    start_urls = ['http://books.toscrape.com/']
    
    # 爬取目錄頁的每一本書的連結（挑聖誕樹）
    
    def parse(self, response):
        for url in response.css(".product_pod a ::attr(href)").getall():
            yield response.follow(url, callback=self.parse_book)
            
    # 爬取每一本書的資訊（挑裝飾品）
            
    def parse_book(self, response):
        item = {
            "title": response.css(".product_main h1 ::text").get(),
            "price": response.css(".product_main .price_color ::text").get(),
            "url": response.url,
            "availability": response.css(".product_main .availability ::text").getall()
        }
        yield item
```

----

### Run the code
```bash=
scrapy crawl books -o data.json
```

----

### Open the file, what happened?
![](https://i.imgur.com/4ifis1E.png)

----

### Shxt...sth went wrong, let's revise the code.
![](https://media.tenor.com/UF5GVNzdWIAAAAAd/doctor-strange-things-just-got-out-of-hand.gif)

----

```python=
def parse_book(self, response):
        item = {
            "title": response.css(".product_main h1 ::text").get(),
            "price": response.css(".product_main .price_color ::text").get(),
            "url": response.url,
        }
        availability = response.css(".product_main .availability ::text").getall()
        item["availability"] = "".join(availability).strip()
        yield item
```

----

### Let's try again.

----

![](https://i.imgur.com/L15u4ba.png)

----

![](https://media.tenor.com/KMxrZ-A6ev4AAAAM/nice-smack.gif)

---

## Scrapy flow (2)
* Begin at the seed url
* ~~Extract all the books from this page~~
* Go through each category at the sidebar
    * Extract all the books in the categories
    * Structurize the data
* Extract all the books for the page
* Store the extracted data locally
    * run `scrapy crawl books -o data.json`

----

Let's go back to our code.
```python=
import scrapy
class BooksSpider(scrapy.Spider):
    name = "books"
    allowed_domains = ["books.toscrape.com"]
    start_urls = ['http://books.toscrape.com/']
    
    def parse(self, response):
        for url in response.css(".product_pod a ::attr(href)").getall():
            yield response.follow(url, callback=self.parse_book)

            ...
```

----

### We need to find the CSS path of the categories

----

Let's modify our `parse` function.
```python=
def parse(self, response):
    for url in response.css(".nav-list ul li a ::attr(href)").getall():
        yield response.follow(url, callback=self.parse_category)
```

----

Let's create a new `parse_category` function.
```python=
def parse_category(self, response):
    for url in response.css(".product_pod a ::attr(href)").getall():
        category_name = response.css(".page-header h1 ::text").get()
            yield response.follow(
                url,
                callback=self.parse_book,
                cb_kwargs={"category_name": category_name},
            )
         if next_page_url := response.css(".pager .next a ::attr(href)").get():
                yield response.follow(
                    next_page_url,
                    callback=self.parse_category,
                )
```

----

## Have you noticed any new friend?

----

* `:=`

```python=
n = len(a)
if n>10:
    print(f"List is too long ({n} elements, expected <= 10)")
```
```python=
if (n := len(a)) > 10:
    print(f"List is too long ({n} elements, expected <= 10)")
```

----

* `cb_kwargs`

----

### Run the code
```bash=
scrapy crawl books -o data.json
```

----

![](https://media.tenor.com/KMxrZ-A6ev4AAAAM/nice-smack.gif)

---

## Let's try to improve our spider.

----

### Define items (what you scraped)
1. Scrapy's own item class
2. Python's dataclass
3. attrs library
4. ...

----

## Now go to `items.py`
You should see this...
```python=
import scrapy


class ScrapeBookItem(scrapy.Item):
    # define the fields for your item here like:
    # name = scrapy.Field()
    pass
```

----

# Delete them all

----

We are using Python's own dataclass today...
```python=
from dataclasses import dataclass
from typing import Optional

# from scrapy_jsonschema.item import JsonSchemaItem


@dataclass
class BookItem:
    url: str
    category_name: Optional[str] = None
    title: Optional[str] = None
    price: Optional[str] = None
    availability: Optional[str] = None
```
<!-- 這是因為 url 是在我們所要爬的資料中一定會有的欄位，所以將他設定為必須有的資料，至於其他則是將它設定為 optional，這樣即使爬到沒有的資料，也不會影響爬蟲對資料的爬取 -->

----

Back to `books.py`...
```python=
from books_to_scrape.items import BookItem
# change the code below
...
    yield item

# into
...
    yield BookItem(**item)
```

----

Run `scrapy crawl books -o data.json`

<!-- 結果跟之前會是一樣的，這是因為我們還沒有在先前的dataclass再做詳細定義-->

----

### Let's explore a little bit more
```python=
...
        breakpoint()
        yield BookItem(**item)
```
```bash=
BookItem(**item)
BookItem(**item, **{"unknown": "value"})
BookItem(title="Alice in wonderland")
```

---

## Decoupling parsing from crawling
* Concept of Page Objects!
* Make simpler code
* spider focus on crawling
* Page Object focus on extraction

```bash=
pip install web-poet scrapy-poet
```

----

Create a new pyfile called `page_objects.py`...
```python=
from web_poet import ItemWebPage
from books_to_scrape.items import BookItem # moved from books.py

class BookPage(ItemWebPage):
    def to_item(self):
        item = {
            "title": self.css(".product_main h1 ::text").get(),
            "price": self.css(".product_main .price_color ::text").get(),
            "url": self.url,
        }
        availability = self.css(".product_main .availability ::text").getall()
        item["availability"] = "".join(availability).strip()
        return BookItem(**item)
        
```

<!-- Web poet implements Page Object pattern for web scraping -->

----

add the config below at the bottom of `setting.py`
```python=
DOWNLOADER_MIDDLEWARES = {
    'scrapy_poet.InjectionMiddleware': 543,
}
SPIDER_MIDDLEWARES = {
    "scrapy_poet.RetryMiddleware": 275,
}
```

----

In `books.py`...
```python=
from books_to_scrape.page_objects import BookPage

...

def parse_book(self, response, page: BookPage, category_name):
    item = page.to_item()
    item.category_name = category_name
    yield item
```

Run the code to see if it works.
<!-- Scrapy poet 在看到page: BookPage時，就會知道要去呼叫 BookPage 的 class -->

----

### Let's modify other page with web_poet

----

In `page_object.py`...
```python=
from web_poet import ItemWebPage, WebPage

class HomePage(WebPage):
    @property
    def category_urls(self):
        return self.css(".nav-list ul li a ::attr(href)").getall()


class BookCategoryPage(WebPage):
    @property
    def book_urls(self):
        return self.css(".product_pod a ::attr(href)").getall()

    @property
    def category_name(self):
        return self.css(".page-header h1 ::text").get()

    @property
    def next_page_url(self):
        return self.css(".pager .next a ::attr(href)").get()
```

----

In `books.py`...
```python=
import scrapy

from books_to_scrape.page_objects import HomePage, BookCategoryPage, BookPage
...

    def parse(self, response, page: HomePage):
        for url in page.category_urls:
            yield response.follow(url, callback=self.parse_category)

    def parse_category(self, response, page: BookCategoryPage):
        for url in page.book_urls:
            yield response.follow(
                url,
                callback=self.parse_book,
                cb_kwargs={"category_name": page.category_name},
            )

            if next_page_url := page.next_page_url:
                yield response.follow(
                    next_page_url,
                    callback=self.parse_category,
                )

    def parse_book(self, response, page: BookPage, category_name):
        item = page.to_item()
        item.category_name = category_name
        yield item
```
<!-- 這麼做可以增加程式的維護性，因為網頁很有可能在未來會改變結構 -->

----

# Let's compare the code with the first version.

---

# Some other feature

----

## When you have multiple spiders...
* You'll need to **manage** and **visualize** the activities
    * schedule periodic runs
    * view current and finished runs
    * search through the extracted items, logs & stats
    * easy to debug
    * visualize the running performance

----

## Monitoring the spider

* Custom monitors
* Support notification via Slack, Telegram, Discord, Email

Run: 
```bash=
pip install spidermon
```

----

In `books.py`...
```python=
...
    start_urls = ['http://books.toscrape.com/']
    custom_settings = {
        "SPIDERMON_ENABLED": True,
        "EXTENSIONS": {
            "spidermon.contrib.scrapy.extensions.Spidermon": 500,
        },
        "SPIDERMON_SPIDER_CLOSE_MONITORS": "spidermon.contrib.scrapy.monitors.SpiderCloseMonitorSuite",
        "SPIDERMON_MIN_ITEMS": 10,
        "SPIDERMON_MAX_ERRORS": 1,
        "SPIDERMON_MAX_WARNINGS": 1000,
        "SPIDERMON_ADD_FIELD_COVERAGE": True,
    }

    def parse(self, response, page: HomePage):
...
```

----

![](https://i.imgur.com/V7p3JoS.png)

----

![](https://i.imgur.com/gJDSjxI.png)

----

## Add schema validation
* Ability to write custom schema validations per item
* Use JSON schema to define data format
* CONS: not compatible with dataclass or attrs library
Run: `pip install jsonschema scrapy-jsonschema`

----

In `items.py`...

```python=
from scrapy_jsonschema.item import JsonSchemaItem

class BookSchemaItem(JsonSchemaItem):
    jsonschema = {
        "$schema": "http://json-schema.org/draft-07/schema#",
        "title": "Book",
        "description": "A Book item extracted from books.toscrape.com",
        "type": "object",
        "properties": {
            "url": {
                "description": "Book's URL",
                "type": "string",
                "pattern": "^https?://[\\S]+$"
            },
            "category_name": {
                "description": "Name of the category which the book belongs to",
                "type": "string"
            },
            "title": {
                "description": "Book's title",
                "type": "string"
            },
            "price": {
                "description": "Book's price",
                "minimum": 0,
                "type": "number"
            },
            "availability": {
                "description": "Book's availability",
                "type": "string"
            }
        },
        "required": ["url"]
    }
```

----

In `page_objects.py`...
```python=
from books_to_scrape.items import BookItem, BookSchemaItem
...
# change
return BookItem(**Item) 
# to
return BookSchemaItem(**Item)
```

----

In `books.py`...
```python=
# delete the custom monitor setting

...
def parse_book(self, response, page: BookPage, category_name):
    item = page.to_item()
    item['category_name'] = category_name
    yield item
```
<!-- This is because json schema does not accept field attribute -->

---

## What about dynamic page?

----

```bash=
scrapy genspider quotes quotes.toscrape.com
pip install scrapy-playwright
playwright install
sudo playwright install-deps
```

----

In `quotes.py`...
```python=
class QuotesSpider(scrapy.Spider):
    name = 'quotes'
    allowed_domains = ['quotes.toscrape.com']

    custom_settings = {
        "DOWNLOAD_HANDLERS": {
            "http": "scrapy_playwright.handler.ScrapyPlaywrightDownloadHandler",
            "https": "scrapy_playwright.handler.ScrapyPlaywrightDownloadHandler",
        },
        "TWISTED_REACTOR": "twisted.internet.asyncioreactor.AsyncioSelectorReactor",
    }

    def start_requests(self):
        yield scrapy.Request(
            "http://quotes.toscrape.com/js",
            callback=self.parse,
            meta={"playwright": True},
        )

    def parse(self, response):
        for quote in response.css(".quote .text ::text").getall():
            yield {"quote": quote}
```

---

# Helper libraries

----

```python=
from number_parser import parse
print(parse("One two three go!"))
print(parse_number("twenty three"))
print(parse_ordinal("seventy fifth"))
```
```
'1 2 3 go!'
23
75
```

----

```python=
from price_parser import Price, parse_price
print(Price.fromstring("22,90 €"))
```
```
Price(amount=Decimal('22.90'), currency='€')
```

----

```python=
import dateparser
dateparser.parse("Fri, 12 Dec 2014 10:55:50")
```
```
datetime.datetime(2014, 12, 12, 10, 55, 50)
```

----

```python=
import requests, extruct
page = requests.get("https://tw.pycon.org/2022/en-us")
print(extruct.extract(page.text))
```

----

```bash=
deactivate
```

----

# [Full Code](https://github.com/milanochuang/Scrapy_tutorial)

----

## Source:
* [Effective Ways to Scale-Up and Maintain Your Web Crawling Project｜Kevin Lloyd Bernal｜PyCon APAC 2022
](https://www.youtube.com/watch?v=pLucY2PoSts&list=PLqtzN042QpfdkQbkOlwtEJMBGZHHsvimo&index=20)
* [Python 裡的 yield — 讓你簡單、快速瞭解 yield 的概念](https://chriskang028.medium.com/python-裡的-yield-讓你簡單-快速瞭解-yield-的概念-f660521f3aa7)
* [Scrapy Documentation](https://docs.scrapy.org)

---

<!-- <style type="text/css">
  .reveal p {
    text-align: left;
  }
  .reveal ul {
    display: block;
  }
  .reveal ol {
    display: block;
  }
</style> -->

# Debug note

----

## if this happens...
```
ERROR: Loading "scrapy.core.downloader.handlers.http.HTTPDownloadHandler" for scheme "https"
```
## or this...
```
ModuleNotFoundError: No module named 'attrs'
```
## try run
```
pip install Twisted==21.7.0
```


## How to Web Scrape with Python ?

Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort.
In this article, we will go through an easy example of how to automate downloading hundreds of files from the New York MTA. This is a great exercise for web scraping
beginners who are looking to understand how to web scrape. Web scraping can be slightly intimidating, so this tutorial will break down the process of how to go about 
the process.


### Important notes about web scraping:

1. Read through the website’s Terms and Conditions to understand how you can legally use the data. Most sites prohibit you from using the data for commercial purposes.

2. Make sure you are not downloading data at too rapid a rate because this may break the website. You may potentially be blocked from the site as well.

### Inspecting the Website

The first thing that we need to do is to figure out where we can locate the links to the files we want to download inside the multiple levels of HTML tags. 
Simply put, there is a lot of code on a website page and we want to find the relevant pieces of code that contains our data. If you are not familiar with HTML tags,
refer to W3Schools Tutorials. It is important to understand the basics of HTML in order to successfully web scrape.

### Python Code

1.start by importing the following libraries

2.set the url to the website and access the site with our requests library.

3.Next we parse the html with BeautifulSoup so that we can work with a nicer, nested BeautifulSoup data structure. If you are interested in learning more
about this library

4.We use the method .findAll to locate all of our <a> tags.

soup.findAll('a')
  
5.extract the actual link that we want. Let’s test out the first link.

one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]
  
6.we should include this line of code so that we can pause our code for a second so that we are not spamming the website with requests. This helps us
  avoid getting flagged as a spammer.

time.sleep(1)
  

## How to Scrape Websites Without Getting Blocked
  
  Web scraping is a task that has to be performed responsibly so that it does not have a detrimental effect on the sites being scraped. Web Crawlers can 
  retrieve data much quicker, in greater depth than humans, so bad scraping practices can have some impact on the performance of the site. While most websites
  may not have anti-scraping mechanisms, some sites use measures that can lead to web scraping getting blocked, because they do not believe in open data access.
  
  
1. Respect Robots.txt
  
2.Make the crawling slower, do not slam the server, treat websites nicely
  
3.Do not follow the same crawling pattern
  
4.Make requests through Proxies and rotate them as needed
  
5.Rotate User Agents and corresponding HTTP Request Headers between requests
  
6.Use a headless browser like Puppeteer, Selenium or Playwright
  
7.Beware of Honey Pot Traps
  
8.Check if Website is Changing Layouts
  
9.Avoid scraping data behind a login
  
10.Use Captcha Solving Services
  
  
  
### How can websites detect web scraping?
  
  Websites can use different mechanisms to detect a scraper/spider from a normal user. Some of these methods are enumerated below:

1. Unusual traffic/high download rate especially from a single client/or IP address within a short time span.
  
2. Repetitive tasks performed on the website in the same browsing pattern – based on an assumption that a human user won’t perform the same repetitive tasks all 
  the time.
  
3.Checking if you are real browser – A simple check is to try and execute javascript. Smarter tools can go a lot more and check your Graphic cards and CPUs 
 to make sure you are coming from real browser.
  
4. Detection through honeypots – these honeypots are usually links which aren’t visible to a normal user but only to a spider. When a scraper/spider tries to 
  access the link, the alarms are tripped.

### How do you find out if a website has blocked or banned you ?
  
If any of the following signs appear on the site that you are crawling, it is usually a sign of being blocked or banned.

1. CAPTCHA pages
  
2. Unusual content delivery delays
  
3.Frequent response with HTTP 404, 301 or 50x errors
  
  
 Frequent appearance of these HTTP status codes is also indication of blocking

.301 Moved Temporarily
  
.401 Unauthorized
  
.403 Forbidden
  
.404 Not Found
  
.408 Request Timeout
  
.429 Too Many Requests
  
.503 Service Unavailable
  

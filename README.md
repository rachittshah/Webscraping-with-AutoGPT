# Web Scraping With Python

<img src="/Images/01-Intro_Image.jpg" alt="drawing"/>

**Table of contents:**

<!--ts-->
  * [Objective](#objective)
  * [Motivation](#motivation)
  * [How Does It Work?](#how-does-it-work)
  * [HTML (Optional)](#html-optional)
  * [Web Scraping Workflow](#web-scraping-workflow)
  * [Ethics of Scraping](#ethics-of-scraping)
  * [References](#references)
  * [Feedback](#feedback)
<!--te-->

<br>

## Objective

This tutorial aims to show how to use the Python programming language to web scrape a website. Specifically, we will use the `requests` and `Beautiful Soup` libraries to scrape and parse data from [companiesmarketcap.com](https://companiesmarketcap.com/) and retrieve the “*Largest Companies by Market Cap*”.

We will learn how to scale the web scraping process by first retrieving the first company/row of the table, then all companies on the website’s first page, and finally, all 6024 companies from multiple pages. Once the scraping process is complete, we will preprocess the dataset and transform it into a more readable format before using `matplotlib` to visualise the most important information.

<br>

## Motivation

Web scraping is a technique employed to extract large amounts of data from the Web using intelligent automation. Nowadays, web scraping is an essential tool for data scientists as it can be used to potentially source hundreds, millions, or even billions of data points from the Internet’s seemingly endless frontier.

<br>

## How Does It Work?

The first step in performing web scraping involves understanding what a web page is. Simply put, a web page is a text document provided by a website and displayed to a user in a web browser. Such documents are written in the [HTML language](https://html.com/).

HTML (which stands for HyperText Markup Language) is the most fundamental building block of the World Wide Web. It is the underlying source code of all web pages (along with CSS and JavaScript) as it encodes the displayed content and the overall structure of a web page. HTML documents are files that end with a .html or .htm extension. We can easily access the HTML source code using our browser's ‘view page source’ or ‘inspect’ tools.

Finally, a web scraper is a computer program that can understand an HTML document, parse it and extract useful information. To build a successful web scraper, we need at least a basic knowledge/understanding of HTML. If you are already familiar with HTML, you can skip the following section.

<br>

## HTML (Optional)

An HTML file is made of the so-called elements. An element represents semantics or meaning. Typically, an element includes an opening tag enclosed in angle brackets (\<tag>) and a closing tag enclosed in angle brackets but with a forward slash preceding the tag (\</tag>). The content of an HTML element is the information between its opening and closing tags.

```
<tag_name>Content</tag_name>
```

Elements in HTML can have attributes, i.e. values added to the opening tag to define additional characteristics or properties of the element. HTML attributes consist of a name and a value using the following syntax: name = "value".

```
<tag_name attribute_name="value">Content</tag_name>
```

Everything written in HTML is either an element or contained in an element (or both). In other words, HTML is organised into a family tree structure since HTML elements can have parents, grandparents, siblings, children, grandchildren, etc.

```
<body>
  <div>
    <h1>It's div's child and body's grandchild</h1>
    <h2>It's h1's sibling</h2>
  </div>
</body>
```
Note that the code is formatted such that the indentation level of text increases once for each level of nesting.

Every HTML file must have one grand/root element called \<html>. This element contains all other elements of the document. It is necessary that `<html>` always has two child elements:
  
- The \<head> element: a container for metadata, i.e. information about an HTML page that is not displayed on the web page itself.
- The \<body> element: represents the main content of an HTML document displayed on the browser.
  
```
<html>
  <head>
    <!-- META INFORMATION goes here -->  
  </head>
  <body>
    <!-- PAGE CONTENT goes here -->
  </body>
</html>
```  
  
For more information, please use the links in the References section of the notebook.

<br>
  
## Web Scraping Workflow

The workflow for web scraping with Python can be divided into the following three steps:
  
1. **Obtaining the HTML**: Firstly, we need to send an HTTP request to the web page server that we want to scrape. If the request is successful, the server will respond with the HTML content of the page.
  
2. **Parsing the HTML**: Most of the obtained HTML data is nested, making it difficult to extract information using stand string processing techniques. Instead, we need a parser, i.e. an algorithm designed to parse the HTML and create a parse/syntax tree of the HTML data.
  
3. **Extracting the Data**: Once the syntax tree is created, we need to navigate it and retrieve the information that we are interested in

To complete those steps, we need two third-party Python libraries:
1. **[Requests](https://docs.python-requests.org/en/master/)**: a simple but powerful library for sending all kinds of HTTP requests to a web server,
  
2. **[Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)**: a library for parsing HTML and XML documents. It works with a user-selected parser to provide idiomatic ways of navigating, searching, and modifying the parse tree.

<br>
  
## Ethics of Scraping
  
Web scraping is a powerful tool that should be used responsibly. Below is a list of things to consider before we start scraping data:
  
1.	Always check the robots.txt file of the site you are about to scrape, as it contains guidelines on how bots should behave on the website.
  
2.	Do not spam the website with multiple requests in a short amount of time, as that may hurt their server(s) and/or may be classified as a DDOS attack. If you need to scrape multiple pages, you can artificially limit the rate of requests, as we will show in the code.
  
3.	Do not engage in piracy or other unauthorised commercial use regarding the data you extract.

Additionally, some companies and websites may provide the data we are interested in in a clean and concise way through an API. If a public API that provides the information we are looking for is available, web scarping should be avoided altogether.
  
If you would like to know more, I suggest reading James Densmore’s article on the [Ethics in Web Scraping](https://towardsdatascience.com/ethics-in-web-scraping-b96b18136f01).

<br>
  
## References
  
The complete list of reference for this tutorial is included at the end of the notebook.

<br>

## Feedback

If you have any feedback or ideas to improve this project, feel free to contact me via:

<a href="https://twitter.com/korfanakis">
  <img align="left" alt="Twitter" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/twitter.svg" />
</a>

<a href="https://uk.linkedin.com/in/korfanakis">
  <img align="left" alt="LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />
</a>

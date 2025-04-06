# Selenium

## What is Selenium WebDriver?
> Selenium is a powerful tool for **automating web browsers**. It allows us to **control a browser programmatically**, **simulating user interactions** like **clicking buttons**, **entering text in forms**, and **navigating pages**. It is widely used in web scraping, automated testing, and browser automation.

# What is Selenium WebDriver?
> Selenium WebDriver is the main interface for automating browsers. It communicates diractly with the browser and controls it using a specific browser's driver (e.g., ChromeDriver for chrome, GekoDriver for firefox).

> - **WebDriver is one of the component in Selenium.**

> - **WebDriver is a Java Interface.** <br/>
> WebDriver(I) --> RemoteWebDriver(C) --> ChromeDriver(C), GekoDriver(C), EdgeDriver(C) etc

> - **WebDriver is an API (Application Programming Interface** <br/>
> USER --> URL (FrontEnd/Presentation Layer) --> ServerSide (ApplicaitonLayer/BusinessLayer/BackEnd) --> Database (DBLayer/AdminLayer) <br/>
> **Explanation**- Whenever a USER hits a URL to access tha URL OR Click on a Submit button, then a **request** will go the the **server**, and When it hits the server, there are n number of APIs presents in the Business layer, and when User sents a request, there are different type of requests are there, get, post, put, delete etc,. so what type of request we are sending from presentation layer, the corresponding type of API will hit in Business layer. And then that perticular API will get the request and triggered and then send request to the DB layer and receive **response** from the DB layer and corresponding requested response will return to the user.
> 

## Supported Browser: 
> Selenium supports all major browsers like:
> - Google Chrome
> - Firefox
> - Edge
> - Opera
> - etc

## Language Supported: 
> Selenium supports multiple programming languages for writing automation scripts, including:
> - Python
> - Java
> - C#
> - ruby
> - JavaScript

## Usage: 
> **Web Automation:** Selenium can simulate real-world user interactions (like filling out forms, clicking buttons, etc.) for web applications.
> **Testing:** Selenium is often used in automated testing to ensure that web applications work as expected across different browsers.
> **Web Scraping:** By automating browsing, Selenium can extract data from websites where other scraping tools might not be effective.

## Envoirement Setup

#### Manual Way

#### Maven way

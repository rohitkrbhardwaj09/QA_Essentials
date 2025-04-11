<hr/>
<p align="center">INDEX</p>
<hr/>

## 1. Introduction to Selenium
- What is Selenium?
- History & components (Selenium IDE, RC, WebDriver, Grid)
- Advantages & limitations

## 2. Basic Setup
- Installing Java/Python
- Installing Eclipse/IntelliJ or VS Code
- Adding Selenium libraries
- Setting up WebDriver (ChromeDriver, GeckoDriver, etc.)

## 3. Core WebDriver Basics
- Launching browsers
- Navigating to URLs
- Locating elements (id, name, class, tag, CSS, XPath)
- Basic user actions (click, sendKeys, getText, clear)
- Browser navigation (back, forward, refresh)

## 4. Locators & XPath
- Absolute vs Relative XPath
- CSS Selectors
- Advanced XPath (contains, starts-with, following-sibling, etc.)

## 5. Waits
- Implicit Wait
- Explicit Wait
- Fluent Wait

## 6. Handling Web Elements
- Dropdowns (Select class)
- Checkboxes & Radio buttons
- Alerts & Pop-ups
- Frames and iFrames
- Windows/tabs handling

🟡 Intermediate Level
## 7. Test Framework Integration
- TestNG (for Java) / PyTest / unittest (for Python)
- Assertions (hard/soft)
- Annotations (@Test, @BeforeMethod, @AfterMethod
- Grouping, prioritization, and parallel testing

## 8. Page Object Model (POM)
- Page Factory
- Reusability & maintainability
- Best practices

##  9. Data-Driven Testing
- Reading from Excel, CSV, JSON
- Parameterization using TestNG or PyTest
- DataProviders (TestNG) / Fixtures (PyTest)

## 10. Logging & Reporting
- Log4j or Python’s logging module
- TestNG/Extent Reports/Allure Reports

## 11. Exception Handling
- Try-catch blocks
- Common Selenium exceptions
- Debugging tips

🔵 Advanced Level
## 12. Selenium Grid
- Concept of distributed testing
- Setting up Hub and Nodes
- Parallel execution across machines/browsers

## 13. CI/CD Integration
- Git basics
- Jenkins for automation
- Running Selenium tests via Jenkins

## 14. Cross-browser Testing
- Running tests on Chrome, Firefox, Edge, Safari
- Handling browser-specific issues

## 15. Handling Advanced Scenarios
- File Uploads/Downloads
- JavaScript Executor
- Shadow DOM elements
- Captchas & 2FA (with limitations/workarounds)

## 16. BDD with Cucumber (Java) / Behave (Python)
- Gherkin syntax (Given-When-Then)
- Feature files
- Step Definitions
- Integration with Selenium

## 17. Docker + Selenium Grid
- Introduction to Docker
- Running Selenium tests on Docker containers
- Docker Compose with Selenium Grid

<hr/>
<hr/>
<hr/>

# Selenium

##  What is Selenium WebDriver?
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

##  Supported Browser: 
> Selenium supports all major browsers like:
> - Google Chrome
> - Firefox
> - Edge
> - Opera
> - etc

##  Language Supported: 
> Selenium supports multiple programming languages for writing automation scripts, including:
> - Python
> - Java
> - C#
> - ruby
> - JavaScript

##  Usage: 
> **Web Automation:** Selenium can simulate real-world user interactions (like filling out forms, clicking buttons, etc.) for web applications.
> **Testing:** Selenium is often used in automated testing to ensure that web applications work as expected across different browsers.
> **Web Scraping:** By automating browsing, Selenium can extract data from websites where other scraping tools might not be effective.

##  Envoirement Setup

##  Manual Way

##  Maven way

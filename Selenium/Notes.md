# Module-1: Overview on Automation & Selenium

**1. Introduction to Automation**

  - **Automation Testing**: Using tools/scripts to execute test cases automatically.
  - **Goal**: Increase test efficiency, coverage, and reduce human errors.
  - **Used For**: Regression, smoke, sanity, load testing, etc.
<hr/>

**2. Challenges in Manual Testing**

 - Time-consuming & repetitive.
 - Error-prone (human mistakes).
 - Not suitable for large-scale or frequent regression testing.
 - No reusability of test cases.
 - Limited test coverage under tight deadlines.
<hr/>

**3. Overcoming Challenges with Automation**

<table>
  <tr>
    <td>Challenge (Manual)</td>
    <td>Solution (Automation)</td>
  </tr>
  <tr>
    <td>Repetitive tasks</td>
    <td>Run scripts repeatedly, quickly</td>
  </tr>
    <tr>
    <td>Human errors</td>
    <td>Accurate and consistent test execution</td>
  </tr>
  <tr>
    <td>Less coverage</td>
    <td>Run many tests across environments/browsers</td>
  </tr>
  <tr>
    <td>Time-consuming</td>
    <td>Fast execution via tools like Selenium</td>
  </tr>
</table>
<hr/>

**4. Importance of Programming in Automation**

 - Required to write test logic, loops, conditions.
 - Enables:
   - Data-driven testing
   - Modular framework design
   - Use of OOPs concepts (Java)
 - Example:
  ```Java
    WebElement btn = driver.findElement(By.id("submit"));
      if (btn.isDisplayed()) {
        btn.click();
      }
  ```
<hr/>

**5. Introduction to Selenium**

 - Selenium is an open-source automation tool for web applications only.
 - Supports multiple browsers and languages.
 - Does not support desktop or mobile apps directly.
<hr/>

**6. Selenium Components**

📦 Selenium Suite:
<table>
  <tr>
    <td>Component</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Selenium IDE</td>
    <td>Record & playback tool, Firefox/Chrome extension</td>
  </tr>
  <tr>
    <td>Selenium RC</td>
    <td>Obsolete; used a server to communicate with browsers</td>
  </tr>
  <tr>
    <td>Selenium WebDriver</td>
    <td>Directly interacts with browsers using drivers</td>
  </tr>
  <tr>
    <td>Selenium Grid</td>
    <td>Runs tests in parallel across machines/browsers</td>
  </tr>
</table>
<hr/>

**7. Selenium WebDriver Architecture**

```plaintext
Test Script (Java)
      |
Selenium WebDriver API
      |
Browser Driver (ChromeDriver, GeckoDriver)
      |
Browser (Chrome, Firefox)
```

**8. Advantages(✅) & Disadvantaged(❌) of Selenium WebDriver**

**--Advantages of Selenium WebDriver--**

  ✅ Open-source and free

  ✅ Cross-browser support (Chrome, Firefox, Edge, etc.)

  ✅ Cross-platform (Windows, macOS, Linux)

  ✅ Language support (Java, Python, JS, etc.)

  ✅ Integration with TestNG, Maven, Jenkins, etc.

  ✅ Supports parallel testing via Grid

**--Disadvantages of Selenium WebDriver--**

  ❌ Only web application testing

  ❌ No built-in reporting

  ❌ No support for desktop/mobile apps (need Appium for mobile)

  ❌ Requires programming knowledge

  ❌ No built-in object repository


# **Module-4: Selenium WebDriver**

### **1. Introduction to WebDriver and Architecture**

Selenium WebDriver can be defined in three ways:

**1) WebDriver is one of the component in selenium.**
> Component of Selenium Suite:
> - Selenium Suite includes:
>   - Selenium IDE
>   - Selenium WebDriver
>   - Selenium Grid
> - WebDriver is the core component for automating web applications.

**2) WebDriver is a java interface.**
> - WebDriver is a Java interface containing:
>   - Public & static variables
>   - Public, default, and abstract methods
> - It is implemented by:
>   - RemoteWebDriver class, which is extended by:
>     - ChromeDriver
>     - FirefoxDriver
>     - EdgeDriver
>     - (etc., for other browsers)
> ```plaintext
> WebDriver (interface)
>     ↓
> RemoteWebDriver (class)
>     ↓
> ChromeDriver / FirefoxDriver / EdgeDriver (classes)
> ```

**3) WebDriver is an API( Application Programming interface)**
> - Acts as a bridge between:
>   - Java Program (Client/Presentation Layer)
>   - Browser (Action Target)
> - WebDriver exposes methods which are invoked from a Java program (e.g., using Eclipse).
> - It performs actions on the browser:
>   - Opening URLs
>   - Entering inputs
>   - Clicking buttons
> - Communication Protocol:
>   - Old: JSON wire protocol
>   - New (Selenium 4+): W3C protocol

